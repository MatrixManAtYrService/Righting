# Owning a Piece of the Monolith
## A Decomposition Story

### Chapter One: Separating the Code

This is a story about the billing team and our server: _William_ (*W*e *I*nvestigate *L*ucritive *L*apses *I*ndependantly, *A*ccurately, and *M*onthly).
Particularly it's about the *I*ndependantly part of his name.

William shares much of his DNA with an older, larger server creatively named _Server_.
There was probably a time when _Server_ Had a resonable set of responsibilities.
Something like this:

![simple swiss army knife](https://images-na.ssl-images-amazon.com/images/I/81Zi3MsS2cL._SL1500_.jpg)

But as the business grew, so did _Server_ and now it's more like this:

![comedically complex swiss army knife](https://images-na.ssl-images-amazon.com/images/I/71FHJU17djL._SL1204_.jpg)

William was born from the frustrations that appear when you try to work with code that has so many separate purposes.
As for us, for the most part we just have two:
 1. Each month, calculate how much every merchant should be billed and how much each developer should be paid.
 2. Provide visibility into how these calculations have gone in past months, and will go next month.

For the first of these, we employed something we call "the strangler pattern."
We would use _Server_ to generate the monthly billing data, and then we would use _William_ to do the same.
The ideas was that the output should be identical, and that we would make changes to _William_ until it was.
This worked fine as a guiding philosphy, but in practice it had some challenges.

For example, the billing month ends as 00:00 UTC, but in order to avoid placing undue load on the system during dinner hours in the USA (where our server load is highest), we billing happens several hours later.
Ideally, it wouldn't matter--once the month has ended, no changes should be relevant to that month's bill.
Actually, this isn't strictly the case.
Once we started comparing _William_'s output with _Server_'s, it became clear that it mattered _when_ we took the database backup that we used for this comparison.
Since database backups don't happen instantaneously, it was nearly impossible to take the perfect snapshot.
We worked around this by developing tools that allowed us to confidently ignore anomalies of this sort.

Once we felt like William was ready to take over for the monthly job, we disabled the it in _Server_ and met during the wee hours of the morning on the first of the month to run billing manually.
We would use the window between 00:00 UTC and the scheduled time (about 2 AM, local time) to transfer snapshots to a local instance of _Server_ and compare its outputs with _William_ in production.
If they checked out, we would promote _William_'s results, and if there was doubt, we would manually trigger _Server_ to do the job.
It took a few tries to make the switch, but _William_ has been calculating bills in the US since last summer, and we put him in charge of EU billing on new years day.

Recently, we've been focusing on independence from _Server_ when it comes to our second responsibility: serving billing-related data to web and device users.
In some ways, this one is trickier, because _some_ server (preferably _William_) must be available to provide these data at all times (not just during scheduled timeslots, which was the case before).
In other ways it is easier because we can take ownership of this functionality in bite-sized pieces.
In our case, those pieces take the from of REST endpoints.
The take-ownership-of-an-endpoint process looked like this:

- We receive a requirement that one of _Server_'s billing endpoints needs to behave differently.
- My team adds an endpoint to _William_ with the same path and the desired functionality.
- I determine the maximum historical load that the target endpoint has ever placed on _Server_.
- In a local environment, I determine _William_'s breaking point for this endpoint (requests per second).
- We deploy the new endpoint to _William_ in production, and I test it with a load somewhere between _Server_'s max, and my locally-found breaking point (I have been using [locust](https://locust.io/) for this).
- If everything checks out, we configure the load balancer to start directing traffic for the target endpoint to _William_.

A few weeks ago, William went live in web-mode in the US (on separate servers than the batch-mode version I described earlier).
We expect to take responsibility for billing web operations in the EU soon.
We can't claim total independence from _Server_--there are several components that play a critical role in the billing team's mission that are still handled in _Server_, and some of thes may never find their way over to _William_.
But we feel that having deployed both an independent web and batch server is a significant milestone.

![a water droplet, nearly separated from a larger body]https://commons.wikimedia.org/wiki/File:Water_droplet.jpg)

Initially, it seemed, each challenge could be handled most easily with a compromize that took us back towards tight coupling with _Server_.
And some of those compromizes have turned out to be the right thing to do.
But in cases where the functionaity was central to our team's mission, we resisted _Server_'s pull.
And now that we've achieved a certain distance, the easier-way-forward has started to favor independence.
Rather than pulling us back, the natural tensions within our code seem to be focusing us on our interfaces--on which server is responsible for what--and I think that it is a healthy focus.
_William_'s story isn't over, but that's where chapter one ends--with the code finally relaxing and letting the separation happen.

### Chapter Two: Ripples

It is obvious that Clover's trajectory has made the code the way it is, but I believe that there is some feedback in play, and that the code has been putting its fingerprints on us too.
We are a company made mostly of engineers--we like to build things.
We build them according to the best assumptions we have at the time, because what else would you do?
Then we use them, and those assumptions are subtly reinforced, because the easiest way forward is the one that uses the tools we built.

When an assumption changes--like maybe a small server manages to escape the gravitational pull of the monolith--suddenly all sorts of things that used to just work now need to be done by hand.
The billing team has tried to make sure that it is our hands that do that work where possible, but we're discovering that as a team of developers, the idea that we might manage production servers just isn't yet baked into the Clover way of doing things.

Many of these challenges became apparent when we tried to get our server into production.
Earlier I mentioned that _William_ has a batch mode and a web mode.
Initially this was two separate servers, addressing two separate concerns.
It made sense from a development perspective, but elsewhere in the company the idea of deploying the same code to every server had made its way into much of the deployment automation.
Adding two special-case deploys turned out to be more of a burden than we we realized.
The compromize was to have the same artifact deployed to both the web and batch infrastructure, and then to add endpoints which would allow my team to toggle the mode after the fact.

Another organizational challenge can be seen in the load balancer trickery I described in the previous chapter--where we directed real traffic to _William_ only after prodction load testing was complete.
It wouldn't have been appropriate for our team to make arbitrary real-time changes to a production load balancer.
We had someone from operations standing by to help us with those changes (thanks Josh).
But what if everyone did what we've done?
Ops has better things to do than to hold our hand because we want to mess with the load balancer.
These problems have solutions, both technical and organizational, but if we want to see them happen it's going to take time and buy-in from people outside of our team.

There are also some project management ripples that we are still watching spread.
When we notice that one of our servers in production needs attention, it quickly becomes an all-hands endeavor.
When should we stay focused on delivering features, and when should we set them down to help calm a brewing storm?
How do you account for that kind of thing when planning a sprint?
Here too, we're still finding our way; the right one will likely involve no small measure of patience and willingness to adapt.

Lastly, as the SDET most closely tied to _William_, I have a number of new challenges.
Today we planned the deployment of _William_'s latest version, which addresses a breaking change that will soon be deployed in _Server_.
The primary question was:

 > Should we deploy before or after _Server_? (or both, with a different version each time?)

To answer this we needed to know how compatibility varied across different version combinations.
Where do you put the code for an automated test that gives you that answer?
Should I write tests that provision, configure, and connects new environments just for that test?
I have some ideas about this, but nobody wants yet another competing way to configure environments.
To do it right means aligning my plans with config management decisions being refined elsewhere in the company.

As you can see, chapter two of William's independence story isn't actually about William, and much of it hasn't happened yet.
It's about the feedback effect, where we find out how splitting off a chunk of the code affects how we think, and how we communicate.
If we play our cards right, I think it will be a positive change, even if it takes more work in the interim.

It's like how we used to communicate by accidentally breaking each other's code and then wondering why we can't get a clean build.
What _William_ has taught me is that, clumsy as it may have been, that communication served a purpose (sometimes).
Although we can remove the frustration of being blocked when others break our build, we can't forgo the ensuing coordination for long.
Still, I would like to change the texture of that communication so that we have a clearer picture of what our servers and services expect, and what is expected of them.
That is, we should make them right-sized so each team can take more ownership for the behavior it is responsible for.
By doing this, I think we'll ultimately get software that is more reliable, more flexible, and more fun to build.

As for _William_'s story, it's to be continued.
