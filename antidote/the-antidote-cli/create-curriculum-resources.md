# Create Curriculum Resources

The `antidote`tool comes with the ability quickly bootstrap a new resource, such as a lesson. This provides you with an interactive wizard that walks you through all of the fields within a resource definition, and creates a barebones framework for that lesson. In the case of a lesson, this not only creates the required `lesson.meta.yaml` file, but also all of the files and directories required by that lesson.

You can access this wizard by simply running `antidote <resource> create`. So, to create a new lesson, run `antidote lesson create`. You'll immediately be presented with a series of prompts to provide the necessary information to bootstrap that lesson:

{% embed url="https://www.youtube.com/watch?v=G3sM\_5rk2yc" %}

> Similar commands may exist for other resources like `images` and `collections`.

Note that this tooling isn't designed to build a finished lesson, only a starting point. There's still a lot left to do at the end of these wizards, so pay close attention to the hints at the end of the wizard for next steps.

Next thing you'll want to do is bookmark the [Antidote Object Reference](../object-reference/). All curriculum resources, such as lessons, are defined "as-code", meaning they are all defined using simple text files stored in Git. This documentation is vital for knowing what kind of things you can use to create an awesome lesson, so read that carefully, and follow the instructions there, whether you're creating a new lesson, or modifying an existing one.

