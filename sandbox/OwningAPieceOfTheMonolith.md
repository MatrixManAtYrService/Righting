# Owning a Piece of the Monolith
## A Decomposition Story

### Chapter One: Separating the Code

This is a story about the billing team and our server: _William_ (**W**e **I**nvestigate **L**ucritive **L**apses **I**ndependantly, **A**ccurately, and **M**onthly).
Particularly it's about the **I**ndependantly part of his name.
William shares much of his DNA with an older, larger server creatively named _Server_.
There was probably a time when Server had a reasonable set of responsibilities.
Something like this:

<img src="https://images-na.ssl-images-amazon.com/images/I/81Zi3MsS2cL._SL1500_.jpg" width=300 />

But as the business grew, so did Server and now it's more like this:

<img src="https://images-na.ssl-images-amazon.com/images/I/71FHJU17djL._SL1204_.jpg" width=500 />

William was born from the frustrations that appear when you try to work with code that has so many separate purposes.
As for us, we have two:
 1. Each month we calculate how much every merchant should be billed and how much each developer should be paid.
 2. We provide visibility into how these calculations have gone in past months, and how they will go next month.

For the first of these, our approach went like this:
Use Server to generate the monthly billing data, then do the same with William.
The idea was that the output should be identical, and that we would make changes to William until it was.
This worked fine as a guiding philosophy, but in practice it had some challenges.

For example, the billing month ends as 00:00 UTC, but the billing calculations happen several hours later.
Initially, we didn't think it would matter--once the month has ended, no changes should be relevant to that month's bill.
Once we started comparing William's output with Server's, it became clear that it actually did matter _when_ we took the snapshot that we used for this comparison.
This and similar obstacles served as repeated reminders that however well you think you know a server, replicating its I/O in a separate codebase is bound to teach you a thing or two about both the code and about the organization that created it.

Once we felt like William was ready to take over for the monthly job, we disabled it in Server and met during the wee hours of the morning on the first of the month to run billing manually.
We would use the window between 00:00 UTC and the scheduled time (about 2 AM, local time) to transfer snapshots to a local instance of Server and compare its outputs with William in production.
If they checked out, we would promote William's results, and if there was doubt, we would manually trigger Server to do the job.
It took a few tries to make the switch, but William has been calculating bills in the US since last summer, and we put him in charge of EU billing on new years day.
We still make changes in Server, but since then, they've been fewer and further between--which has made for a happier new year so far.

Recently, we've been focusing on independence from Server when it comes to our second responsibility: serving billing-related data to web and device users.
In some ways, this one is trickier, because _some_ server (preferably William) must be available to provide these data at all times (not just during scheduled timeslots, which was the case before).
In other ways it is easier because we can take ownership of this functionality in bite-sized pieces.
In our case, those pieces take the from of REST endpoints.

After we received a requirement that one of Server's billing endpoints needed to behave differently, our first take-ownership-of-an-endpoint process looked like this:

- Add an endpoint to William with the same path and the desired functionality.
- Determine the maximum historical load that the target endpoint has ever placed on Server.
- In a local environment, determine William's breaking point for the new endpoint (requests per second).
- Deploy the new endpoint to William in production, and test it with a load somewhere between Server's max, and the locally-found breaking point (I have been using [locust](https://locust.io/) for this).
- Once everything checks out, configure the load to start directing traffic to William.

This pattern shows up again and again in William's story:
First we establish parity, then once we're confident, we take control.
At least for a little while the team had to be responsible for the proper functioning of the same feature set on two servers.
As we add functionality to William the practicality of switching back to Server dwindles, but in the early days it was nice to have it as a fallback.
We think that this kind of gradual hand-off is the most comfortable way.

A few weeks ago, William went live in web-mode in the US.
We expect to take responsibility for billing web traffic in the EU soon.
We can't claim total independence from Server--there are several components that play a critical role in the billing team's mission that are still handled in Server, and some of these may never find their way over to William.
But we feel that having deployed both an independent web and batch server is a significant milestone.

<img src="https://upload.wikimedia.org/wikipedia/commons/e/ec/Water_droplet.jpg" width=500 />

Initially, it seemed, each challenge could be handled most easily with a compromise that took us back towards tight coupling with Server.
And some of those compromises have turned out to be the right thing to do.
But in cases where the functionality was central to our team's mission, we resisted Server's pull.
And now that we've achieved a certain distance, the easier-way-forward has started to favor independence.
Rather than pulling us back, the natural tensions within our code seem to be focusing us on our interfaces--on which server is responsible for what--and I think that it is a healthy focus.
William's story isn't over, but that's where chapter one ends--with the code finally relaxing and letting the separation happen.

### Chapter Two: Ripples

It is obvious that Clover's trajectory has made our code the way it is, but I believe that there is some feedback in play, and that the code has been putting its fingerprints on us too.
We are a company made mostly of engineers--we like to build things.
We build them according to the best assumptions we have at the time, because what else would you do?
Then we use them, and those assumptions are subtly reinforced, because the easiest way forward is the one that uses the tools we built.

When an assumption changes--like maybe a small server manages to escape the gravitational pull of the monolith--suddenly all sorts of things that used to just work now need to be done by hand.
The billing team has tried to make sure that it is our hands that do that work where possible, but we're discovering that as a team of developers, the idea that we might manage production servers just isn't yet baked into the Clover way of doing things.

Many of these challenges became apparent when we tried to get our server into production.
Earlier I mentioned that William has a batch mode and a web mode.
Initially this was two separate servers, addressing two separate concerns.
It made sense from a development perspective, but elsewhere in the company the idea of deploying the same code to every server had made its way into much of the deployment automation.
Adding two special-case deploys turned out to be more of a burden than we we realized.
The compromise was to have the same artifact deployed to both the web and batch infrastructure, and then to add endpoints which would allow my team to toggle the server's mode after the fact.

Another organizational challenge can be seen in the load balancer trickery I described in the previous chapter--where we directed real traffic to William only after load testing was complete.
It wouldn't have been appropriate for our team to make arbitrary real-time changes to a production load balancer.
We had someone from operations standing by to help us with those changes (thanks Josh).
But what if everyone did what we've done?
Ops has better things to do than to hold our hand because we want to mess with the load balancer.
These problems have solutions, both technical and organizational, but if we want to see them solved it's going to take time and buy-in from people outside of our team.

There are also some project management ripples that we are still watching spread.
When we notice that one of our servers in production needs attention, it quickly becomes an all-hands endeavor.
When should we stay focused on delivering features, and when should we set them down to help calm a brewing storm?
How do you account for that kind of thing when planning a sprint?
Here too, we're still finding our way; the right one will likely involve no small measure of patience and willingness to adapt.

Lastly, as the SDET most closely tied to William, I have a number of new challenges.
Today we planned the deployment of William's latest version, which addresses a change that will soon be deployed in Server.
The primary question was:

 > Should we deploy before or after Server?

Or to put it differently:

>  Are they backwards compatible with us, or do we need to be backwards compatible with them?

We tried a few version pairs and figured it out, but the manual testing time was significant enough that I want to be better prepared next time.
In the future I want to know how compatibility varies across several pairs of candidate versions.
This means making tests that take version pairs (one for William and one for Server) as parameters.
The to-do list for this breaks down as 90% environment stuff, 10% test writing.
Doing it right means aligning my plans with config management decisions being refined elsewhere in the company.

As you can see, chapter two of William's independence story isn't actually about William.
It's about the feedback effect, where we find out how splitting off a chunk of the code affects how we think, which strategies make sense, and how we communicate.
If we play our cards right, I think it will be a positive change, even if it takes more work in the interim.

This process has been teaching me that there is a certain quantum of collaboration that cannot be dispensed with.
In Server, it wasn't unheard of for "communication" between teams to mean accidentally breaking each other's code and then wondering why nobody can get a clean build.
Most of the time, this was too wide of an audience for a why-did-this-test-fail kind of conversation, but it did force us to have those conversations.
Apart from that hubbub, we code more efficiently, but it comes at a cost.
If there's a cross-team conversation that needs to happen, it's on us to make it happen.

If you have something like Server in your life, I hope William's story gives you two measures of hope, and one of caution.
Hope because once you can comprehend all of your project's responsibilities, you can be more confident that it meets them.
Hope because working in a project that is right-sized for your team is more fun; you have more opportunity to be creative, and you can see more results with less effort.
And caution because your story will also have a chapter with ripples that demand more responsibility than before the separation started; you'll need to take ownership of functionality on both sides.

As for William, the rest of his story is to be continued after the ripples settle.
