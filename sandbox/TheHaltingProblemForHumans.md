# The halting problem for humans

## Intro

You are more than a computer, but you are _at least_ a computer.
In this document I'm going to try to convince you that all computers have limits, which means that you do too.
For this discussion let's lay down a simple definition for what computers do.
It may be overly simple, but you have my word that I'm not hiding any nasty gotchas in the simplicity.

A computer accepts input, and based on that input, changes state.
Sometimes, it only changes state for a little while, and then it stops and provides some output (we'll call this halting).
Other times, it gets stuck in some kind of cyclical behavior where it transitions from state to state, but never provides any output.
This is annoying, especially because it's sometimes challenging to know whether the computer is truly stuck in an infinite loop, or if it's working fruitfully and will halt and provide some output any minute now.

Some computers are more or less powerful than others.
In this case "powerful" is a qualitative thing, it has nothing to do with speed or access to resources like memory.
In fact, in computability theory, all computers are assumed to have infinite memory, and we're really not interested in how long they take to complete their work--just whether they complete their work at all.

## A Simple State Machine

Let's take a look at a computer that isn't very powerful, here's a diagram:
![A finite state machine](fsm.png)

The computer starts in state one (S1) and if you give it an 'a' it will transition to S2.
It won't halt though, it will just sit there, waiting for more input,
You can keep giving it a's all day long, and it will stay at S2.
Then, if you give it a 'c' it will transition to S4 and halt (that's what the extra circle at that state means).

So the computer doesn't halt for:
- ''
- 'a'
- 'aa'
- 'aaaaaaaa'
- 'acd'
- 'print("hello world")'

But it does halt for:
- 'ac'
- 'acdb'
- 'acdaac'
- 'acdbdb'

I haven't listed all of the strings that it does or does not halt for, but I hope you get the idea.
The set of strings that this computer halts for is called a _language_, and we say that the computer _recognizes_ a language if it halts for every string in that language.

The computer described here is called a deterministic finite state machine.
There are other deterministic finite state machines, and they each recognize different languages.
You could probably design one that would halt on your first name, and on your first name followed by your last name, if it received the word "hamburger" it would not halt, but instead just sit there, waiting for more input.

For this type of machine, the languages that it can recognize are called "regular languages".
They're pretty useful, but regular languages will only get you so for.

## Context Free Grammars

For example, you can't make a deterministic finite state machine that checks to see if each parenthesis has match.
That is, no machine of this type will halt on these:
- (foo)
- (foo (bar baz))
- (((((())))))

But not these:
- (foo
- (foo (bar)
- ((())))

Well ok, you could make one that halts on the first three, and not the last three, but what I mean is that you can't make one that halts on _all possible_ strings with mismatched parentheses, but that doesn't halt on _any_ string with mismatched paremtheses.

But you, as a human, can easilty solve this problem.
This means that whatever kind of computer you are, it's not a determinisic finite state machine, and whatever languages you're capable of recognizing, they are somewhat more than just regular languages.

You'll also notice that this capability of yours--to keep track of how many parenthesis still need to be closed--it's not because you have more memory than the finite state machine, it's because you have any memory (the finite state machine has none).
If you modify a finite state machine and give it the ability to remember how many outstanding parenthesis there are, you'll have created what's called a _pushdown automaton_.
A language recognized by such devices is called a _context free grammar_.

## Turing completeness

But there are tricks that even a pushdown automaton can't do, but that you or I can.
So we aren't pushdown automata either.
If you further augment your machine, and you teach it these tricks too, then you'll have constructed a _turing machine_ and it will recognize a still more expressive language.
Such a language, if it excercises the tricks that a pushdown automaton can't do, is called _turing complete_.

So there's this hierarchy:

| Machine Name | Languages Recognized |
| :-: | :-: |
| Finite State Machine | Regular Language |
| Pushdown Automaton | Context Free Grammar |
| Turing Machine | Turing Complete Language |
| Human | ??? |

Some would say that whatever computational component you contain, it is equivalent in power to a turing machine.
Others would say that you can recognize languages that turing machines can't, so you're still one level higher than they are.
We'll be getting back to how you fit in in a moment.

## Halting Problems

Earlier, we looked at a finite state machine.
Here's a question: given any finite input, could you trace through the machine and tell me if it halts for that input?
I bet you could.
Now another question: given _any_ finite state machine, and any input, could you trace that input through that machine and tell me if the input caused it to halt?
Well, maybe not in practice.
My memory, my attention span, and my patience might all be too small for a very complex state machine or very long input.
Probably, I would make a mistake.

But recall that we're only talking about qualitative jumps in capability here.
All that matters is _that_ you have the capacity for memory at all.
For this excercise, we can pretend that you're infinitely patient, focussed, and immune to mistakes.
And in that case, I think you could determine whether _any_ finite state machine woud halt on _any_ input.

That is to say, you can solve the halting problem for finite state machines.
The halting problem for _X_ goes like this:

> Given an arbitrary _X_ machine and arbitrary input string _s_, provide an algorithm that determines whether the machine will halt on the input.

Now maybe you're not quite sure how to express the algorithm you'd use in such a scenario, but it's up there, in your head, and it counts as proof that you're something more than a finite state machine.

Here's a trickier problem: can you make a finite state machine that can solve the halting problem for finite state machines?  That is, it would accept some string, along with some description of some other finite state machine, and it would halt in one state if the input machine would halt on the input string, and it would halt in another state if the input machine would _not_ halt on the input.
If you think you can do this, you should consider publishing about it, because there is a well accepted result which states that it can't be done.

Particularly, no algorithm for a computer of type _X_ can solve the halting problem for computers of type _X_.
So whatever theoretical computer type you are equivalent in power to, you can't solve your own halting problem.

## But what would such a problem look like?

Recall that we're only talking about your capacity follow algorithmic instructions and arrive at some result, and also that to halt is to reach the end of whatever instructions you're following.
We will indicate the halting step with the word: "Stop"
Before posing a halting problem, let's look at what this kind of thing would look like for humans:

Recipe A:
1. Put your left foot in
2. Put your left foot out
3. Put your left foot in
4. Shake it all about
5. To the hokey pokey and turn yourself around
6. Stop

Recipe B:
1. Stand Up
2. Sit Down
3. Go to step 1

Recipe C:
1. Pick a positive integer
2. Divide your number by six and remember the remainder
3. Go to whatever step is indicated by the remainder plus 1
4. Go to step 5
5. Go to step 4
6. Stop

Recipe D:
1. If there is a largest pair of twin primes, pick the number 6
2. If there is not a largest pair of twin primes, pick the number 4
3. Go to the step of the number you picked
4. Go to step 5
5. Go to step 4
6. Stop

For recipe's A and B our task is easy.
A human computer running recipe A will halt, and a human computer running recipe B will not halt.
Even though we're humans, and these problems are related to the halting probem for humans (which is supposed to be unsolvable for us), we can recognize patterns that tell us what would happen if a human followed the recipe.
In the case of recipe B, we don't even have to loop very many times before it becomes obvious that we would loop forever if we continued.

Recipe C is a scientific curiosity.
If you had perfect information about the internal state of the human, could you predict the number they would choose at step one?
If so, then perhaps you could indeed say whether the human would halt (reach the stop step).
I suspect that there are a variety of interesting problems that would prevent you from being able to perfectly predict the behavior of a human asked to choose a number at random (or do any other action with a potentially nondeterministic result).
But hey, maybe it's possible.

Recipe D, though, is a doosie.
Recall that we're working with humans that are infinitely motivated, have infinite memory, attention span, and any other mental capability that you have--but might want enhaced.
Currently, no human alive knows whether there is a largest pair of twin primes (though many mathematicians think that there is not).
In order to follow Recipe D, our weakly superhuman test subject would have to complete the mathematics research necessary to resolve the twin primes conjecture before proceeding to step two.
But here's the thing: we don't know whether proving the twin primes conjecture is mearly difficult, or in fact impossible.
Such a human trying to get to the bottom of that particular problem might take a very long time, or they might take forever.

Now that we have a feel for the difficulty of of knowing whether a human computer would halt on specific input, let's consider the halting problem for humans in general.
A solution to the problem would be a recipie, like the ones above, except that it would tell you how to take any human, and any recipe, and determine whether that human would be able to complete that recipe, and in either case, it would have to halt in finite time.

## Conclusion

I still can't tell you whether you're a turing machine or some more powerful computer.
Nobody has ever solved the halting problem for turing machines, a fact that would be easy to explain if we were equivalent to turing machines.

Maybe my choice of letting Recipe D fall to an unsolved math problem seems a bit strange.
I expect it would if you consider math to be like astronomy--where we study the properties of things that are actually out there.
I don't think math is like this.
I think math is what you get when you start naming all of the ways that it is possible to think.
In this light, the connection to the various types of computers is pretty straightforward:
Each subsequent computer type is defined by adding a previously unavailable "way to think".

I went looking for limits on our cognitive capacity (however farfetched) because I wanted an example of a case where we can know that something is unknowable (to us).
I don't think that this is the only knowably unknowable thing.
In fact, I think some of us make the mistake of claiming to know an unknowable because we're on one side of a disagreement, and we can't back down because if we admitted we didn't know then the other side would surely claim that they know.
If knowably unknowable were a more common concept, maybe we would spend less time fighting over who is right, and more time finding better ways to live with each other.

## A final note

Another reason to couple computability with unsolved problems in mathematics:
Godel's incompleteness theorem states, more or less, that any formal system that contains natural numbers also contains true but unprovable statements.
The Church-Turing thesis states, more or less, that computing an arbitrary function on the natural numbers requires a turing machine.
So Godel established that there was an unprovable statement--that is (according to Church and Turing) unprovable by a turing machine, and then he later established that the unprovable statement was true--something he couldn't have done with a turing macine.
Because of this, I suspect that Godel's proof contains an operation that humans are capable of, but that turing machines aren't.
If I'm right, then humans are at least Godel machines (one step above turing machines).  From that position, the hunt would continue for still more computational tricks that we didn't know we had up our sleeves.


Lastly, what would it be like if we encountered an intelligence which was at a higher level in the hierarchy of theoretical computers established above?
Such a being would be able to make predictions about our own behavior that we would probably find unsettling (because it could solve the halting problem for humans).
Suppose it reached into its strongly-superhuman skillset and presented us with an answer to a question that we couldn't have come up with on our own.
(The computer sciency word for such a being is an _oracle_.)
Could we verify the authenticity of the answer, or would our ability to justify a belief in it have to rely on faith?

