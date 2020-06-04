# Development

If you're interested in digging into the actual code and contributing to the Antidote project, this set of documents will help.

## Familiarize Yourself

First, you should take a look at the [Architecture section](../antidote-architecture/). It's likely you don't need to know how the whole thing works, as most contributions here are to a very specific component, but the context to which your contributing is important.

From a code perspective, the Antidote platform is separated into two main parts:

* [antidote-web](https://github.com/nre-learning/antidote-web) - this is the web front-end for the platform. If you lean more towards front-end development, such as HTML, CSS, and Javascript, this repository is a good place to start. Note that antidote-web forms the basis for the web front-end, but depends on a few other repositories for certain functionality:
  * [antidote-ui-components](https://github.com/nre-learning/antidote-ui-components) - houses web components for various portions of the application
  * [nre-styles](https://github.com/nre-learning/nre-styles) - stylesheets used by antidote-web and other project sites
  * [antidote-localizations](https://github.com/nre-learning/antidote-localizations) - localization strings for the copy within the platform application
* [antidote-core](https://github.com/nre-learning/antidote-core) - this is the core set of services that power the "back end" of Antidote. It is here that we integrate with Kubernetes and provide an API for `antidote-web` to consume. It is also here where we maintain any command-line tooling, such as the `antidote` command.

> The `README.md` file for both `antidote-web` and `antidote-core` contain instructions for building the software, and, if applicable, running tests. Please refer to those for more information.

The first thing you should do for any repository mentioned above that is of any interest to you, is to "[Watch](../../other-resources/nre-labs-git-repositories.md#watching-for-activity-notifications)" it. Any activity that takes place in this repository will generate a notification for you. You can control how you're notified in your GitHub settings, but we recommend enabling email notifications. It's a great way to make sure you're at least aware of what's going on. If you aren't interested, you can always just delete the email.

## Pull Request Reviews

A good way to get familiar with the code is to "[Watch](../../other-resources/nre-labs-git-repositories.md#watching-for-activity-notifications)" a repository, and when someone opens a PR, provide a constructive review. Many of the core platform developers open pull requests as soon as they start working on a feature or a bugfix, which often gives a large window of time where the pull request is open and questions can be asked, even on specific lines of code that changed.

Any constructive comments or questions here are not only appreciated, but it's often the best way to get insight into how the platform works, as you're inserting yourself right into where the work is actually getting done, without having to write a single line of code yourself. You don't have to be a platform developer or even consider yourself a developer at all to be curious and ask questions. We'd love to have you and help you get more familiar with how things work within the Antidote platform.

## Contribute

In almost every repostory, we have [labeled issues by complexity](../../other-resources/nre-labs-git-repositories.md#using-issues-to-identify-low-hanging-fruit), so you can see at-a-glance which issues have been identified for the express purpose of getting started with the project. You can use this to get an estimate for how much work a given task is expected to take. For your first contribution, you may want to stick with "low complexity".

For simple enhancements or fixes, feel free to open a Pull Request at any time. If you're not quite ready for a review, open the pull request as a "draft", or otherwise indicate that it's a work-in-progress. Please fill out the template description so reviewers can make sense of your contribution more easily.

For big contributions, know that the more communication you provide ahead of time, the better - especially if you're new to the platform. It's often work opening an issue in advance, so we can have a discussion about the intended outcome of the contribution, and how we can make sure it melds well with the project as a whole.

