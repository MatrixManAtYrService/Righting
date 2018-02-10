
# What is Semantic Paint

Semantic Paint is a framework for sharing, finding, and dissagreeing about interpretations of unstructured data.  
Given a collection of data (a *canvas*), a semantic painting identifies certain subsets (*brushstrokes*) as fitting some ontology (the *palette*).
Semantic Paint differs from other technologies that do this (e.g. RDF) in several ways:

- Write-access is not needed to apply an ontology to a dataset, the *brushstrokes* are stored separately and reattached by a *frame* at viewtime.
- Each *brushstroke* identifies its painter (pseudo-anonymously), so the often implict: "according to whom?" is answered explicitly.
- The collaborative nature of palette-building provides cues about whether one painter can trust another.

Semantic Paint is also a distributed index into the Merkle forest (i.e the set of all Merkle trees (and DAG's)).
Anything that can be hashed, can be *painted* on.

Consider this sentence:
> Old windows are thicker at the bottom because the glass has flowed downward since their installation.
Its MD5 hash is 96c85100dd71a9cdb4ebd06c173ba3b4.
It is also a common [misconception](https://engineering.mit.edu/engage/ask-an-engineer/how-does-glass-change-over-time/).
Suppose I painted that sentence in the semantic *color* "misconception".

The association between the hash and the sentence is a relationship in the Merkle forest.
The association between the *color* and the hash is a relationship in semantic paint (which also happens to be stored on a Merkle tree).
If you view the sentence through a properly configred *frame* then you will see that I think it is a misconception.
Whether you ought to configure your *frame* to include palletes that I work on is up to you.

On the surface, this looks a bit like Genius Web Annotator.
However, Genius attaches its annotations to a data's location--not the data itself.
This means that if somebody retypes the sentence elsewhere, Genius will not reidentify it as somthing that I think is a misconception--but since the sentence will still hash to 96c85100dd71a9cdb4ebd06c173ba3b4, Semantic Paint will [1].

[1] If your reaction to this is: "But how will the frame know what to hash?"  Then you're onto one of the hard problems of semantic paint: *canvas* identification and targeting.  Before we can identify a sentence as a common misconception, we need to know that the bits inolved can be thought of as a sentence at all.  The extent to which this will be handled by machine learning, algorithmic code, and/or humans in the loop is not yet known.  Palettes that solve this problem (*primers*) will have to be among the first developed, and the most stable. *Painting* on a primer will be much easier for the painter than painting the data directly.

Lastly, Semantic paint is a platform for trust discovery.
You can paint on anything in any color--and if people have their *frames* configured to trust you, they'll see your paint.
However, most people probably don't care to maintain yet another social network.
It will be simpler for these people will configure their frames to trust community maintained *palettes*.
Whether they see your *paint* will depend on whether that community trusts you as a *painter*.

In the real world there are many kinds of trust.
For example, I might trust you with my wallet, but not with a water baloon.
Or I might trust that we agree about what makes a good beer.
This is the kind of trust relationship that Semantic Paint uses: X trust Y in the domain Z.

Recall that a palette is a particular way to look at raw data and derive something meaningful.
In some sense, a palette encapsulates a world view.
Popular worldviews don't always get along with each other.
This is not a problem that semantic paint can solve--welcome to being a human in an ontologically messy world.

Semantic paint hopes to make the nature of worldview-conflict explicit so that the people are better equipped to reason about it.
Among *viewers*, the idea is that if we both subscribe to the same worldview, we are more likely to be able to find common ground in that domain.
And even if we don't, as long as we understand each other's worldview, we still might be able to find ways to cooperate.
It would go like this.

If two *viewers* decide to make their *frame* settings public, then they can easily get answers to questions like:
 - Do we trust *any* of the same palettes?  Which ones?
 - What does the world look like if I drop my frame settings for a day and adopt theirs?
 - If we each trust separate palette communities that used to be a single one, what is the brush stroke that caused the division?  Is it relevant to our conflict?

Among *painters* of the same *palette* the situation is a bit different.
A *brushstroke* is a decision and the *palette* and the *canvas* together form the context for that decision.
When a palette maintainer decides to accept 




# What are its goals?


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
