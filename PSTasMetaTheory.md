In this paper I propose a theory that I expect might be useful for evaluating other theories (as well as the models they describe). The theory is called TMMC (a Topological Metatheory for Mathematical Criticism). Whether mathematics needs such a tool is left as an open question for now.  Once it has been developed slightly, I will circle back and discuss why it might be worth finishing.  As an example of how TMMC might be used, consider a theory (like real analysis) and a model for that theory (like the real numbers).  Properly applied, TMMC will allow us to define metrics for how well the theory fits the model, and study properties of the theory-model-pair.

In order for TMMC to be applicable to a theory-model-pair, that theory-model-pair must itself be a model for TMMC.  In order to achieve this, we must be able to conceive of each component of the pair as topological space.  We can show this generally by considering a large space containing some (or all) theories, as well as a large space containg models.  The applicability of TMMC to a particular theory-model-pair in these spaces then comes "for free" because we can use the subspace topology on either side.

We shall start with theory space (Th).  Let T be a set of propositions and let h be a topology on T where each open set (P) has this property: elements of P are either themselves axioms, or can be proven from other axioms in P.  So any h-open set either consists of all axioms, or it contains, through the application of logic rules to axioms, some nugget of reasoning.  As it stands, Th is the discrete topology, since you could show that any set of propositions is open by just taking every proposition to be an axiom.  We shall soon add a restriction about when a proposition can be taken as an axiom that will make Th topologically more interesting, but first we need to answer this:  When are two propositions equal?

Once a theorem is proved in mathematics, we generally do not refer to it by its proof, but only by some string of symbols that we understand *could* be proved.  This allows us to simplify things by taking that string of symbols as an axiom, and only bothering to expand it into a proof if pressed to do so by a skeptic.  This potential for expansion represents an oportunity to transform a small Th-open set with a couple dubious axioms into a larger Th-open set with different axioms that are (hopefully) more agreeable to the audience.  We shall call this process *proof-substitution*(10). It is a facet of argumentation that we wish to preserve, and in order to do so we cannot have any ambiguity about *which* proof a given string of symbols ought to be expanded to.  Because of this, we shall take two propositions to be equal when they have the same proof.

It may seem that we have swept something under the rug here, because now we need to know what a proof is.  But notice that our open sets here provide a very specific context in which to find a proof for a theorem.  They provide a neighboring set of propositions and a guarantee (i.e. provability) that the chosen proposition can be traced back to axioms.  That is to say, our open sets are themselves proofs, so the proof to consider when determining proposition equality is (at least for starters) the one that is indicated in the open set that contains the point.  A diagram may be helpful here.

[ Proposition Graph goes here]

Let A = { 8, 9, 10 }
Let B = { 1, 8, 9, 10, 11 }

First note that if you take 8 and 9 as axioms then 10 is provable, and if you take 1, 8, and 9 as axioms then both 10 and 11 are provable, so A and B are Th-open sets.  So far, we have described proposition equality in terms of the neighborhoods of those propositions.  The reader may be at this point concerned about circularity: If a point's identity is defined based on what set it is in, can you still define a set based on what points are in it?  Well, on the surface, probably not, but this is where the process of proof-substitution discussed previously comes in.  As an example, let us prove that proposition 10 is indeed equal to itself.

Since 10 is in A, we take 8 and 9 as axioms.  Then we expand A by substituting proofs of 8 and 9.  8 and 9 are no longer required to be axioms, and our new set is {6,7,4,8,9,10}, with {6,7,4} as axioms.  Expanding further upon 6 and 7 adds 2,3,4 to our set, and they are they are now the only axioms necessary to keep the set open.  Repeating this process for 10 in set B results in the same set, except that it has 1 and 11 in it as well.  We can exclude them, since they are not necessary to prove 10.  In either case, we end up with the set {2,3,4,6,7,8,9,10} where {2,3,4} are axioms.  To be totally rigorous we would also need to show that the proof structure underlying this set is also equivalent for A and B, but we will defer this until TMMC is completed.  For now we will just take as an axiom that a proposition is some thing for which a unique proof can be found, and further that two proofs are equal if they rely on the same axioms in the same way (i.e. they apply the same logic rules in the same order).

Conventionally, the word "axiom" is used to indicate the starting points of big open sets in Th, like whole branches of mathematics.  When one is examining a smaller thing, like a proof, "hypothesis" is typically used.  Topology being a dicipline that does not care about size, we will use "axiom" for both of these.  The conventional distinction still has meaning here, however.  If you look at theory space as a directed graph (where the nodes are propositions and the edges can be bundled such that each bundle represents the application of a logic rule) the hypothesis-axioms are nodes with both incoming and outgoing edges.  Conventional axioms, then, have only outgoing edges.  If an open set has for axioms only the conventional sort, then it is a basis set for theory space.

To see this, note that we have defined points in theory space in such a way that the space must contain axioms that prove the proposition.  So we can find basis sets that cover any point in Th. Also, given any two basis sets with a nonempty intersection, we can find another basis set that contains that intersection.  To do so, simply take the intersection of the axioms for the original bases, and consider its interior.  For example, if B1 






[1] That is to say, "You and I."  You, because in order for us to communicate at all we must first come to terms with each other--that is, agree upon some axioms, and I because these these are the axioms I have chosen for what I want to communicate.  It is common to adopt the "we" voice while making a mathematical argument.  I must admit there is a possibility that this convention came about while imitating proofs that appear in papers with multiple authors, but until corrected I will be sticking with my version.

[2] For which it is a model, but only vacuously.

[3] You might say that the theory generated the model, so that any new properties found in the reals are as much constructed as they are discovered.

[4] Notice that this is exactly the opposite of what happened when we paired S with the six-persion model, which had extra facts left over, even after the fullest application of S.

[5] On the other hand, this could be exactly what Leibniz or Newton (probably newton) had had in mind for calculus.  But, if that is the case then I think it comes not out of necessity for their work, but out of some kind of spiritual leaning regarding ineffability that is probably no longer in vogue, but that is still kicking around in our mathematics.

[6] At this point, it may be natural to wonder what an evenly-powered theory-model-pair looks like.  Each proposition in the theory would match up perfectly to a fact about the model, and each fact about the model would have a corresponding proof in the theory.  In this case there is no apparent reason to prefer reasoning in the theory to reasoning in the model, as they may as well be the same thing--so why bother having two?  In the language of TMMC we would say that the explanation function between them is a homeomorphism.

[7] Another question that arises here is: What if a theory overpowers a model for some cases, but is underpowered in the model for others?  It is hoped that TMMC can identify these areas, at which point it would be up to the critic to decide whether the particular distribution of power was appropriate.

[8] It is hoped that TMMC can one day be extended beyond mathematical theories as a a sort of semantic analytics tool.  However, we are already casting our net pretty wide here, so at least for the present we will restrict our focus to mathematics.

[9] It is tempting to call T the set of *all* propositions, but until we are clear on just what a proposition is, we can't be sure that this is not paradoxical.  This shall be discussed soon, but for now feel free to exclude from T any propositions about T itself, anything having to do with barbers, and any other propositions you feel might be troubling.

[10] If TMMC grows up to be the kind of theory I have in mind, an better word might be *communication*
