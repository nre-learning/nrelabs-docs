# Communicating Your Idea


## Step 1 - Ask Around!

The NRE Labs Curriculum should be treated like any other open source project. It's built via contributions from all over the world, all the time. So, the very first thing you should do is get a lay of the land. First, peruse the `existing curriculum issues <https://github.com/nre-learning/nrelabs-curriculum/issues>`\_ to see if anyone is already working on something similar to what you have in mind.

If not, please first [open an issue](https://github.com/nre-learning/nrelabs-curriculum/issues/new) so the community can have a chance to provide feedback on your idea before you spend time building it. There's a chance that something already exists, or maybe someone else is planning to work on it, and evangelizing your idea first gives you an opportunity to combine forces with these existing efforts if they exist. A single lesson that covers all the bases is way better than two similar lessons that have overlap and confuse the learner.

## Step 2 - Plan It Out

Even if you have determined that no one else is working on the thing you want to work on, it's still a good idea to build a general outline of the lesson you want to build and solicit feedback from the maintainers and contributors to NRE Labs.

If you haven't [opened an issue](https://github.com/nre-learning/nrelabs-curriculum/issues/new>) yet, it's still recommended you do so. Use this as a way to provide an outline to the community, as well as yourself, of the lesson you have in mind. Provide as much detail as you can, listing the various topics you want to cover, how long each lab/stage is expected to take, what kind of new software will need to be brought into the curriculum, etc.

This gives other community members a chance to review your plan and maybe address any concerns ahead of time, saving you a lot of headache in the long-term.

Here are some tips for a great lesson:

* Lessons in NRE Labs should demonstrate something that a network engineer could easily replicate in their own environment. Topics we teach here should be aimed at getting the learner skilled up enough to actually put these concepts into production. So, the more practical the better.
* Individual labs within a lesson should be kept to a reasonable length. The general rule of thumb is that a single lab can be finished in about 5 minutes. A lab that is too short, and the learner will feel like they're not learning a lot. Too long and the learner won't feel like they're accomplishing anything. So, within a single lesson, be very intentional with how you're breaking content up into different labs.
* Some lessons can be repeated 2 or 3 times.  For instance, in addition to the NAPALM lesson, you could show the user how to collect system information using an alternate method.  You should explain why a network engineer would want to choose one method over another.  In the case of the first lesson, NAPALM is a somewhat limited tool. If the user needs additional information, they would need to do something different.  They could use PyEZ, for instance.
* Some lessons could be a group of inter-related tasks.  A troubleshooting workflow that helps a network engineer locate a device in the network, or the path between two devices, could be broken up into a set of distinct tasks. Not every task has to be automated, but some could be, and the lessons could reflect this.