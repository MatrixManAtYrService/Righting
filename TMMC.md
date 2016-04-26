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

As another example, consider two experts in the same field, one trying to prove a theorem to the other.
In general, an effective proof is represented in TMMC as any set that contains the theorem, and that is open in the intersection of the two experts' respective theory spaces (i.e. they both accept the necessary axioms for the proof).
However, since they share a field, they likely have a set of theorems that they are both comfortable using.
Even if these theorems are not conventionally called axioms, for the task at hand, they may as well be.
This allows our experts to work in a very small platonic realm consisting of only the relevant axioms, and so long as they know who their audience is, they have a much smaller space in which to search for a proof.

The reader may have noticed that so far we have not been concerned with whether a theorem is true or not--just that it is provable from some set of axioms.
This is because we are using Tarski's notion of mathematical truth, by which a theorem is true if it is true in all models for the theory that it came from.
So in order to talk about truth, we will need to construct a second topological space, one whose open sets involve models [6].
Once this is done, we can use these models to re-establish the structure that was lost when we fixed a point in theorem space for every proof of what we probably feel should be the "same" theorem, or an "equivalent" axiom.

Model space can be thought of a kind of chart where one can look up true statements about a particular interpretation.
A point here might be something like ("Hyperbolic Plane", "No triangle has internal angle measures totaling greater than 180 degrees").
The structure necessary to communicate *why* this statement is true is taken care of in theory space, so all that is needed here is a directory of facts.
Model space has the discrete topology.

We will be interested in functions that map from a Th-open sets to a subsets of model space where every interpretation that is represented in set is a model for the Th-open set (which itself counts as a theory).
That is to say, we will be interested in pairing theory with models in such a way that our theoretical statements are true.
Because there is often more than one model for a particular theory, we will have to be careful to be sure that these explanation functions are well-defined.
Luckily, it is abnormal for mathematicians to use more than one model for the same theory at the same time, so we will just restrict the explanation functions to whichever models are relevant to a particular context, and if they are still not well defined then we must ask users of TMMC to avoid jumping between equivalent models.

We will not go into detail about how explanation functions are constructed, except to say that a mathematician is somebody who can do so.
Instead we will take it for granted that if a mathematician is confronted with a problem whose characters map to models that she is familliar with, that mathematician will begin constructing explanation functions that bridge between theory and model space--this is TMMC's way of describing mathematical thought.

Suppose our mathematician is then called upon to communicate this solution to some audience.
It is unlikely that she found her solution while working in a theorem space that traced all the way back to textbook axioms.
Much like the experts above, she probably has come up with a stripped-down platonic realm [7] for working on this problem.
If her audience is not comfortable in that realm, she will need to widen[8] her basis sets until her axioms are all familliar to her audience--or she will have to convince them to accept some of those axioms.

Finally, we shall reintroduce the structure that we gave up when we defined our theorems as having a unique proof.
Fix some platonic realm, and pick just one model for each of our basis theories.
Under the explanation functions that arise from this pairing, call two points in theory space equivalent if they map to the same point in model space.
Use this equivalence to generate a quotient space from theory space.
We will call the new space a platonic theory space, since the sort of truth that arises from a platonic realm was used to merge points that were "the same".  In order to "clean up" the axioms, we might consider a similar operation, where two axioms are considered equivalent if they are both required to prove the same points in the new quotient.

This completes our formulation of TMMC.
It lets us use topological concepts to talk about the relationships between propositions within a theory, and also between facts about a model and the theory that can explain those facts.
I was once told by a teacher that "this is in some sense the best proof of this property."
TMMC may be able to provide a more rigorous explanation of just what that sense is.
In order to see that the language of topology does not fall short in describing this domain, we will run through a few examples.

Th-open sets are theoretical structures that establish some propositions, either through the application of logic rules to axioms, or by virtue of the proposition itself being an axiom.
The limit points of a Th-open set turn out to be the points that share axiomatic dependency with the set.
There is a theorem in topology that says that the union of any subset with its limit points is a closed let.
Refer to the diagram above for an example of this.

Let all of the points pictured be the set U.
Note that {9} is a subset of U, so we expect that the set containing it and its limit points should be closed.
The smallest neighborhood containing 9 is {3,4,7,9}.
We can see that 6, 8, 10, and 11 all depend on 3 and 4--so any neighborhood of those points will meet {3,4,7,9} nontrivially.
So our closed set is U \ {1,2,5}, and we can see that {1,2,5} is open.

We can see from this that in TMMC, a closed set in theory space represents a portion of the theory that can be deleted without undermining the provability of anything outside of that set.
This indicates another way we can use TMMC.
Admittedly, what follows is a rather heavy-handed approach to mathematics because it requires the audience to accept drastic alteration to their platonic realm, but it may be a way of mutating one realm into another, which could afford new possibilities for exploration.

The strategy is to think of a theoretical structure that would be nice (perhaps you have a well understood model in mind), but doesn't quite work because there is a theorem in your way.
Use TMMC to find the closure of the blocking theorem (you would want the closure, and not just any closed set--otherwise you would be deleting more than strictly necessary) and remove the closure from your platonic realm [8].
As we saw in the example, a relatively small subset can have a relatively large closure, so one might expect the whole thing to come crashing down









(1) "Rougly," because we still need to retain enough information about an axiom so we can identify whether, and how, a logic rule can be applied to it.  Such an analysis would likely involve storing axioms in terms of parse-trees containing undefined terms and maybe some other linguistic elements.  For now, we will take it for granted that axioms can be understood, and treat them otherwise as points.

(2) There is still some ambiguity here.  Perhaps one can apply different logic rules to the same hypotheses in order to provide different proofs of what would be considered the *same* theorem under the given desceiption.  This is another point that will need to be addressed in a more detailed study involving proof grammar.

(3) This is not a paper for exploring self-reference paradoxes, so feel free to exclude from X anything about X itself, anything about TMMC, and anything about barbers.

(4) Note that we claimed earlier that we were building a space from a basis, and now here we argue that Theory Space is topological from definitions.  This is because TMMC is not complete.  I feel like the given sets do capture the feel of a basis, but they don't actually cover the space.  One can imagine cross-theory characters like a set of polygons with prime numbered sides.  Theorems could be proved about these characters that are not in either basis theory, but result from the joining of the two.  It is hoped that a fix can be found for this.

(5) or other intelligent life

(6) I ask the reader's forgiveness for instances in which I may gloss over the nuances of model theory, it is not a theory I am particularly acquainted with (yet).  Here are my working definitions: An interpretation is a collection of statements and a way to map that those statements onto a theory.  If, under that map, all of the axioms map to true statements, then the interpretation is a model for that theory.

(7) Which may work out to be a subspace topology

(8) The size of our Th-open sets is, I believe, a relevant factor in considering "how true" some statement is.  Consider these three statements: "All wibbles are wobbles," "Harry potter is a wizard," and "The speed of light is constant."  These are all true statements in some model or another, and indeed theories could be constructed for those models that would allow satisfying explanations of these facts.  Still, they seem fundamentally different.  The first example came from an IQ test, the model and associated Th-open set are too small to feel like they have any reality.  The second one comes from a work of fiction which has its own internal consistency and enough detail to feel like there's a whole world in there.  As for the third, there's a whole world in here too--the difference in this case may have more to do with where I am.  It is hoped that TMMC can provide some language to discuss these notions more precisely.

(9) In my novice understanding of Relativity, this is exactly what Einstein did.  He wanted to take as axioms that light traveled at a constant speed and in a straight line (barring reflection or refraction), but could not do so because of 
