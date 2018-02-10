
# What is Semantic Paint

Semantic Paint is a framework for sharing, finding, and dissagreeing about interpretations of unstructured data.  
Given a collection of data (a canvas), a semantic painting identifies certain subsets (brushstrokes) as fitting some ontology (the palette).
Semantic Paint differs from other technologies that do this (e.g. RDF) in several ways:
Write-access (and indeed, permission) is not needed to apply an ontology to a dataset.
Each brushstroke identifies its painter (at least pseudo-anonymously).
And the collaborative nature of palette-building provides cues about whether that painter should be trusted.

Semantic Paint is also a concensus app



# Why do we need it?

Something really cool was supposed to have happened by now.
It was going to be called "The Semantic Web."
The idea was that whenever we published something human friendly, like "We will be closed on Monday" we would also publish something machine friendly, like `{ BusinessHours : { '2/12/2017' :  [] } }`
If it had worked, you'd be able to do searches like:  "Give me a list of all restaurants in Denver that serve mac 'n cheese and are open later than 9:00 PM"
It didn't work.


The problematic assumption behind this idea was that for any given blob of data there is a correct interpretation, and that humans can be trusted to find it.




Previous attempts to develop the semantic web have failed because they have assumed that ontologies can be applied to data in ways that people more or less can agree on.



Here are some desires that motivated its creation:


- I want to annotate the content of math textbooks in a way that lets me later query those annotations to expose the argumentative structure of the proofs they contain.

- If I download a .doc .txt and .pdf of the same book, I want software that can identify the common data so that it does not need to be downloaded three times.

- If I comment on a sentence in that book, I want to be able to view and edit the comment without thinking about the format.

- I want to stop building systems that recognize ads so they can be blocked, and start building systems that recognize content so it can be made available cleanly.

- I want systems for managing trust that have more than one axis--like how I might trust you with my wallet, but not with a water baloon.

- I want there to be an index of common misconceptions, and an a service that notifies me when I type one.

- I want to use cryptography to prevent ideas from being misrepresented by people who either oppose them or don't understand them.

- I want to pay a few dollars every month and have it go (without middlemen) to a community of specialists who take the time to ...

  - identify javascript with non-obvious intentions and maintain a browser plugin that disables it

  - annotate online discourse in a way that helps me tell the difference between a good argument poorly made and a bad argument
  - track word usage in the wild such that I can query two near-synonyms and get a (long, curated) list of usage examples which specifies how they differ.

- I want a quantitative measure of policy complexity, which I will use to propose legislation that would ensure that the tax code never gets so complex that a typical human can't understand it all with a few weeks of study.

- I want to write a society-simulator and a compiler for legalese.  Then I want to use computational techniques to assist government in weeding out bad laws and designing/evolving good one. 

- I want to identify subsets of discourse that have identical linguistic structures, but use different words.  Then I want to introduce practicioners of either field to each other.

- I want to create a digital copy of Diophantus's Arithmetica whose margin is not only big enough to contain the proof of Fermat's last theorem, but can actually contain every published mathematical work that it inspired (and they too can contain the work based on them) so that Fermat and Wiles appear as footnotes on Diophantus.  Then I want to press some hotkey which reorganizes the whole shebang so that Fermat and Diophantus appear as footnotes on Wiles.  Then I want to reorganize the works of David Foster Wallace into this format, so his fiction can be read without the need to acknowledge that yes--you're still in a footnote.

- I think that consensus technologies (like the blockchain) will change the world in a positive way, but that implementing distributed ledgers to support token exchange (e.g. Bitcoin et al) is insufficiently imaginative.  I want to build something imaginative.

- I believe that the human concept of value is non-archimedean, and that our monetary practices usually assume otherwise.  To prove this to myself, I want to create something of value that cannot be sold.
