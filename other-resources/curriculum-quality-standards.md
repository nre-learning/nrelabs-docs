# Curriculum Quality Standards

NRE Labs is a **learning** platform. While there are certainly tools in the platform for creating compelling, interactive experiences, the goal of NRE Labs is not merely to demonstrate a piece of technology. These tools are supporting elements for the greater mission to educate and edify the learner and the infrastructure community as a whole.

This document is meant to provide guidance so that any contributed content can be well-aligned towards this mission. As you consider contributing to the curriculum, please approach it with a teacher's mindset. Always be asking yourself: "How can I meaningfully and tangibly improve the day-to-day experiences of the learner?" If you can learn to think this way, you'll find you'll be much better aligned with the spirit of the project.

Please read this document and its guidance thoughtfully. Doing so will make the review and ultimately, the acceptance of your contribution much smoother.

## NRE Labs' Guiding Principles

### The Learner Must LEARN Something

You'll notice that we rarely \(if ever\) use the term "users", but rather "learners" when referring to people who consume the content on NRE Labs. This is intentional; it helps us to keep our eyes on the mission of education, rather than pushing a certain tech stack or product feature.

From the beginning of the project, the goal of NRE Labs has been to tangibly improve the day-to-day lives of infrastructure professionals. The past few decades have been plagued with talk of people losing their jobs due to automation, and infrastructure professionals being "replaced by programmers". This project took a different approach, of not talking down to, but rather empowering these professionals with the skills they need to not only keep pace with the changing technology landscape, but to get ahead. There is no other goal that is more central to the NRE Labs project. It is our "[Raison d'être](https://www.merriam-webster.com/dictionary/raison%20d%27%C3%AAtre)".

The NRE Labs project is so much more than a collection of docker images that we let people play with in a web-based environment. This is certainly a great feature of the platform, but these are meaningless without compelling, well thought-out content that allows the learner to come away from this experience with real skills they can apply immediately.

These skills must also be reasonably portable. While it's totally acceptable to use a specific tool or technology to illustrate a concept, lessons that focus too deeply on the specific features/functionality of a given tool or product \(to the point where the learner must use that exact same tool or product to get any value out of that content\) are not appropriate for NRE Labs. Instead, lessons must focus on the concepts and principles, using specific tools or products as an illustration of an example of how those concepts can be achieved, leaving room for others.

So in short:

* **The Learner Must Acquire Tangible Skills From the Content** - It's not enough to have them run some commands - how can they take the underlying core principles behind the content and use them to improve their day-to-day?
* **Learned Skills Should be Portable** - Where at all possible, these skills must be widely applicable beyond a specific technology or stack. Can the learner take these skills and reasonably apply them in their own environment?

### The Learner Must DO Something

Complex subjects like automation can be especially hard to learn by simply reading a blog post. At some point you have to get practical experience before anything "sticks". So much of what modern infrastructure professionals are expected to know these days are acquired not only through textbooks or video courses, but by years of practical experience.

One of the biggest ways NRE Labs helps the learner adopt new skills is by giving them an opportunity to actually interact with relevant technologies in a very hands-on way. If our goal is to truly edify the learner, this "learning by doing" is how we make this possible.

However, this interactivity is a balancing act. What we aim for is to provide **the simplicity of a blog post, with the interactivity of a home lab**. When writing your content, try to keep this aim in mind. Content should provide a [compelling lesson guide](../antidote/object-reference/lessons/stages.md#lab-guides), with illustrative images and videos where possible, to help the learner understand what they're expected to accomplish in your lesson. This should be joined with tools like [Endpoint Images](nre-labs-endpoint-images.md) and [Presentations](../antidote/object-reference/lessons/presentations.md) to bring this content to life with real, interactive experiences. Break your content up into [Stages](../antidote/object-reference/lessons/stages.md), and build on concepts learned in previous stages to accomplish the broader purpose for your Lesson. Aim to give the learner a sense that they've really accomplished something, and that the time they spend in the NRE Labs curriculum will give them a tangible return on their investment.

It's also important that when you build interactive examples that you ensure this interactivity is at an appropriate level. If for instance, you build a lesson that shows a script that you built to solve a certain problem, perhaps it would be useful to first spend a few stages walking through the script, maybe having the learner run the commands in the script line-by-line. Don't just build a lesson for the purpose of having the learner run a few scripts: break those scripts down into the basic concepts and principles, so that the learner can learn from your thought process, and then write their **own** scripts.

Finally, there are some things you may want to do in the lesson environment that are not strictly relevant to the concept you want to teach. Maybe you need to run a script to prepare the environment at runtime so the learner can experience a specific workflow or aspect of a tool or technology stack. In this case, consider using [Endpoint Images](nre-labs-endpoint-images.md) and [Endpoint Configurations](../antidote/object-reference/lessons/endpoint-configuration.md) to prep the lesson environment behind the scenes, so that when a learner loads a lesson, they're given an environment that has already been prepared for them. It's important that the interactive steps that we give to the learner remain focused on the task at hand - anything outside of that scope can and should be automated by the NRE Labs platform using these tools.

So, to summarize:

* **Lessons Must be Appropriately Interactive -** Balance good content with useful interactivity.
* **Give the Learner Superpowers** - Don't just show the end result, teach the learner how to get there themselves.
* **Focus On the Task at Hand** - If a task needs to be done, but isn't core to the concepts you're trying to teach, try baking it into the [Endpoint Image](nre-labs-endpoint-images.md) or run via [Endpoint Configurations](../antidote/object-reference/lessons/endpoint-configuration.md) to keep learner's focus where it needs to be.

## Contribution Process

Generally we try to keep process to a minimum. However, to ensure quality remains high, there are a few things that any contribution must adhere to.

**ALL** contributions to the NRE Labs curriculum must be done via a Pull Request, and Pull Requests can only be merged to `master` if the latest commit on that Pull Request's branch satisfies all of these requirements:

1. Passes all GitHub CI checks
2. Has a valid "accepted" review from a curriculum maintainer.

Note that the goal for **each and every review** is not to nitpick or make it difficult to contribute to NRE Labs, but rather to ensure the content is reflected in the best light possible. Be patient and willing to adapt to feedback.

## Content Outline

From time to time, a reviewer may ask you for an outline of your planned content. This is an easy way for you to communicate the "big picture" for your content so that everyone can get on the same page with what your lesson is trying to teach.

For this purpose, you can think of an outline in the same way that someone would write a "table of contents" for a book. This can simply be a bulleted list where each entry is a [lesson stage](../antidote/object-reference/lessons/stages.md) you plan to create. In each bullet, briefly name and describe each stage and what you expect the learner to get out of it.

While there is no strict requirement for providing an outline ahead of time, you're encouraged to provide one **as early as possible**, to ensure that if there are any problems, they can be addressed early. For simple contributions, you may choose to provide this your contribution's Pull Request. For complex content, or especially if your content requires new [Endpoint Images](nre-labs-endpoint-images.md), a separate Issue ahead of time would be immensely helpful.

Well thought-out outlines should answer the following questions:

* How will this content be chunked, if appropriate, into separate [stages](../antidote/object-reference/lessons/stages.md)? Put each stage in its own bullet point.
* In each stage, what will the learner actually **do** interactively, and what skills will they expect to pick up along the way, that they can apply to their day job?
* Is the relevance to the learner clear from this lesson? How easy is it for people to link this content with their day-to-day?
* Does each lesson stage hit the target length of 5-10 minutes?

## General Quality and Technical Tips

Here are some helpful tips on general quality or various technical aspects of building NRE Labs content. Don't stress out too much about these; do your best, and we'll help you work things out during the review process.

* Are the lesson guides easy to follow? Are they well-written, with appropriate chunking, punctuation/grammar, and visuals?
* If you're creating or modifying images, have you read the guide on [NRE Labs Endpoint Images](nre-labs-endpoint-images.md)?
* Does the lesson appropriately take advantage of Antidote's features, such as [lesson guide types](../antidote/object-reference/lessons/stages.md#lab-guides), diverse [presentations](../antidote/object-reference/lessons/presentations.md), lesson diagrams or videos?
* Ensure that any [configurations](../antidote/object-reference/lessons/endpoint-configuration.md) you use treat each stage atomically. Don't assume that the learner will view each stage in order.

