# Bootstrapping Your Content

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

