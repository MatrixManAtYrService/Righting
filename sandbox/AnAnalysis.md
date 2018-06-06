An analysis of ownership and value

This is gonna be dense. If I were explaining or arguing, I'd take more time--but I'm defining.  By reading further you're entering a world of my creation, either deal with it or submit a github issue requesting either explanation or argument, and please be specific, without guidance I could explain or argue my life away, and never build anything.

I am imagining a theory which would help a human decide which theories to embrace.  I'll start with some definitions and work my way into a description of some properties that this theory might have.  Note that I'm not a platonist trying to *discover* something.  I'm a hacker trying to create something.  I'll take truth where I can find it, and I'll construct truth where I need it.  Here are some definitions:

A *Theory* (noun) is a set of statements according to which some (external) statement can be judged--typically the judgement will be a proclamation that the external statement is either true or false.

*Analysis* (proper noun) refers to that theory in mathematics which concerns itself with <, >, absolute value, and epsilons. Trigonometry and calculus are subsets of analysis.  Any time you are comparing values, you're doing analysis.

*An analysis* (noun) is a specialization of Analysis onto a domain of reasoning which influences human behavior (that is, human behavior concerning itself with something other than pontificating about epsilons).

*Value* means the stuff off analysis.  In an analysis of financial decisions, this means dollars. In an analysis of spacecraft trajectories, this might be some function of fuel, time, and mission success likeleihood. If you're playing chess this is the probability of checkmating your opponent--unless you're already certain that you can do so, in which case it's the number of moves necessary to win (unless you're on the run, then it might be the number necessary to achieve stalemate).

Value exists only in conjunction with an analysis.  There is no such thing as the best decision for you to make right now--only the best decision for you to make *given some analysis*.  This is arguable, but it is not what I want to argue right now.  In case you don't like it, note that I'm ok with there being some kind of *correct analysis*, according to which your best move is objectively the best. (I don't believe in such a thing myself, but this difference between us will not interfere with my purposes here).

Analyses (that's the plural of analysis) might be unrelated to one another.  This is like the way chess-strategy is unrelated to spacecraft trajectory.  Analyses also might relate to one another to through *support*.  Analysis A *supports* analysis B if the following scenario makes sense:

Human:                   I make decision b
Hypothetical Inquisitor: Why?
Human:                   Because according to analysis B, decision b is optimal.
Hypothetical Inquisitor: Why?
Human:                   I dunno, that's just how analysis B works.
Hypothetical Inquisitor: Yeah, but why use analysis B?
Human:                   Because according to analysis A, using analysis B is optimal.

In this scenario, we say that A > B.  Restated, A > B if A can motivate someone chose B from some set of alternatives.  For example, there are a number of schools of thought regarding how to play chess.  The B-type analysis might require inputs like: 

> From A7 I can threaten two pieces at once with a knight--no deceptions, just hard choices

While the A-type analysis might require inputs like

> Forcing people to repeatedly choose between two bad alternatives, even given full information, is a fun and effective way to win

It might be tempting to assume, given that I've used the symbols < and >, that analysis support behaves the same way that you're used to < and > behaving in other places.  Please resist.  Here are some potentially tempting assumptions:

- Antisymmetry : If A < B then it is not the case that B > A
- Transitivity : If A < B and B < C then A < C

Most of the analyses you are familliar with have these properties.  Later, I'd like to explore why this is.  For now, just notice that not all analysis are transitive.  For example, "rock-paper-scissors" is a non-transitive analysis.  Paper covers rock, rock breaks scissors, but paper does NOT cover/break scissors.  

Here we are concerned with second order analyses--those that motivate the choice between subsequent analyses.  Since "rock", "paper", and "scissors" are not analyses--the above example does not contradict the idea that second order analyses might all be transitive.  If this were the case then...

> For any given analysis there is an infinity of "higher" analyses.

...or...

> For any given analysis there here is a top-level analysis which objectively motivates "right" decisions about whether the given analysis is optimal.

I think that the first conclusion here is too fantastical to be useful, and that the second is both commonly held, and harmful.  I'll get to why it is harmful later, for now I will finish mapping the possibilities for an analysis of analyses.

The alternative to enforcing transitivity on second order analyses is to allow for cycles.  An example of such a cycle is this:
> Measurements made by clocks in sattelites conform to the theory Relativity because that theory is true.
> Relativity is true because measurements made by clocks in sattelites conform to it.

This is a 2-cycle of analyses, which forms a *coherent set*.  Each statement is both consistent with, and supports the other.  There could be more complex structures too--in order to be *coherent* each contained theory must supported by some other one, and no contained theories can contradict ano other ones in the set.

Here we run into a problem though--because we might run into two coherent sets of theories.  How can we determine which one to use?  Can one set be more coherent than another?

There are several ways that we can imagine comparing the coherence of sets of theories.  But in each case, what we're really doing is comparing the value of second-order analyses, which means we're going to need a third order analysis to make the decision.

This third-order analysis could be something like "whichever second-order analysis allows me to assess more scenarios is better", and of course this would be transitive (presumably we would use regular counting numbers to handle the "more").

Alternatively it could be: "Whichever coherent set 'feels right' according to my gut is the better one." But then later we might have to consider that gut feelings may have evolved through natural selection--so while we found a non-transitive third-order analysis, it seems like it might be the result of a transitive fourth-order analysis.

What a mess.  We've got these strata of theories, and at each step it seems like we can always find at least two distinct ways to proceed (one where the next-higher-order analysis is transitive, and one where it is not).  The contradicts the notion that eventually we'll find a top-level theory.  The more we abstract, in hopes of generalizing, the more choices we have.

----

I was going somewhere, but I ran off the rails at some point.  I'll try again later.  This was the target:

There are two kinds of ownership: ZSOwnership, which causes the owner to play zero-sum games (like protecting trade secrets), and NZSOwnership, which promotes behavior of the 'taking ownership' kind and results in nonzero-sum games (like fixing clogged toilets--which benefits everybody).  Token exchange (via a ledger) promotes ZSOwnership, which is less helpful for humanit than NZSOwnership.  It should be possible to use blockchains implement a value-tracking system other than a ledger, and which exhibits the more helpful kind of ownership (i.e. is a nonzero-sum game).

I got mixed up with the transitivity of justification for value (which I do think is relevant--somehow abstracting along the transitive axis feels like it creates coherences that are more likely to be zero-sum).
