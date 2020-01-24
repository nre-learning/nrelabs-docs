# First Steps

So, you want to contribute to the NRE Labs curriculum! Great, and thank you! Please read on for some helpful hints that will guide you along the process and ensure your time is spent wisely.

> No one should feel like they have to get permission to contribute. There's no harm in you opening an Issue or Pull Request that you feel is valuable and is worthy of your time. This section of the docs is aimed at empowering you to do this on your own and get your contributions merged into the project.

## Communicate Your Idea

The NRE Labs curriculum should be treated like any other open source project. It's built via contributions from all over the world, all the time. So before getting started, you should first spend time communicating your plans with the rest of the community.

First, peruse the [existing GitHub issues](https://github.com/nre-learning/nrelabs-curriculum/issues) to see if anyone is already working on something similar to what you have in mind. Maybe someone else is looking to build a similar lesson, and this gives you the opportunity to combine forces with these existing efforts if they exist. A single lesson that covers all the bases is way better than two similar lessons that have overlap and confuse the learner. If this exists, post to that issue and indicate you'd like to contribute.

If no existing issue exists, you should [open an issue](https://github.com/nre-learning/nrelabs-curriculum/issues/new) for yourself so the community can have a chance to provide feedback on your idea before you spend time building it. This will save you a lot of headache in the future.

In this issue, provide as much detail as you can, such as your target audience, and what learners should be expected to get out of this lesson. Remember that this is learning content, so it's not enough to just have a bunch of commands for the learner to run - they should be able to get something tangible from your lesson that they can immediately apply in their day-to-day work.

If you're building a lesson, it's important that you include an outline of what will be contained within the lesson. Each lesson is built of multiple stages, so you should be able to summarize each in a bullet. Note that each stage should follow some kind of natural progression, and should take no more than 10 minutes for the learner to finish.

## Bootstrap Your Content

Once you have a plan in place and have communicated it to the community, it's time to create your lesson.

First, [fork the NRE Labs curriculum GitHub repository](https://github.com/nre-learning/nrelabs-curriculum/fork). This allows you to create a copy of the curriculum at a location of your choosing \(usually underneath your own Github username\) that you have permissions to push to. In a future step, when you're ready to contribute your changes, we'll open a Pull Request to bring your changes back into the upstream curriculum repo.

Once you have your fork, you can clone it to your local filesystem. This is where you'll make all the changes you have planned for your curriculum contribution.

{% tabs %}
{% tab title="SSH" %}
```text
git clone git@github.com:<insert your username here>/nrelabs-curriculum.git
cd nrelabs-curriculum/
```
{% endtab %}

{% tab title="HTTP" %}
```
git clone http://github.com/<insert your username here>/nrelabs-curriculum.git
cd nrelabs-curriculum/
```
{% endtab %}
{% endtabs %}

And this is where we arrive at a bit of a weak spot in our current tooling. In an upcoming effort to re-vamp the Antidote platform, we're hoping to introduce new command-line tools for creating new content. The idea is that you could run a command like `antidote lesson new` and it will run you through an interactive wizard to create new content as easily as possible.

Unfortunately, until this is done, the best thing to do is look for an existing lesson, copy it, and tweak it to meet your needs. So for now, look for examples in the `lessons/` sub-directory of the curriculum that are similar to the idea for a lesson you have in mind, create a copy of that entire lesson directory \(using `cp -r <existing lesson directory> <new lesson directory>`\) and then make edits to the new copy. The [Antidote documentation](https://antidoteproject.readthedocs.io/en/latest/platform/curricula/lessons/index.html) will help with understanding the various files and fields you'll need to know about.

> We're aware this makes for a fairly poor experience, and we're actively working to improve the Antidote tooling to make this a lot easier. In the meantime, the existing [`syrctl validate`](https://antidoteproject.readthedocs.io/en/latest/platform/architecture/syringe/syrctl.html)  command **does** allow you to at least check to ensure the copied content you've created meets the basic standards. Please stay tuned to the [Antidote Mini-Project 1 \(MP1\)](https://community.networkreliability.engineering/c/antidote-platform-project-management/mp1-syringe-redesign) for updates on new tooling to make lesson content easier to bootstrap.

