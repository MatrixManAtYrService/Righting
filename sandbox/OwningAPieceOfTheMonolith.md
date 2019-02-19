# Owning a Piece of the Monolith
## A Decomposition Story

This is a story about the billing team and our server: _William_ (*W*e *I*nvestigate *L*ucritive *L*apses *I*ndependantly, *A*ccurately, and *M*onthly).
Particularly it's about the *I*ndependantly part of his name.

William shares much of his dna with an older, larger server creatively named _Server_.
There was probably a time wher *Server* Had a resonable set of responsibilities.
Something like this:

![simple swiss army knife](https://images-na.ssl-images-amazon.com/images/I/81Zi3MsS2cL._SL1500_.jpg)

But as the business grew, so did _Server_ and now it's more like this:

![comedically complex swiss army knife](https://images-na.ssl-images-amazon.com/images/I/71FHJU17djL._SL1204_.jpg)

William was born from the frustrations that appear when you try to work with code that has so many separate purposes.

Our team primarly has two responsibilities:
 1. Each month, calculate how much each merchant should be billed and how much each developer should be paid.
 2. Provide visibility into how these calculations have gone in past months, and will go next month.

For the first of these, we employed something we call "the strangler pattern."
We would use _Server_ to generate the monthly charges, and then we would use _William_ to do the same.
The goal was the the output would be identical, we would extract the charge calculation functionality exactly--bugs and all (we fixed those bugs as soon as William was deemed authoritative).
This worked fine as a guiding philosphy, but in practice it had a number of challenges.
For example, the billing month ends as 00:00 UTC, but in order to avoid placing undue load on the system during dinner hours in the USA, billing is run several hours later.
Ideally, it wouldn't matter--once the month has ended, no changes should be relevant.
Actually, there are several cases where changes after the month has ended _do_ impact the bill.
Once we started comparing _William_'s output with _Server_'s, it became clear that it mattered _when_ we took the database backup that we used for this comparison.
Since database backups don't happen instantaneously, it was nearly impossible to take the perfect snapshot.
We had to develop tools that would filter out anomalies created by temporal differences.

Once we felt like William was ready to take over for monthly charge calculations, we disabled the scheduled charge-calculation jobs in _Server_ and met during the wee hours of the morning of the first of the month to run billing manually.
We would transfer backups of the relevant database tables to a local instance of _Server_ and compare its outputs with _William_ in production.
If they checked out, we would promote _William_'s results, and if there was doubt, we would manually trigger _Server_ to do the job.
It took a few tries, but _William_ has been calculating bills in the US since last summer, and we put him in charge of EU billing on new years day.

Recently, we've been focusing independence from _Server_ when it comes to on our second responsibility: serving charge-related data to web and device users.
In some ways, this one is trickier, because _some_ server--preferably _William_--must be available to provide these data at all times (not just during scheduled timeslots, which was the case before).
On the other hand, we can take ownership of this functionality in bite-sized pieces.
In our case, those pieces take the from of REST endpoints.
The process looks like this:

- We receive a requirement that one of _Server_'s billing endpoints needs to behave differently.
- My team adds an endpoint to _William_ with the same path and the desired functionality.
- I determine the maximum historical load that the target endpoint has ever placed on _Server_.
- In a local environment, I determine _William_'s breaking point (in requests per second).
- We deploy the new endpoint to _William_ in production, and I test it with a load somewhere between _Server_'s max, and my locally-found breaking point (I have been using [locust](https://locust.io/) for this).
- If everything checks out, we configure the load balancer to start directing traffic for the target endpoint to _William_.

A few weeks ago, William went live in web-mode in the US (on separate nodes than the batch-mode version I described earlier).
We expect to take responsibility for web operations in the EU soon.
We can't claim total independence from _Server_ yet--there are several components that play a critical role in the billing team's mission that are still handled in Server.
But we feel that having deployed both an independent web and batch server is a significant milestone.

It used to feel like every step we took away from _Server_ was a great effort.
The easiest way forward seemed to always be a compromize which lead us back into tight coupling with _Server_.
But now that we have William-Web and Willaim-Batch deployed, it seems like making the right decisionsukj
