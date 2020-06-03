# First Steps

So, you want to contribute to the NRE Labs curriculum! Great, and thank you! Please read on for some helpful hints that will guide you along the process and ensure your time is spent wisely.

Before you get started, please read the [NRE Labs Curriculum Standards](https://github.com/nre-learning/nrelabs-curriculum/blob/master/CONTRIBUTING.md). This is **the** document used by all content reviewers to ensure curriculum quality remains high, and all contributions must adhere to these standards.

> **NOTE for Open Source Maintainers -** we would love the opportunity to host tutorials for your project. If you've created or are maintaining an open source project you should have the right of first refusal for contributing a lesson on your project in the NRE Labs curriculum.

## Communicate Your Idea

The NRE Labs curriculum should be treated like any other open source project. It's built via contributions from all over the world, all the time. So before getting started, you should first spend time communicating your plans with the rest of the community.

First, peruse the [existing GitHub issues](https://github.com/nre-learning/nrelabs-curriculum/issues) to see if anyone is already working on something similar to what you have in mind. Maybe someone else is looking to build a similar lesson, and this gives you the opportunity to let them know, and combine forces.

> lf you are looking to collaborate on a lesson, [opening an issue](https://github.com/nre-learning/nrelabs-curriculum/issues/new) is often a good way to see if anyone in the community is interested in helping out.

## Do You Need New or Changed Images?

We have a dedicated document for handling [Endpoint Images in NRE Labs](../other-resources/nre-labs-endpoint-images.md), and you should definitely read this first. In the \(ideally rare\) event that you need a new image or a modified image for your lesson, this must be handled **first**, ahead of any lessons that may need them.

## Bootstrap Your Content

> **IMPORTANT NOTE** - if your lesson will require new software images not already in the curriculum, or edits to an existing image, please read "[NRE Labs Endpoint Images](../other-resources/nre-labs-endpoint-images.md)" first, as this must be handled separately, ahead of any content contributions.

Once you have a plan in place and have communicated it to the community, it's time to create your content.

First, [fork the NRE Labs curriculum GitHub repository](https://github.com/nre-learning/nrelabs-curriculum/fork). This allows you to create a copy of the curriculum at a location of your choosing \(usually underneath your own GitHub username\) that you have permissions to push to. In a future step, when you're ready to contribute your changes, we'll open a Pull Request to bring your changes back into the upstream curriculum repository.

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

Next, you'll need the [Antidote CLI](../antidote/the-antidote-cli/). This is the command-line tool for bootstrapping new content for NRE Labs like lessons. Install this tool using the instructions provided, and then [follow the instructions here](../antidote/the-antidote-cli/create-curriculum-resources.md) to bootstrap a new curriculum resource such as a lesson. These interactive wizards will create a skeleton copy of a new resource within your existing curriculum directory, which you can then use as a starting point.

> Note that this tooling isn't designed to build a finished lesson, only a starting point. There's still a lot left to do at the end of these wizards, so pay close attention to the documentation as well as the output at the end of the wizard.

Once finished with the initial bootstrap, you'll also want to [validate your local curriculum](../antidote/the-antidote-cli/validating-an-existing-curriculum.md). This validation step can identify any problems with what you've built, and is a necessary next step after the initial bootstrap. Contributions to the curriculum must pass this validation step before being merged, so it's worth it to run this locally yourself first.

If you run into problems here, you may consider moving to the next phase, and open a pull request anyways. This way, maintainers will be able to see what you've done thus far, and provide suggestions.



