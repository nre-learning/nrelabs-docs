# Development

If you're interested in digging into the actual code and contributing to the Antidote project, this set of documents will help.

## Familiarize Yourself

First, you should take a look at the [Architecture section](../antidote-architecture/). It's likely you don't need to know how the whole thing works, as most contributions here are to a very specific component, but the context to which your contributing is important.

From a code perspective, the Antidote platform is separated into two main parts:

* [antidote-web](https://github.com/nre-learning/antidote-web) - this is the web front-end for the platform. If you lean more towards front-end development, such as HTML, CSS, and Javascript, this repository is a good place to start. Note that antidote-web forms the basis for the web front-end, but actually has some children repositories for housing specific aspects of the front-end:
  * [antidote-ui-components](https://github.com/nre-learning/antidote-ui-components) - houses web components for various portions of the application
  * [nre-styles](https://github.com/nre-learning/nre-styles) - stylesheets used by antidote-web and other project sites
  * [antidote-localizations](https://github.com/nre-learning/antidote-localizations) - localization strings for the copy within the platform application
* [syringe](https://github.com/nre-learning/syringe) - this is the core set of services that power the "back end" of Antidote. It is here that we integrate with Kubernetes, provide an API to the front-end, etc. It is also here where we maintain any command-line tooling, such as the `syrctl` command.
  * This will soon be referred to as `antidote-core`

The first thing you should do for any repository mentioned above that is of any interest to you, is to "[Watch](../../other-resources/nre-labs-git-repositories.md#watching-for-activity-notifications)" it. Any activity that takes place in this repo will generate a notification for you. You can control how you're notified in your GitHub settings, but we recommend enabling email notifications. It's a great way to make sure you're at least aware of what's going on. If you aren't interested, you can always just delete the email.

## Pull Request Reviews

A good way to get familiar with the code is to "[Watch](../../other-resources/nre-labs-git-repositories.md#watching-for-activity-notifications)" a repository, and when someone opens a PR, provide a constructive review. U of platform developers open pull requests as soon as they start working on a feature or a bugfix, which often gives a large window of time where the pull request is open and questions can be asked, even on specific lines of code that changed.

Any constructive comments or questions here are not only appreciated, but it's often the best way to get insight into how the platform works, as you're inserting yourself right into where the work is actually getting done, without having to write a single line of code yourself. You don't have to be a platform developer or even consider yourself a developer at all to be curious and ask questions. We'd love to have you and help you get more familiar with how things work within the Antidote platform.

## Starting Small

Okay - let's say you're ready and willing to contribute something more directly, but you're not sure where to start. Fear not - you're not alone. This is one of the most challenging parts of any open source project - picking that first or second task that's challenging enough to teach you something, but not so challenging that you have to spin your wheels for weeks before you feel like you've accomplished anything.

We've explicitly carved up Github issues in nearly every Antidote project repository just for you. Take a look at the :ref:`Git section of these docs <git-lowhanging>` where you'll find a system of labeling issues by complexity, so you can see at-a-glance which issues have been identified for the express purpose of getting started with the project.

## Going Big

For complex features, especially those that span across the various component projects to the Antidote platform, you'll be required to create a blueprint in the [proposals](https://github.com/nre-learning/proposals/tree/master/blueprints) repo. This gives needed structure for the effort you have in mind, and gives others a chance to get involved.

There are no hard rules on when a blueprint is required, but please be prepared to do this if a maintainer asks in order to move things forward. There are also no rules on what should be _in_ a blueprint, but it should minimally answer the following:

* What is the problem you're trying to solve? How will this solve that problem?
* What components of Antidote \(and how\) will this need to touch?
* What is the detailed design of the feature in it's ultimate state?
* What are the discrete steps \(each step being its own PR\) we will need to take to accomplish this feature. If

  separate steps, how will we ensure project stability while the work is in progress?

Blueprints aren't meant to be a super formal, heavy-handed process for everyone to go through before they can do anything - ideally they'll only be used for the really complicated ideas as the project moves out of the "alpha" stage, and will help keep everyone abreast of the big ideas and how the work will get done - providing space for everyone to contribute the way they want to.

