# Schema
Import: category theory

Definition: *Tathata* (T) is the set that contains only itself.

Discussion: Defining Tathata as a set is necessary to use functions to work with it.  This is something of an abuse of the term, because the concept is not supposed to tolerate anything so artificial as set theory.  For us, T is simply a generic, pre-ontological starting place.  A situation without further bias, Tathata is meant to be the canvas upon we will paint meaning.

Theorem: The cardinality of T is 1

Definition: A *world* is a quadruple: (W, O, A, H) where:
    - W is a finite category
    - O is a partition of W's objects (a set of object-types)
    - A is a partition of W's arrows (set of arrow-types)
    - H is a set of predicates (in terms of O and A) which *H*old in W

Definition: A *lens* is a function onto a world.

Definition: A *primary lens* is a lens whose domain is T.

Definition: - Lenses are said to *define* the world that is their codomain.
            - Lenses that are not primary are said to be *defined in terms of* the world that is their domain.  

Definition: A *composite lens* is a lens _h_ which can be expressed as the composition of at least two other lenses, _f_ and _g_ such that f(g(x)) = h(x).

Example: Facebook is a world.  O = { people, content }, A = { likes, friendships }. W has for objects the union of the sets in O, and has arrows as the union of the sets in A.  In the case of Facebook, we find that like-type arrows only occur from people to content and that friendship-type arrows only occur between people and other people--but always symetrically.  That is to say, for a,b in A, if a is friends with b, then b is friends with A.  These two predicates together form H_facebook.

Example: A traffic intersection is a world.  O = { lanes, vehicles, stop-bars, signals, moments }.  A = { yield-to, stop-when, go-when, etc.}.  H includes statements like, "two vehicles may not share a lane in the same moment, if they would, instead one must yield-to the other".

Discussion: Any two people observing an intersection will confront the same Tathata, but when asked to describe it they may find different lenses and end up describing different worlds.  For example a different lens might take a second viewer to a world where yeild-relationship might be something that exists between lanes--not vehicles.  A third person, confronted with the same Tathata might map it the whole intersection to a world with just one object (of the type: waste-of-taxpayer-money).  This third world would likely be defined in terms of a world whose arrow-types are things like "elected".

One might ask: Given two worlds, which is better?  Which should we use?  Tathata itself gives us nothing with which to make such a judgement.  It just sort of... is.  In some cases we may be able to find a way to find the best world--in others, we may not.

Axiom: All worlds have at least one primary lens, it may be composite.

Definition: The _genesis of A_ is the list of lenses whose composition (in order) yields a primary lens for A.

Example: Let A and B be worlds defined by primary lenses _h_ and _k_.  Now consider these two alternatives:

i) A = h(T) = f(g(T))
   B = k(T) = j(l(T))
   g != l
   f != j

ii) A = h(T) = f(g(T))
    B = k(T) = j(g(T))

In case (i) the genesis of A from Tathata has no known overlap with the genesis of B. Here we can say nothing about whether adopting lens h would be a _better_ or _worse_ choice than adopting lens k--they're simply different perspectives, and they'll put you in different worlds.

On the other hand, in (ii) we can see that A and B share a common parent, the world g(T).  If it turns out that g(T) has something to say about the relative merits of lenses (e.g. maybe g has types like "irrational" or "sinful" and connects those concepts with properties that A has, but that B doesn't) then we may be able to appeal to the common heritige of the worlds A and B and indeed come up with an answer about which one is better.

Definition: In part (ii) above, _g_ is called a worldview over A and B.  A lens is a worldview over some set of worlds if it is part of the genesis of each world in the set.  Worldviews are useful because they let us reason about relationships between objects in separate worlds.

Example: Physics is a world, and its parent lens is worldview over { Astronomy, Zoology }.  The genesis of Physics from Tathata is unlikely to have much to do with llamas or Betelgeuse.  Further, neither Astronomy nor Zoology are likely to explicitly suggest that llamas are unlikely to be able to survive very near Betelgeuse.  Conveniently, I can appeal to their common parent and with some thought, come to the conclusion that Betelgeuse is probably no place to park a llama.

Definition: In part (i) above, the inability to establish precedence between A and B is called a _toplevel lens dilemma_.

Example: "Is it more important that the black knight take the rook at A6, or that the ice cream not sit out too long?"  This question, lacking additional context, puts you in a toplevel lens dilemma.  For all you know, it's plenty cold out, so the ice cream is fine.  Or maybe checkmate is right around the corner, and the rook on A6 is irrelevant.  Without developing further structure, there is no way to decide which of these outcomes is favorable.

Questions: Are all toplevel lens dilemmas resolvable by adding context?  If I tell you that it's your ice cream, but it's not your game of chess, you can construct a worldview over both in which the ice cream is more important--but does this trick work each time?

# Order

Undefined term: Choice (noun)

Undefined term: Values/Over (verb, X values Y over Z)

Definition: An individual is an oracle for resolving toplevel lens dilemmas










Axiom: There exists a function between the tuple (Ins, Ind) and 

Definition: analysis, a method of ordering choices so that some are more desireable than others

Definition: The meta-analysis problem
Given a 
