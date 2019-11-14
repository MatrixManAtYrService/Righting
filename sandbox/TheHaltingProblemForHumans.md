# The halting problem for humans

You are more than a computer, but you are _at least_ a computer.
For this discussion let's lay down a simple definition for what computers do.
It may be overly simple, but you have my word that I'm not hiding any nasty gotchas in the simplicity.

A computer accepts input, and based on that input, changes state.
Sometimes, it only changes state for a little while, and then it stops and provides some output (we'll call this halting).
Other times, it gets stuck in some kind of cyclical behavior where it transitions from state to state, but never provides any output.
This is annoying, especially because it's sometimes challenging to know whether the computer is truly stuck in an infinite loop, or if it's working fruitfully and will halt and provide some output any minute now.

Some computers are more or less powerful than others.
In this case "powerful" is a qualitative thing, it has nothing to do with speed or access to resources like memory.
In fact, in computability theory, all computers are assumed to have infinite memory, and we're really not interested in how long they take to complete their work--just whether they complete their work at all.

Let's take a look at a computer that isn't very powerful, here's a diagram:
![A finite state machine](fsm.png)

