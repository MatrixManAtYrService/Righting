# If Time Were Money

If time were money then moments when I had more time would also be moments when I had more money.
This is not the case, so time is not identically money.
But maybe time and money are the same sort of thing, sort of like snow and hail.
If this were about snow and hail then we would eventually find our way to terms like temperature, electromagnetism, and crystaline structure.
Instead I expect we'll find our way to terms like value, motivation, and exchange.

Before we proceed, I'd like to modify the phrase slightly.
As it stands, I have yet to establish any correspondence (like maybe temperature will somehow correspond with transaction fees), and I am reluctant to start with "time" and "money" because I think that time is to clocks like value is to money.
You can ignore your watch and examine the wall clock--the time is the same; you can exchange your dollars for yuen--the amount of value is the same.
So what we'll actually be exploring is the simmilarities between time and value.

The similarity that attracted me to this analysis is that both time and money are somehow involved with reducing complex things to at least a preorder, and probably an equivalence relation.
Some notation:
For time, we'll use <= to indicate "preceeds or coincides with according to a narrator "
The idea is that it's ok to show up early and then wait around, or to show up on time, but being late is an altogether different thing.
For value, we'll use <= to indicate "would be rationally traded for in a market where trades are unrestricted"
Here the idea is that maybe you're exchanging comodities at a profit, or maybe it's an even trade, but you're going to behave quite differently if you're about to be ripped off.


Some proofs:
Time is reflexive because if a <= b then b <= a
Time is transitive because if a <= b and b <= c then a <= c
Yeah, it's gonna be one of those papers.
These two properties also apply to value.

So far we have time as a preorder on moments, and value as a preorder on commodities.
For now, let's assume that history doesn't repeat itself so well that a <= b <= a is true for moments a and b.
That is to say: time doesn't loop.
Let's also assume that market conditions are such that in a single moment, finite set of agents will rationally choose to make only a finite set of trades.
With these two assumptions, we can conclude that time and value are also symmetric, which (given the above properties) makes them equivalence relations.
This is handy because equivalence relations are well understood.

Something about this condition on value reminds me of the axiom of determinacy, which was unexpected at the ouset of this endeavor.
Here's the relationship:
The axiom of deterinacy states that a certain sort of game involving successive picks from a set will have a player that can win.
It's a bit weird because the games may involve an infinity of picks, so you can't actually derive a winning strategy with finite considerations--which is why it needs an axiom.
The value-symmetry assumption I have made above indicates that if you could somehow stop time so that commodities don't change, but also grant all market participants as much time as they need to make trades, that eventually there would be a state where nobody would want to make any more trades.
It's equally weird becuase you're ignoring a potential infinity in the middle (why not have two agents swap comodities forever?) and asserting that an end-state exists.

Since time is alledgedly money (or rather, value), then perhaps something about the time-symmetry assumption should resemble the axiom of determinacy too.
Well, in value-symmetry, one can imagine quite a convolution of ways that agents could trade ad-infinitum and muddying the waters about how the commodities are valued.
But in our first draft for time-symmetry, there was only one dissalowed configuration--a big loop where the start was both before and after the end.
Let's change this.

Imagine instead a community of narrators, all contributing to the story--but taking turns.
They needn't have the final word exactly, but they may have conflicting interests regarding how the story is told.
This would be something like how conflicting authors in wikipedia ultimately make concessions until (hopefully) the resulting article represents something that both sides can stomach.
It's not precicely like that though, because time and effort are resources that prevent infinite circular editing.
Instead, imagine some rule that make a certain part of each edit permanent--maybe just a randomly chosen letter or somesuch.
If both narrators have a stake in the result, they have a reason to not disagree too strongly--otherwise the story is going to become filled with hazards that they must awkwardly avoid while still managine to achieve their ends.

If this is true of time, then it relates to the axiom of determinacy through games like eeny-meeny-miny-moe.
There is a... poem? which is recited while a finger is pointed.
The finger moves between alternatives when certain parts of the poem are spoken.
The goal is to ultimately choose one of the alternatives.
In a discourse where time is symmetric the poem goes like this:

    Eeny meeny miny moe
    catch a tiger by his toe
    if he hollers let him go
    my mother said to pick the very best one and you are not it.

In a discourse where time is not symmetric, somthing like this might happen

    Eeny meeny miny moe
    catch a tiger by his toe
    if he eeny meeny miny moe
    catch a tiger by his toe
    if he eeny meeny miny moe...

Here we have a finite incantation failing to terminate because time has somehow folded up and hidden the final word.
The revised time-symmetry assumption guarantees that time cannot be folded in this way.
It relates to the axiom of determinacy because that axiom guarantees that games like eeny-meeny-miny-moe will ultimately result in a choice being made--which precludes the sort of time shenanigans described above.

What you have seen so far is typical of how I plan to proceed.
I'll point out obvious differences in time and value, and I'll be maleable with how I understand those words.
Once sufficient theoretical structure emerges, I'll re-evaluate and see whether the modified usages can be made useful--with luck, we'll discover something.

  
