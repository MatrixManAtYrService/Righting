I have heared it said that we could have built a different mathematics than we did.
Suppose so, how should we feel about the mathematics that we have?
It has grown with us after all--and we with it--for a long time.
Maybe we're idealy suited to each other.
On the other hand, our mathematics is the result of creative choices by smart, but fallible, people.
It might have some rough spots.

If math is an art, then perhaps like other arts it could have a healthy relationship with criticism.
Or, if math is a tool, then maybe we could use a method for assessing how well a particular theory fits the application--and a guide for the constructing an even better fit.
However you prefer to look at it, what is called for is a theory that lets us study the properties of other mathematical theories and the way they those theories apply to the models that they are paired with.
In this paper I propose such a theory, it is called a Topological Metatheory for Mathematical Criticism, or TMMC for short.

For our purposes here, a theory is a set of theorems all of which can be proven from some set of axioms.
These theories could be something as small as a particular proof, or as large as a whole branch of mathematics.
TMMC makes use of theories like this as basis sets for a topological space.
Before we define these sets and argue that this really is a basis, we must be sure that these creatures are well behaved enough to be treated as sets.

It is generally accepted that the same theorem can have more than one proof, and there is some sense in which a given axiom can have numerous equivalent statements.
This equivalence is necessary to understand the structure of mathematics, and TMMC does make use of it, but not yet.
The strategy here is to first construct a topological space where proof and axiom equivalence is ignored, and then to reintroduce that equivalence and use it to form a quotient space which will assume the structure that was at first neglected.
For our first construction, we will ignore the content of our axioms and treat them as roughly atomic[1].
We will also treat two theorems as equal when they have the same proof.

This shifts the concern to whether we can identify when two proofs are equal.
It will be conventient to think of the points in our theories as nodes on a directed tree.
In this tree the directed edges mean "proved in terms of."
Because of this, our axioms will have no incoming edges, but our theorems will.
If a theorem has an outgoing edge, then we know that the theory requires it to prove yet another theorem.
With this structure in mind, any theorem can be traced backwards to its axioms, and the resulting subgraph can be thought of as a proof for that theorem [2].
If this process yields the same subgraph for two points, then those points have the same proof, and are therefore equal.

[diagram here]

Referring to the diagram above, we can use this process to see that theorem 8 is equal to itself by tracing its proof dependency backwards to the axioms.
This yields the tree containing {2,3,6,7,8} which is indeed equal to itself.
Also notice that the proof for theorem 9 requires axiom 4, which is not required for theorem 8, so we find that--as expected, theorems 8 and 9 are not equal.

Before we build our topological space, we will need one additional set: C, the character set.
Characters are entities to which theorems apply, but whose existence is not asserted by a theory on its own.
If I were to pose a problem to you that started with "Let n be a natural number," the first two words would indicate that the proof I seek contains an element from C, and the last two indicate that, if this proof is to be an effective communication, the natural numbers should be a model for one of the theories in our basis.

Consider a set of theories, together with C.
Let T be the set of all propositions[3] that are provable from the axioms among our basis theories, plus any cast of characters from C.
Let h be a collection of subsets of T such that each element of h can be proven from axioms (and characters) in the proposed basis.
We call Th theory space, and claim that it is toplological [4].
Note that T is open by construction, and that the empty set is open vacuously.
Since every open set contains a path back to the axioms for every point, no union of open sets will ever orphan a theorem, and will therefore remain open.
As for intersections, note that if a theorem is in the intersection of two open sets, then all of the theorems necessary to prove it must also be in that intersection.
To see an example, refer to the diagram above and consider {2,3,6,7,8} and {3,4,7,9}.
The intersection here is {3,7}, which is indeed an open set.

Notice that this construction is contingent upon the selection of basis theories.
I like to call these theories (together with any models for them), a platonic realm.
Examples of platonic realms include conventional mathematics as me know it, as well as any alternative mathematics that we[5] might have come up with instead.
This construcion makes sense at smaller scales too.
While learning, or teaching, a subject, a mathematician may need to limit the scope of their available theorems in order to demonstrate an acceptable proof.
The question, "which theorems can we use in the homework?" when framed in the language of TMMC, asks "What is in our platonic realm?"

As another example, consider two experts in the same field, one proving theorem to the other.
In general, an effective proof is represented in TMMC as any set that both contains the theorem and is open in the intersection of the two experts' respective theory spaces (i.e. they both accept the necessary axioms for the proof).
However, since they share a field, they likely have a set of theorems that they are both comfortable using.
Even if these theorems are not conventionally called axioms, for the task at hand, they may as well be.
This allows our experts to work in a very small platonic realm consisting of only the relevant "axioms", and so long as they know who their audience is, the proof they build can stay somewhat small.

The reader may have noticed that so far we have not been concerned with whether a theorem is true or not--just that it is provable from some set of axioms.
This is because we are using Tarski's notion of mathematical truth, by which a theorem is true onlif it is true according to all models for the theory that it came from.
So in order to talk about truth, we will need to construct a second topological space whose open sets involve models [6].
Once this is done, we can use these models to re-establish the structure that was lost when we defined two proofs of the same theorem as "separate theorems".

Model space can be thought of a kind of chart where one can look up true statements about a particular interpretation.
A point here might be something like ("Hyperbolic Plane", "No triangle has internal angle measures totaling greater than 180 degrees").
The structure necessary to communicate *why* this statement is true is taken care of in theory space, so all that is needed here is a directory of facts.
Model space has the discrete topology.

We will be interested in functions that map from a Th-open set to a subsets of model space where every interpretation that is represented in set is a model for the Th-open set (which itself counts as a theory).
That is to say, we will be interested in pairing theory with models in such a way that our theoretical statements are true.
Because there is often more than one model for a particular theory, we will have to be careful to be sure that these explanation functions are well-defined.
Luckily, it is abnormal for mathematicians to use more than one model for the same theory at the same time, so we will just restrict the explanation functions to whichever models are relevant to a particular context, and if they are still not well defined then we must ask users of TMMC to avoid jumping between equivalent models.

We will not go into detail about how explanation functions are constructed, except to say that a mathematician is somebody who can do so.
Instead we will take it for granted that if a mathematician is confronted with a problem whose characters live in models that she is familliar with, she can begin constructing explanation functions that bridge between theory and model space--this is TMMC's way of describing mathematical thought.

Suppose our mathematician is then called upon to communicate this solution to some audience.
It is unlikely that she found her solution while working in a theorem space that traced all the way back to textbook axioms.
Much like the experts above, she probably has come up with a stripped-down platonic realm [7] for working on this problem.
If her audience is not comfortable in that realm, she will need to widen[8] her basis sets until her axioms are all familliar to her audience--or she will have to convince them to accept some of those axioms.

Finally, we shall reintroduce the structure that we gave up when we defined our theorems as having a unique proof.
Fix some platonic realm, and pick just one model for each of our basis theories.
Under the explanation functions that arise from this pairing, call two points in the resulting theory space equivalent if they map to the same point in model space.
Use this equivalence to generate a quotient space from theory space.
Another way of thinking of this is that we are merging points so that the explanation function is one-to-one.
We will call the new space a platonic theory space, since the sort of truth that arises when a platonic realm is used to merge points that feel "the same".
In order to "clean up" the axioms, we might consider a similar operation, where two axioms are considered equivalent if they are both required to prove the same points in the new quotient.

This completes our formulation of TMMC.
It lets us use topological concepts to talk about the relationships between propositions within a theory, and also between facts about a model and the theory that can explain those facts.
I was once told by a teacher, "this is in some sense the best proof of this property."
TMMC may be able to provide a more rigorous explanation of just what that "sense" is.
In order to see that the language of topology does not fall short in describing this domain, we will run through a few examples.

Th-open sets are theoretical structures that establish some propositions, either through the application of logic rules to axioms, or by virtue of the proposition itself being an axiom.
The limit points of a Th-open set turn out to be the points that share axiomatic dependency with the set.
There is a theorem in topology that says that the union of any subset with its limit points is a closed let.
Refer to the diagram above for the following example.

Call the set of all nodes pictured U.
Note that {9} is a subset of U, so we expect that the set containing it and its limit points should be closed.
The smallest neighborhood containing 9 is {3,4,7,9}.
We can see that 6, 8, 10, and 11 all depend on 3 and 4--so any neighborhood of those points will meet {3,4,7,9} nontrivially.
So then our closed set is U \ {1,2,5}, and we can easily verify that {1,2,5} is open, so the theorem holds.

In TMMC, a closed set in theory space represents a portion of the theory that can be deleted without undermining the provability of anything outside of that set.
This indicates another way we can use TMMC.
Admittedly, what follows is a rather heavy-handed approach to mathematics because it requires the audience to accept drastic alteration to their platonic realm, but it may be a way of mutating one realm into another, which could afford new possibilities for exploration.

The strategy is to think of a theoretical structure that would be nice (perhaps you have a well understood model in mind), but doesn't quite work because there is a theorem in your way.
Use TMMC to find the closure of the blocking theorem (you would want the closure, and not just any closed set--otherwise you would be deleting more than strictly necessary) and remove the closure from your platonic realm [9].
As we saw in the example, a small subset can have a large closure, so one might expect the whole thing to come crashing down, but remember that the more natural space to work in is platonic theory space, where each point is in some sense "supported" by a number of points back in flat theory space.
There is a possibility that deleting large swaths of flat theory space may have a relatively small impact on platonic theory space, as long as the the theorems involved have alternative proofs that exist outside of the deletion.

Having discussed limit points and closures, perhaps "interior" is the next topological term we should explore.
To take the interior of a Th-open set is to ask what else can be proved from that place.
This is typically a large set, since standard logic rules allow one start with a propostion A and then prove A & A, and then prove A & A & A, and so on.
It might be more interesting to ask which theorems are not in an interior.
This lines up with the concept of logical independence[10].
So when Cohen showed that Cantor's continuum hypothesis was independent from ZFC, his result could be translated into TMMC by saying that the continuum hypothesis is not in the interior of the set containing ZFC's axioms.

Another metamathematical concept that we can talk about in TMMC's terms is completeness.
If you pick a set in model space that represents all known facts about an interpretation, and also pick a Th-open set in theory space for which the interpretation is a model, then that Th-open set is complete if every fact about the model can be proved in the subset of model space.
Or to put it another way, a theory is complete in a model if the explanation map between them is continuous.

Tarski once proved that his formulation of elementary geometry was complete.
In TMMC this means that the explanation function is continuous, and since model space has the discrete topology, the explanation function is also open.
Further, if you use a platonic theorem space then you know that the explantion function is one-to-one.
As long as the model in question is onto[11], then we can conclude that the explanation function is a homeomorphism.

Hilbert's program, it would seem, was motivated out of a belief that this homeomorphism held generally.
But as it turns out, elementary geometry is a special case here--some of our favorit models do not have this property.
This is why the program had to change track when people began to accept Godel's incompleteness theorem, which tells us that there are no continuous explanation functions onto a model for the natural numbers.

In a certain sense, TMMC is a response to the limitations pointed out by Godel.
If I must accept that the foundations of mathematics cannot be secured in logic, then I propose the following alternative:
We should build wings for it and fly it around.

Beyond these abstract desires, there is also the possibility of some more concrete applications of the theory.
One of these lies in our pedagogical methods.
At the heart of pure mathematics is argumentation, which is typically expressed in a symbolic or auditory way.
After some practice, one learns to visualize the structure of an argument--and it really feels like it has some sort of shape--but nobody ever tries to draw one.
However, topology is a field of many diagrams.
If the data for the argumentative structure of textbook proofs were available, perhaps we could find visualizations to help visualize the "shape" of the argument they're working with.
This, and other concepts from TMMC could form a proof assitant that may be of use in the classroom.

Secondly, again supposing this data were available, there may be some opportunities in math publishing.
LaTeX, our current standard for math publication, is a fine language for symbolic representation, but it is not easily queryable.
If there were a way to do searches like, "find all known contradiction proofs of such-and-such result," it would be a powerful thing.
Also, theorem-level granularity could allow new business models that ultimately lead towards for fundint for mathematics in general.

Perhaps a robot somewhere in the world is trying to solve a problem.
Somewhere else, beforehand, a Mathematician was playing around with a theory that solves that problem.
With the appropriate infrastructure, and the ability to delve into the theoretical structure of mathematics, perhaps the robot can query some web site for the tools it needs to solve the problem at hand.
Once found, the robot solves its problem, and the mathematician gets a small deposit in their account for providing the necessary framework.
Amazon does computing by the sip, and Spotify pays musicians per-played-song, perhaps TMMC could allow for mathematics on tap to be a viable business model.

Finally, there is an idea called "linked data" or "the semantic web" that has been around for some time.
It was supposed to change the world in a big way, but many feel that it has fallen short of its promise.
The idea was that instead of linking documents together so that humans could read them  (which is what happens in the traditional web), we could provide enough semantic metadata that machines could follow the links directly.

Everything was supposed to be stored in triples (subject, verb, object) and we were supposed to be able to solve some big problems with it.
Oppinions are mixed about why we have yet to see the glories of a semantic-aware web browser, but I believe that the big shortcomming was the expectation that each triple be true in some absolute sense.
People don't get along well enough to collaborate on a project like that.

I think that what is needed to "fix" the semantic web is a fourth item which would answer "according to whom/what?".
Or, to put it in the language TMMC, "in which platonic realm?".
By providing this additional scope and structure to the sea of triples that was supposed to form the semantic web, I think we could see a few more of its promised benefits.
If the TMMC practice of finding the intersection of two platonic realms as a context for communication holds water mathematically, then perhaps it can be generalized to serve a similar purpose on the semantic web.

In summary, I have proposed a theory which encapsulates metamathematical concepts in the language of topology.
It does this by encapsulating formal systems in a topological space, and mathematical models in another topological space.
This opens the door for the use of topological concepts to analyze the way these two spaces interact, which is central to the daily activities of mathematicians everywhere.
If we could have built a different mathematics than we did, then we are currently building the next generation's mathematics.
Maybe this theory, or one like it, can help ensure that we build the one that serves them best.













(1) "Rougly," because we still need to retain enough information about an axiom so we can identify whether, and how, a logic rule can be applied to it.  Such an analysis would likely involve storing axioms in terms of parse-trees containing undefined terms and maybe some other linguistic elements.  For now, we will take it for granted that axioms can be understood, and treat them otherwise as points.

(2) There is still some ambiguity here.  Perhaps one can apply different logic rules to the same hypotheses in order to provide different proofs of what would be considered the *same* theorem under the given desceiption.  This is another point that will need to be addressed in a more detailed study involving proof grammar.

(3) This is not a paper for exploring self-reference paradoxes, so feel free to exclude from X anything about X itself, anything about TMMC, and anything about barbers.

(4) Note that we claimed earlier that we were building a space from a basis, and now here we argue that Theory Space is topological from definitions.  This is because TMMC is not complete.  I feel like the given sets do capture the feel of a basis, but they don't actually cover the space.  One can imagine cross-theory characters like a set of polygons with prime numbered sides.  Theorems could be proved about these characters that are not in either basis theory, but result from the joining of the two.  It is hoped that a fix can be found for this.

(5) or other intelligent life

(6) I ask the reader's forgiveness for instances in which I may gloss over the nuances of model theory, it is not a theory I am particularly acquainted with (yet).  Here are my working definitions: An interpretation is a collection of statements and a way to map that those statements onto a theory.  If, under that map, all of the axioms map to true statements, then the interpretation is a model for that theory.

(7) Which may work out to be a subspace topology

(8) The size of our Th-open sets is, I believe, a relevant factor in considering "how true" some statement is.  Consider these three statements: "All wibbles are wobbles," "Harry potter is a wizard," and "The speed of light is constant."  These are all true statements in some model or another, and indeed theories could be constructed for those models that would allow satisfying explanations of these facts.  Still, they seem fundamentally different.  The first example came from an IQ test, the model and associated Th-open set are too small to feel like they have any reality.  The second one comes from a work of fiction which has its own internal consistency and enough detail to feel like there's a whole world in there.  As for the third, there's a whole world in here too--the difference in this case may have more to do with where I am.  It is hoped that TMMC can provide some language to discuss these notions more precisely.

(9) In my novice understanding of Relativity, this is exactly what Einstein did.  He wanted to take as axioms that light traveled at a constant speed and in a straight line in a vacuum, but could not do so because his platonic realm included theorems that contradict those axioms.  So, he set aside the troublesome theorems, took his axioms anyway, and built a new theory in the space created by the deletion.  Or, to take our language out of TMMC, he reinterpreted our notions of time and space around accepted properties of light.

(10) If TMMC is completed, it would be an interesting exercise to prove that this method of showing independence is equivalent to the method where one finds two models in which the target property is both true and false.

(11) In this example, it is not clear just how big or small the model in question is.  This may be an indication that model space needs a bit more structure.
