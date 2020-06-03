# NRE Labs Endpoint Images

The primary purpose of NRE Labs is to provide education on modern network engineering and automation principles. So, while this purpose is often accomplished by including specific tools, software, or other technologies, let us not lose sight of this over-arching mission.

That said, one of the biggest benefits of the NRE Labs platform is to use real software in real environments, spun up on demand, to provide compelling interactive experiences in which this learning can take place. In NRE Labs, we accomplish this through [Endpoint Images](../antidote/object-reference/images.md). These are pre-built docker images that we reference from Lesson definitions to power the learner experience.

If you're looking for technical details on how Endpoint images work, and how to create or add them to the curriculum, please head on over to the [Images object reference](../antidote/object-reference/images.md). The remainder of this document will instead help you understand the higher-level process for dealing with Images within the NRE Labs curriculum, and answer some frequently-asked questions.

## Do You Need a New Image?

**NRE Labs curriculum images are where all the complexity lies**. To make things easy for the learner, we have to take on a lot of the complexity that would normally be on their plate, and instead do it ourselves using prebuilt [Docker images](../antidote/object-reference/images.md), and other tools like [endpoint configuration](../antidote/object-reference/lessons/endpoint-configuration.md). As a content author, you should be aware that if you choose to go this direction, you need to be willing and able to shoulder this complexity.

In general, new curriculum content like [Lessons](../antidote/object-reference/lessons/) should take advantage of the Endpoint images that already exist. Images are not meant to be used once, for one lesson - they are meant to be standalone resources that could be used in multiple lessons as the need arises.

There are a few options you should consider before you decide to create a new image. They are, in order:

1. There are a number of existing images that are designed to be very multi-purpose. For instance, the `utility` image comes with Python and a bunch of automation-related libraries pre-installed.
2. If you just want to share some basic files or scripts into the lesson environment, consider using an existing image like `utility`, and using NRE Labs' built-in [directory mapping](../antidote/antidote-architecture/lesson-directory-mapping.md) to make those files available.
3. Maybe there's an existing image that's just missing a dependency. Consider augmenting an existing image, by simply adding a step to that image's `Dockerfile`, or maybe a `requirements.txt` file if applicable.
4. If none of these options work for you, read on to create a new image

> Currently the best place to see details on existing images is to look at the NRE Labs curriculum repository manually. In the future, we'll have some better tooling around this.

If you got to the end of this list and have decided to create a new image or augment an existing one, you should open a Pull Request first, before you contribute any lesson content that would use it. See the [Images reference](../antidote/object-reference/images.md) for instructions on what goes into this. Note that in the pull request for your image, a maintainer may likely request that you provide an outline of your intended lesson, so they can also understand why a new image was needed.

## Commercial Software

NRE Labs is aimed at educating about modern infrastructure engineering processes. While open source has had a dramatic impact on this space over the last decade, which is well-represented by the presence of open-source in the NRE Labs curriculum, it's not possible for the NRE Labs project to **only** include open source software. Most infrastructure professionals are not able to avoid commercial software entirely, and neither can this curriculum.

There are two main things to address when discussing

1. Balance - the focus isn't on the \*thing\* but the content. Talk about how we support it, and how we'll continue to balance against it with other things. 
2. Fair - all commercial software is welcome to participate.  Talk about how ANY vendor is welcome to participate - point out Junos, Cumulus and RH \(Tower\) and maybe Extreme as leading examples.
3. Private - you don't have to post your software publicly. We have private mechanisms.







