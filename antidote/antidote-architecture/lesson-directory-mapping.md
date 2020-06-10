# Lesson Directory Mapping

There are two ways to get your "stuff" into a lesson:

* Image
* Directory

The decision here depends on the nature of that "stuff". Is the stuff lesson specific? If so, probably best to put it into the lesson directory. Is it part of the software used within an image? Build it into the endpoint image itself. Also for large files, it's often better to download it during build time and place it into the image \(see [Images - Large or Sensitive Files](../object-reference/images.md#large-or-sensitive-files)\).



Putting your "stuff" \(scripts, configs, etc\) into a Docker image isn't the only way to get it into a lesson. At this point, you probably know that Antidote lessons are defined with simple text files, and those files are stored in a Git repository. What you might not know is that when a lesson is instantiated, the full directory that contained that lesson in the Git repository is made available to each lesson endpoint.

Every endpoint that's instantiated in a lesson has that lesson's directory mapped to it, and all of its contents. If you just want to run a set of bash or Python commands, or you have a script you wish to show, you likely don't need to do anything beyond simply placing those files into the lesson directory, or putting a set of commands into a lesson guide.

The `utility` image, for example, comes preloaded with Python and a bash shell, so can satisfy a lot of use cases here. You simply reference this image when defining an endpoint in your lesson definition, and any files you place in the lesson directory will be made available at runtime to the configured directory. In NRE Labs, this is the `/antidote` directory.



## How do I get my "stuff" into a lesson?

It's quite rare to have a lesson in mind that doesn't also include some kind of custom "thing". This could be a simple script you wrote or downloaded and wish to show it in your lesson, configuration or data files used by an application, or full-blown software you'd like to be installed and running or available within the environment. At the end of the day, your goal is to get this "stuff" into your lesson definition.

In the **vast majority of cases**, the best way to do this is simply to store those files in your lesson's directory tree. When your lesson is launched, this lesson directory is mapped via volume to every container that runs in a lesson \(at `/antidote`\) so just by having those files in that directory, you'll have access to them at runtime.

You can also create an [Endpoint Image](../object-reference/images.md) if you're looking for a more complicated software installation to be available in your lesson.

