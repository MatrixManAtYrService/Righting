Whether, and Why, Fermat's Last Theorem is Important
===================================================e

## Intruduction

I recently had a conversation with an English teacher about Fermat's last theorem.  She will soon be teaching a play that references the theorem (*Arcadia*, by Tom Stoppard), and had apparently been attempting to understand it by reading about Andrew Wiles' proof.  She mentioned that she didn't yet see what elliptic curves had to do with it.  I didn't have the heart to tell her that his proof is about as inaccessable to the non-mathematicioan as a challenging work of philosophy--written in Old English--would be to the modern English speaker (that is to say, totally).  

I find that my mathematics education (a nearly-complete undergraduate degree) has not armed me with the critical mass of vocabulary necessary to even take a shot at Wiles' proof.  I know what rings and fields are, and I can spell Galois, but I stub my toe on "modular forms".  Most working mathematicians would get further than myself, but unless they specialize in the right area, I expect they would come across similar problems.  The conceptual challenge invloved in understanding Wiles' proof is probably not a walk in the park either--but mathematicians tend to specialize so completely that few are likely to know the right dialect of Number Theory.  With this in mind, perhaps I should warn her about what she is getting into--so as not to have her waste her time.

On the other hand, the willingness to engage with advanced mathematics is uncommon outside of the discipline.  Too often I find myself exiting a classroom--equations still on the board--and hear somebody entering say "I'm not smart enough for whatever *that* class is about."  They mistake not knowing the language with being unable to handle the concepts.  This is a common perception, and I hate it because it drives people away from mathematics.  I appreciate that my Engish-teaching-friend has not fallen into this trap, so I can't in good conscience shut her down about it.

Fortunately, one can have an appreciation for why Fermat's last theorem is cool, without being able to prove it.  Only a basic algebraic competence should be necessary for that appreation--stuff that I feel comfortable teaching.  In this paper I intend to package the necessary bits for my friend the English teacher and, by proxy, her students.  It is my hope to equip them with enough context for the theorem that they notice a few of the subtleties that I'm sure Stoppard has included in the play.  Also, courses for non-math-majors in the USA are calculation-based provide very little insight into the activities of the pure mathematician (which Fermat was).  I hope to provide some insight into various norms surrounding that body of discourse in order to dispel any notion among the students that these are men with especially powerful calculators.

## The Conjecture

### Context

Fermat's claim was found in a copy of *Arithmetica* by Diophantus of Alexandria (written in the third century C.E.).  It is basically a bank of problems together with descriptions of how to solve them.  I found [a translation](https://ia802605.us.archive.org/34/items/diophantusofalex00heatiala/diophantusofalex00heatiala.pdf) and took a crack at Book II, problem 6, which reads:

> To find two numbers having a given difference and such that the difference of their squares 
> exceeds their difference by a given number.

The same problem might be stated differently in a modern high school algebra book (see below).  I was pleased to find that I could solve it.

> Use the following system of equations:
> 
> a - b = c
> a^2 - b^2 = c + d
> 
> 1) Find an expression for a in terms of c and d
> 2) Find an expression for b in terms of c and d

It was not the margin for II.6 that Fermat used to make his claim--it was II.8.  I have included a different problem here to point out that there are no references to triangles here.  The formula for Fermat's Last Theorem (hereafter FLT) bears a striking resemblance to the Pythagorean Theorem.  And perhaps, in a round-about way, they are indeed related.  One might ask if Diophantus' would have included a sum of squares problem in his book if the Pythagorean school hadn't made such problems geometrically interesting.  Still, if Diophantus held triangles in his head while he penned this problem, he at least was not explicit about it.  Here is the problem:

> To divide a given square number into two squares

Or in modern parlance:

> Given a value for c, find a solution to the following equation: a^2 + b^2 = c^2

And here is the method of solution given by Diophantus:

> Given square number 16.
> x^2 one of the required squares. Therefore 16-x^2 must be equal to a square.
> Take a square of the form (mx - 4)^2, m being any integer and 4 the number which is the square 
> root of 16, e.g. take (2x - 4)^2, and equate it to 16 x^2.
> Therefore 4x^2 - 16x + 16 = 16 - x^2
> or 5x^2 = 16x, and x = 16/5.
> 
> The required squares are therefore 256/25, 144/25.

The first thing that jumps out at me here is that Diophantus considers the ratio of what we would call "perfect squares" to be itself a square.  This is not how we usually use that word.  It's easy enough to get your head around the modification, but it does bring to mind a concern:  We are communicating with a man who is eighteen hundred years dead, and never spoke english--what other pieces of the puzzle might our modern view be masking?  

I think that one of the really cool things about math is that it relies on context so weakly.  A notion, properly expressed in mathematics, can stand on its own more completely than any other means of expression that I am aware of.  Nothing exists totally in a vacuum, however, especially not this problem.  As it turns out, Diophantus did not accept irrational numbers, negative numbers, or even zero.  To Diophantus, a number must be expressed as the length of a line segment, anything else was absurd.

This explains why he didn't bother ask whether the solution was rational (which it would have to be in order for his use of "square" to hold up)--which is the second thing to come to mind when I examine his method.  Despite having lived 800 years after the Pythagorean school discovered (and tried to keep secret) the existence of irrational numbers--their use still wasn't considered legitimate enough for Diophantus ("The Father of Algebra") to bother mentioning them.  

The last thing that strikes me about Diophantus' work is how comfortably he calls in his variable *m*. Implicit in his construction is the fact that each square can be decomposed into the sum of two "squares" in an infinitude of ways.  That is a remarkable property for any construction and I think that Diophantus' lack of remark on it indicates a siginificant difference in attitude between his time and ours.

### Formation

Fermat was probably not especially challenged by the problem as stated in *Arithmetica* but he found the thought amusing enough to put it in a margin after making three modifications:

    1. Restrict acceptable solutions to the integers.
    2. Ask not for a method for finding solutions, but instead about what values for *n* solutions exist at all.
    3. Instead of squares, consider numbers of any (*n*th) power.


