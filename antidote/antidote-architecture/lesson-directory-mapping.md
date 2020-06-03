# Lesson Directory Mapping

Putting your "stuff" \(scripts, configs, etc\) into a Docker image isn't the only way to get it into a lesson. At this point, you probably know that Antidote lessons are defined with simple text files, and those files are stored in a Git repository. What you might not know is that when a lesson is instantiated, the full directory that contained that lesson in the Git repository is made available to each lesson endpoint.

Every endpoint that's instantiated in a lesson has that lesson's directory mapped to it, and all of its contents. If you just want to run a set of bash or Python commands, or you have a script you wish to show, you likely don't need to do anything beyond simply placing those files into the lesson directory, or putting a set of commands into a lesson guide.

The `utility` image, for example, comes preloaded with Python and a bash shell, so can satisfy a lot of use cases here. You simply reference this image when defining an endpoint in your lesson definition, and any files you place in the lesson directory will be made available at runtime to the configured directory. In NRE Labs, this is the `/antidote` directory.

