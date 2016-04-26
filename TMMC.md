I have heared it said that we could have built a different mathematics than we did.
Suppose so, how should we feel about the mathematics that we have?
It has grown with us after all--and we with it--for a long time.
Maybe we're idealy suited to each other.
On the other hand, our mathematics is the result of creative choices by smart, but fallible, people.
It might have some rough spots.

If math is an art, then perhaps like other arts it could have a healthy relationship with criticism.
Or, if math is a tool, then maybe we could use a method for assessing how well a particular theory fits the application--and a guide for the constructing an even better fit.
However you prefer to look at it, what is called for is a theory that lets us study the properties of other mathematical theories, and the way they those theories apply to the models that they are paired with.
In this paper I propose such a theory, it is called a Topological Metatheory for Mathematical Criticism, or TMMC for short.

For our purposes here, a theory is a set of theorems all of which can be proven from some set of axioms.
These theories could be something as small as a particular proof, or as large as a whole branch of mathematics.
TMMC makes use of theories like this as basis sets for a topological space.
Before we define these sets and argue that this really is a basis, we must be sure that these creatures are well behaved enough to be treated as sets.

It is generally accepted that the same theorem can have more than one proof, and there is some sense in which a given axiom can have numerous equivalent statements.
This equivalence is necessary to understand the structure of mathematics, and TMMC does make use of it, but not yet.
The strategy here is to first construct a topological space where proof and axiom equivalence is ignored, and then to reintroduce that equivalence and use it to form a quotient space which will assume the structure that was at first neglected.
So for our first construction, we will ignore the content of our axioms and treat them as roughly atomic[1].
We will also treat two theorems as equal when they have the same proof.

This shifts the concern to whether we can identify when two proofs are equal.
It will be conventient to think of the points in our theories as nodes on a directed tree.
In this tree the directed edges mean "proved in terms of," so axioms have no incoming edges, but theorems do.
If a theorem has an outgoing edge, then it is used to to prove some other theorem in the theory.
With this structure in mind, any theorem can be traced backwards along the graph to its axioms, and the resulting subgraph can be thought of as a proof for that theorem [2].
If this process yields the same subgraph for two points, then those points have the same proof, and are therefore equal.

[diagram here]

Referring to the diagram above, we can use this process to see that theorem 8 is equal to itself by tracing 8's proof dependency backwards to its axioms.
We find that this yields the tree containing {2,3,6,7,8} which is indeed equal to itself.
The proof for theorem 9 however requires axiom 4, which is not required for theorem 8, so we find that--as expected, theorems 8 and 9 are not equal.

Before we build our topological space, we will need one additional set: C, the character set.
Characters are entities to which theorems apply, but whose existence is not asserted by a theory on it's own.
If I were to pose a problem to you that started with "Let n be a natural number," the first two words would indicate that the proof I seek contains an element from C, and the last two indicate that, if this proof is to be an effective communication, the natural numbers should be a model for one of the theories in our basis.

Consider a set of theories, together with C.
Let T be the set of all propositions[3] that are provable from the axioms among our basis theories, plus any cast of characters from C.
Let h be a collection of subsets of T such that each element of h can be proven from axioms (and characters) in the proposed basis.
We call Th theory space, and claim that it is toplological [4].
Note that T is open by construction, and that the empty set is open vacuously.
Since every open set contains a path back to the axioms for every point, no union of open sets will ever orphan a theorem.
As for intersections, note that if a theorem is in the intersection of two open sets, then all of the theorems necessary to prove it must also be in the intersection.
To see an example, refer to the diagram above and consider {2,3,6,7,8} and {3,4,7,9}.
The intersection here is {3,7}, which is indeed an open set.

Notice that this construction is contingent upon the selection of basis theories.
Just for fun, I like to call these theories (together with any models for them), a platonic realm.
Examples of platonic realms include conventional mathematics as me know it, as well as any alternative mathematics that we[5] might have come up with instead.
This construcion makes sense at smaller scales too.
While learning, or teaching, a subject, a mathematician may need to limit the scope of their available theorems in order to demonstrate an acceptable proof.
The question, "which theorems can we use in the homework?" when framed in the language of TMMC, asks "What is in our platonic realm?"

As another example, consider two experts in the same field


(1) "Rougly," because we still need to retain enough information about an axiom so we can identify whether, and how, a logic rule can be applied to it.  Such an analysis would likely involve storing axioms in terms of parse-trees containing undefined terms and maybe some other linguistic elements.  For now, we will take it for granted that axioms can be understood, and treat them otherwise as points.

(2) There is still some ambiguity here.  Perhaps one can apply different logic rules to the same hypotheses in order to provide different proofs of what would be considered the *same* theorem under the given desceiption.  This is another point that will need to be addressed in a more detailed study involving proof grammar.

(3) This is not a paper for exploring self-reference paradoxes, so feel free to exclude from X anything about X itself, anything about TMMC, and anything about barbers.

(4) Note that we claimed earlier that we were building a space from a basis, and now here we argue that Theory Space is topological from definitions.  This is because TMMC is not complete.  I feel like the given sets do capture the feel of a basis, but they don't actually cover the space.  One can imagine cross-theory characters like a set of polygons with prime numbered sides.  Theorems could be proved about these characters that are not in either basis theory, but result from the joining of the two.  It is hoped that a fix can be found for this.

(5) or other intelligent life
