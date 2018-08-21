
# The Semantic Paint Manifesto

## What is Semantic Paint

Semantic Paint is a framework for sharing, finding, and dissagreeing about interpretations of unstructured data.
Given a collection of data (a *canvas*), a semantic painting identifies certain subsets (*brushstrokes*) as fitting some ontology (the *palette*).
Semantic Paint differs from other technologies that do this (e.g. [RDF](https://www.w3.org/RDF/)) in several ways:

- Write-access is not needed to apply an ontology (i.e. an object model) to a dataset, the *brushstrokes* are stored separately and reattached by a *frame* at viewtime.
- Each *brushstroke* identifies its painter (pseudo-anonymously), so the often implict: "according to whom?" is answered explicitly.
- The collaborative nature of palette-building provides cues about trustworthyness.

Semantic Paint is also a distributed index into the Merkle forest (i.e the set of all Merkle trees (and DAG's)).
Anything that can be hashed, can be *painted* on.

Consider this sentence:
> Old windows are thicker at the bottom because the glass has flowed downward since their installation.

Its MD5 hash is 96c85100dd71a9cdb4ebd06c173ba3b4.
It is also a common [misconception](https://engineering.mit.edu/engage/ask-an-engineer/how-does-glass-change-over-time/).
Suppose I painted that sentence in the semantic *color* "misconception" in my palette "belief types".

The association between the hash and the sentence is a relationship in the Merkle forest.
The association between the *color* and the hash is a relationship in semantic paint.
If you view the sentence through a properly configred *frame* then you will see that I think it is a misconception.
Whether you ought to configure your *frame* to include my palletes is up to you.

On the surface, this looks a bit like Genius Web Annotator.
However, Genius attaches its annotations to a data's location--not the data itself.
This means that if somebody retypes the sentence elsewhere, Genius will not reidentify it as somthing that I think is a misconception--but since the sentence will still hash to 96c85100dd71a9cdb4ebd06c173ba3b4, Semantic Paint will  be able to reidentify it[1].

[1] If your reaction to this is: "But how will the frame know what to hash?"  Then you're onto one of the hard problems of semantic paint: *canvas* identification and *brushstroke* targeting.  Before we can identify a sentence as a common misconception, we need to know that the bits inolved can be thought of as a sentence at all.  The extent to which this will be handled by machine learning, algorithmic code, and/or humans in the loop is not yet known.  Palettes that solve this problem (*primers*) will have to be among the first developed, and the most stable. *Painting* on a primer will be much easier for the painter than painting the data directly because they can work with paragraphs, phrases, and sentences instead of individual bits.

Lastly, Semantic paint is a platform for trust discovery.
You can paint on anything in any color--and if people have their *frames* configured to trust you, they'll see your paint.
However, most people probably don't care to maintain yet another social network.
It will be simpler for these people to configure their frames to trust community maintained *palettes*.
Whether they see your *paint* will depend on whether that community trusts you as a *painter*.

In the real world there are many kinds of trust.
For example, I might trust you with my wallet, but not with a water baloon.
Or I might trust that we agree about what makes a good beer.
This is the kind of trust relationship that Semantic Paint uses: "X trusts Y in the domain Z".

Recall that a palette is a particular way to look at raw data and derive something meaningful.
A sufficiently complex palette may represent a world view.
Humans often attempt to impose their world views on each other.
Maybe this is unfortunate, but whatever the case it is not a problem that semantic paint attempts solve--welcome to being a human in an ontologically messy world.
Instead, semantic paint makes the nature of worldview-conflict explicit so that humans are better equipped to reason about it.

Among *viewers*, the idea is that if we both subscribe to the same worldview, we are more likely to be able to find common ground in that domain.
And even if we don't, as long as we understand each other's worldview, we still might be able to find ways to cooperate.

If two *viewers* decide to share their *frame* settings with each other, then they can easily get answers to questions like:
 - Do we trust *any* of the same palettes or painters?  Which ones?
 - What does the world look like if I drop my frame settings for a day and adopt theirs?
 - If we each trust separate palette communities that used to be a single one, what is the brush stroke that caused the division?  Is it relevant to our conflict?

Among painters of the same *palette* the situation is a bit different.
Two kinds of brushstrokes can be associated with a pallete:
A *defining* brushstroke is authoritative--only the pallete maintainer (and those she trusts explicitly) can add them to the palette; these brushstrokes are correct by definition.
Alternatively, to place *regular* brushstroke of some *color* on a *canvas* is to say that the indicated subset of that canvas is the same kind of thing that is indicated by the defining *brushstrokes* in that *color*.
(This is analagous to supervised learning--certain exemplar situations are used to train a neural network, and the expectation is that the network will later be able to identify similar situations.
If the community is curating training data for a neural network that is the heart of their palette, then the set of defining brushstrokes may need to be quite large.)

The community builds trust by recognizing that its members consistently make decisions that the palette maintainer would have made.
The particulars of how trust works in a community is up to that community (they can codify it in the palette), but the idea is that painter A has reason to trust painter B if B has a track record of making the same decisions that A would have made.
So if I paint a hyperlink in the color "entrypoint" on a palette called "scam", and then you run across that brushstroke and agree that the hyperlink is the entrypoint to a scam, then you have a small reason to trust that I know how to identify a scam--especially once you look at my track record and find that I rarely identify things that later turn out to *not* be scams.
This is implicit painter trust: is a measure of how well a painter "gets it" for some palette.

Although widespread consensus is a likely goal of a palette maintainer, the protocol also supports dissent.
If a painter doesn't like the direction of the palette, and doesn't care to work towards consensus, that painter can copy whatever defining brushstrokes he likes, abandon whichever ones he doesn't like, and start his own palette.
At the outset, the forked palette will not be trusted by anyone who does not trust the rogue painter--but if it is a useful way of seeing things, it may gather support.

The politics of palette maintenance are not central to the experience of *using* semantic paint.
Most users won't have to care.
To these people, Semantic Paint is just a platform that makes a new kind of app possible, like the command line or the web browser or the gaming console.
But each of these technologies came from an idea about the way humans and data should interact.
For Semantic Paint, that idea starts with a rejection of the notion that the people who make data available are necessarily the best ones to help you interpret it.

## Why make it?

The world is full of problems, and sometimes I can imagine an app that would solve one.
But before I get very far, I see another problem--and maybe it's more important to solve that one.
After years of this I am left with several lifetime's worth of apps to write and one major insight:
If they were somehow magically finished, they would all work with data in the same way.

So instead of writing these apps sequentially, I'm writing a platform that would make each of them easier to achieve.
Here, in no particular order, is a list of apps and other personal desires that Semantic Paint may enable:

- I want to annotate the content of math textbooks in a way that lets me later apply graph theory and topology to the argumentative structure of the proofs they contain.

- When I download a .txt, a .mobi and .pdf of the same book, I want to use software that identifies the data common to each so that it does not need to be downloaded three times, even if each are downloaded several days apart.

- If I comment on a sentence in that book, I want to be able to view the same comment in other copies of that book regardless of format.

- I want to be able to point a mobile camera at a sentence in my hard copy of a book and see the annotations that you put in the kindle version of that book.

- I want us to stop building systems that recognize ads so they can be blocked, and start building systems that recognize content so it can be linked-to and provided more efficiently.

- If I decide to use ad supported services, I want to be able to partition my monthly internet usage so that I can send each advertizer a bill for the bandwidth that they consumed on my account.

- I want there to be an index of common misconceptions, and an a service that notifies me when I type one.

- I want to partipate in gathering and curating training data for open source neural networks that are capable of identifiying 100 different ways to express the same common misconception.

- I want to identify 100 different ways to say any particular thing, and then use my choices from among those 100 to encode a second, steganographically deniable, message.

- If people wind up in court for allegedly hosting a part of a censored file, I want them to be able to summon several other non-censored files that they may have been hosting parts of instead.

- When a movement forms around an idea, I want the movement to be able to instantiate a PKI specificially for that idea--even if it doesn't contain any nerds.

- When people speak about the direction of a social movement, I want tools for assessing whether that person is qualified to speak for the movement.

- I want to pay a few dollars every month and have it go (without middlemen) to a community of specialists who take the time to ...

  - identify javascript with non-obvious intentions and maintain a browser plugin that disables/fixes it

  - annotate online discourse in a way that helps me tell the difference between a good argument poorly made and a bad argument

  - track word usage in the wild such that I can query two near-synonyms and get a (long, curated) list of usage examples which exemplify how those two words differ.

- I want a quantitative measure of policy complexity, which I will use to propose legislation that would ensure that the tax code never gets so complex that a typical human can't understand it all with a few weeks of study.

- I want to write a society-simulator and a compiler for legalese.  Then I want to use computational techniques to assist government in weeding out bad laws and designing/evolving good ones.

- I want to identify subsets of discourse that have identical linguistic structures, but use different words; Then I want to introduce practicioners of either field to each other and show them how they've been having each other's thoughts but using different words.

- I want to create a digital copy of Diophantus's Arithmetica whose margin is not only big enough to contain the proof of Fermat's last theorem, but can actually contain every published mathematical work that it inspired (and further, their margins will contain the work based on them) so that Fermat and Wiles appear as footnotes on Diophantus.  Then I want to press some hotkey which reorganizes the whole shebang so that Fermat and Diophantus appear as footnotes on Wiles.  Then I want to reorganize the works of David Foster Wallace into this format, so his fiction can be read without the need to acknowledge that yes--you're still in a footnote.

- Because I think that consensus technologies (like the blockchain) will change the world in a positive way, but that implementing distributed ledgers to support token exchange (e.g. Bitcoin et al) is insufficiently imaginative, I want to use them build something imaginative.

- I believe that the human concept of value is non-archimedean, despite the fact that our monetary technologies (e.g. money) are usually models of some archimedean structure (e.g. rational numbers).  To prove this to myself, I want to create something of value that either could not be traded in exchange for an archemedean-backed monetary token, or would not retain its value enough to make the exchange worthwhile.

- When I quote anything in writing, I want readers to be able to click the quote and see the source; my writing medium should prompt me if the quote's source cannot be identified and I should be able to provide whatever context cues are necessary to support source finding.

- When somebody else quotes something in writing, and a source cannot be found, I want to be able to instatiate a "citation needed" discussion in a way that either the author or other readers can participate in the source hunt.

- I want the easiest way to publish a data visualization (like a plot) to be to also publish the underlying data and the code that transforms that data into the graph, so much so that anybody who does otherwise is looked upon with suspicion.

- I want students of writing to be able to provide feedback on each other's work in a way that allows their teacher to deputize students that "get it".  Also the students should be able to use the same platform to establish their own trust hierarchies that determine who among them "gets it" the most, regardless of the teacher's ideas.  The emergent merit-based trust structure should flexible enough that it is easy to write apps that facilitate community-driven collaborative growth--both in the classroom and afterwards.

I will never be able to achieve all of these goals, so here's the plan:
 1) Create a data-management framework and a set of libraries in popular computer languages that will make the apps easier to create.
 2) Pick just one and make it awesome.
 3) Hope that the wider community of thoughtful technologists will take the idea and:
  - Show me applications I haven't thought of.
  - Implement some of the ones that I have.

## The Theory of Semantic Paint

One goal of semantic paint is to be widely applicable.  Any time schema intermingles with data, I hope that semantic paint can--in principle--be used to model that relationship.  Whether it ought to be will depend on whether it is useful for that purpose.  It is difficult to be specific about something that aims to be so general--but in order to build this, I'll need to be specific.

This is why I've invented so many terms.  Ultimately I hope to develop rigorous mathematical definitions for these temrs and perhaps even prove theorems about them.  This will help me avoid dwelling in difficult concepts like "meaning" and instead allow me to focus on the nuts and bolts of how these things ought to be handled.

I guess what I'm doing is trying to describe the palette that I will later use to design semantic paint.  If I actually apply semantic paint to the resulting design, it will have to be after-the fact, since at the time of this writing, very little is implemented.  Ultimately, these notions will crystalize into class definitions.  For now, they're just a bunch of words in yet another long bulleted list, and coupled with no promises whatsoever.

- A palette must contain at least one color.

- Colors may be primitive; given the primitive color foo, a brushstroke in that color means that those bits represent 'foo-ness', or possibly 'a/the foo'.

- Colors may be composite; given the composite color "x is the bar of y until z baz's", a brushstroke in that color maps from the canvas to three sets of bits (x, y, and z).

- A palette must have a normalization function, which transforms a proto-canvas to a canvas.

- A proto-canvas is some set of bits that a user stumbled across in the wild.

- A canvas should contain all of the data that it makes sense to paint on, and nothing else.

- Multiple representations (i.e. proto-canvasses) of the same "thing" (e.g. txt and pdf versions of the same novel), should have identical canvasses--that way when a user paints on one representation, the brushstrokes can be viewed by another user who has encountered the other.

- I have used the word "representation" twice in this section: first I meant color-representation and second I mean canvas-representation.

- If a set of bits color-represent something, then semantic paint is being used to add signal to the bits so that they are more meaningful. if a string has characters values that together "represent" an account number according to some palette, that would be a color-representation because "is an account number" is something more than just the characters that comprise it.

- If a set of bits canvas-represents something, then then semantic paint is being used to remove noise from the bits so that they are easier to identify and address parts of. If a set of bits represent the LaTeX-formatted final-copy of somebody's doctoral dissertation, then that would be a canvas-representation of the dissertation, so long as the palette in use was focused on the content of the dissertation (and not the formatting).  This is because the concept of a dissertation is something less than the LaTeX convolutions necessary to represent it, and semantic paint is being used to hide the extra convolution so that components of the dissertation itself can be referenced more cleanly.

- proto-canvasses are canvas-representations of some canvas, and paintings in various palettes are color-represenations of that canvas.

- A palette must have a canvas-check function, which takes a proto-canvas and a canvas and says whether that proto-canvas canvas-represents the canvas.

- A painting is a set of brushstrokes in a single palette, all of which apply to the same canvas.  A canvas and a palette are combined to form a painting, the output is an object (probably represented as JSON or something similar).

- Paintings can serve as canvasses for other palettes, and so can subsets thereof (including individual brushstrokes).

- A palette may have a gallery, which is a way to find paintings in that palette.

- A gallery may either map from proto-canvasses to canvasses, from canvasses to paintings, or both.

- A palette must respond to a maintainer-check, which is a function that takes no paramters and returns the current user of the palette

- A user must have a set of perspectives

- A perspective is a palette together with every brushstroke a user has made in that palette.

- The brustroke list on a perspective is by default ordered by the time that that brushstroke was applied to the canvas.

- Perspective brushstrokes can be reordered by the user so that brushstrokes nearer to the front are taken to be "more important" than those at the back.  What importance means may be palette specific.



---------------------


notes for later:




A gallery is a n-tuple:
    - A pallette-identifier
    - A function from canvasses to sets of 

A proto-canvas is any array of bits which is either not known to contain a convas, or which is known to contain a canvas but has not been normalized.

A canvas is an array of bits which is the output of a palette's normalize function.


A brushstroke is a function from a canvas to a list of subsets of that canvas together with a color.

A perspective is a 3-tuple:
    - A pallete-identifier
    - A list of brushstrokes in the specified palette
        - By default this will be ordered chronologically by time of brushstroke-creation
        - Otherwise the they may be in arbritrary order
        - Either way, the earlier entries are thought of as "more fundamental" than the latter

A user is an n-tuple of the following:
    - A set of perspectives (*voices*)
    - A set of user-identifiers (*peers*)
    - A set of palette-itentifiers (*lenses*)
    - A subset of the lenses (*active lenses*)
    - A partial order over the active lenses (*active lens configuration*)
    - A function from peers to lenses (*trust domains*)
