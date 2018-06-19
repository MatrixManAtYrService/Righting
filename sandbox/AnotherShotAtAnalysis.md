# Schema Import: category theory

Definition: *Tathata* (T) is the set that contains only itself.

Discussion: Defining Tathata as a set is necessary to use functions to work with it.  This is
something of an abuse of the term, because the concept is not supposed to tolerate anything so
artificial containership (which troublingly requires some division between container and thing). For
us, T is simply a generic, pre-ontological starting place.  A situation without further bias,
Tathata is meant to be the canvas upon we will paint meaning.

Theorem: The cardinality of T is 1

Definition: A *world* is a quadruple: (W, O, A, H) where:
    - W is a finite category which contains T
    - O is a topological space where: 
        - the points are W's objects
        - the open sets are types of objects
    - A is a topological space where:
        - the points are W's arrows
        - the open sets are compositions of W's arrows such that the composition's domain is T
    - H is a set of predicates (in terms of O and A) which *H*old in W

Note: Arbitrary sets of types over a category's objects and arrows are not sufficient to form a
world.  However, given some set of types, there are some standard modifications one can make so that
it becomes a world:

    - O and A must be well defined topological spaces, which means:
        1. Open sets must be closed under unions
        2. Open sets must be closed under intersections
        3. Several things regarding infinity that we don't have to worry about since W is finite
           the intersection.
            - For objects:
                1. Throwing in the generc type: Pair<X,Y> achieves this
                2. Treating "things that are both X and Y" as a type is sufficient to meet this
                   requirement (2 is like if the world was designed by somebody who really loved
                   class inheritance)
            - For arrows
                1. Add an object (the index) and from it add arrows to any object which does not
                   already have an arrow onto it.

Definition: A *lens* is a function onto a world.

Definition: A *primary lens* is a lens whose domain is T.

Definition: - Lenses are said to *define* the world that is their codomain.
            - Lenses that are not primary are said to be *defined in terms of* the world that is
              their domain.  

Definition: A *composite lens* is a lens _h_ which can be expressed as the composition of at least
two other lenses, _f_ and _g_ such that f(g(x)) = h(x).

Example: Facebook is a world.  O = { people, content }, A = { likes, friendships }. W has for
objects the union of the sets in O, and has arrows as the union of the sets in A.  In the case of
Facebook, we find that like-type arrows only occur from people to content and that friendship-type
arrows only occur between people and other people--but always symetrically.  That is to say, for a,b
in A, if a is friends with b, then b is friends with A.  These two predicates together form
H_facebook.

Example: A traffic intersection is a world.  O = { lanes, vehicles, stop-bars, signals, moments }.
A = { yield-to, stop-when, go-when, etc.}.  H includes statements like, "two vehicles may not share
a lane in the same moment, if they would, instead one must yield-to the other".

Discussion: Any two people observing an intersection will confront the same Tathata, but when asked
to describe it they may find different lenses and end up describing different worlds.  For example a
different lens might take a second viewer to a world where yeild-relationship might be something
that exists between lanes--not vehicles.  A third person, confronted with the same Tathata might map
it the whole intersection to a world with just one object (of the type: waste-of-taxpayer-money).
This third world would likely be defined in terms of a world whose arrow-types are things like
"elected".

One might ask: Given two worlds, which is better?  Which should we use?  Tathata itself gives us
nothing with which to make such a judgement.  It provides no tools to make judgements about itself.
In some cases we may be able to find a way to find the best world--in others, we may not.

Definition: The _genesis of A_ is the list of lenses whose composition (in order) yields a primary
lens for A.

Example: Let A and B be worlds defined by primary lenses _h_ and _k_.  Now consider these two
alternatives:

i) A = h(T) = f(g(T)) B = k(T) = j(l(T)) g != l f != j

ii) A = h(T) = f(g(T)) B = k(T) = j(g(T))

In case (i) the genesis of A from Tathata has no known overlap with the genesis of B. Here we can
say nothing about whether adopting lens h would be a _better_ or _worse_ choice than adopting lens
k--they're simply different perspectives, and they'll put you in different worlds.

On the other hand, in (ii) we can see that A and B share a common parent, the world g(T).  If it
turns out that g(T) has something to say about the relative merits of lenses (e.g. maybe g has types
like "irrational" or "sinful" and connects those concepts with properties that A has, but that B
doesn't) then we may be able to appeal to the common heritige of the worlds A and B and indeed come
up with an answer about which one is better.

Definition: In part (ii) above, _g_ is called a worldview over A and B.  A lens is a worldview over
some set of worlds if it is part of the genesis of each world in the set.  Worldviews are useful
because they let us reason about relationships between objects in separate worlds.

Example: Physics is a world, and its parent lens is worldview over { Astronomy, Zoology }.  The
genesis of Physics from Tathata is unlikely to have much to do with llamas or Betelgeuse.  Further,
neither Astronomy nor Zoology are likely to explicitly suggest that llamas are unlikely to be able
to survive very near Betelgeuse.  Conveniently, I can appeal to their common parent and with some
thought, come to the conclusion that Betelgeuse is probably no place to park a llama.

Definition: In part (i) above, the inability to establish precedence between A and B is called a
_toplevel lens dilemma_.

Example: "Is it more important that the black knight take the rook at A6, or that the ice cream not
sit out too long?"  This question, lacking additional context, puts you in a toplevel lens dilemma.
For all you know, it's plenty cold out, so the ice cream is fine.  Or maybe checkmate is right
around the corner, and the rook on A6 is irrelevant.  Without developing further structure, there is
no way to decide which of these outcomes is favorable.

To solve this, we can employ a method I'll call *linking by context*, which causes us to search for
a lenses that is a worldview over both of the worlds.  If we discover a lens which provides some
means of evaluating the dilemma--something like: "This chess game is more important than anything
else"--then we have solved the dilemma.  In this case, we have solved it by finding something else
top-level.

Example: There will usually be multiple ways to arrange any set of lenses. Consider these lenses:

        p(T) = P: A typical physics, where the object-types are particles and packets of energy
        o(T) = O: Orbital mechanics, where an object-type is sattelites

    i) It would be pretty straightforward to think of p as a worldview over O ( o(p(T)) = O ), and many do.  Sattelites consist of particles, so asking *why?* to any quesion about sattelites might transform it into a question about particles--hopefully one that physics can answer.

    ii) Maybe, you can also think of O as a worldview over P as well ( p(o(T)) = P ).  Think about *why* we often apply physics to our problems.  Many would say, "because it predicts that sattelites stay in the sky--and in fact, they do!" This lens arrangement highlights the fact that physics arose from the world--if the world were different, so too would physics be.

    iii) In fact, you can actually hold both of these views.  If you ask me why physics is a certain way, I will say that it is because of the world.  And if you ask me why the world is a certain way, I will tell you how physics describes it.  We may go around in circles for a while, but eventually it will be clear that I am defining everything in terms of everything else--it goes in a circle.

Note: The lens arrangement described in (iii) is different than the ones in (i). Particularly, if you look at the worldview relation, we find that in (i) it is transitive and antisymmetric, but in (ii) it is just transitive.  So far, we have not discussed the use of lenses which say that other lenses are *better* or *worse* than each other--but once we have we will look at a wide variety of examples and attempt to classify them. Worldview antisymmetry will be one of the classifications we are interested in.

# Order

Undefined term: Choice (noun)

Undefined term: Values/Over (verb, X values Y over Z)

Definition: An individual is a toplevel lens which shows a world that contains oracle for resolving toplevel lens dilemmas.









Axiom: There exists a function between the tuple (Ins, Ind) and 

Definition: analysis, a method of ordering choices so that some are more desireable than others

Definition: The meta-analysis problem Given a 
