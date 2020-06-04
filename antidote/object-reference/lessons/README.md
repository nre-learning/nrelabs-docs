# Lessons

Lessons are the quintessential curriculum resource. When Syringe starts, it looks for lesson definitions within the configured curriculum directory, loads them into memory, and serves them directly via its API. 

Lessons are primarily defined using a `lesson.meta.yaml` file. This is written in YAML, and contains a series of fields for making a lesson work. 

If you're feeling overwhelmed, don't worry. This file can be broken up into sections, and we'll do this to explain it, piece by piece. For now, let's just focus on the top portion:

```yaml
---

# A human-readable title for your lesson
lessonName: Network Unit Testing with JSNAPY

#
lessonSlug: unit-testing-jsnapy
category: tools
lessonDiagram: https://raw.githubusercontent.com/nre-learning/nrelabs-curriculum/v0.3.2/lessons/lesson-12/lessondiagram.png
tier: prod
prereqs:
  - 14  # YAML
  - 23  # Linux
description: Unit testing your network devices is one of the fundamental building blocks to CI/CD for networking. In this lesson, we'll explore the use of an open source tool - JSNAPy - for doing just this with Junos devices.
slug: JSNAPy
tags:
- jsnapy
- test
- unit test
- testing
collection: 1
```



> Some of these fields are required, some aren't. Some have a length requirement, and others don't. For guidance here, you should definitely get up to speed with the [`syrctl`]() tool. That tool has a validation function you can run on a curriculum, and it will let you know if anything needs fixed.

* `lessonName` The human-readable name for a lesson. Kind of like a blog post title.
* `lessonSlug` A unique ID for this lesson. You can assign this yourself, as long as it's unique in this curriculum.
* `category` The category for this lesson - supported options are "fundamentals", "tools", and "workflows"
* `lessonDiagram` An internet-accessible URL to an image to use as a diagram for this lesson
* `tier` The environment this lesson is meant to run in. Options are "local", "ptr", and "prod"
* `prereqs` A list of lesson IDs that a learner should go to first, to prepare for this lesson properly. 
* `description` A slightly more long-form explanation of what's included in this lesson
* `slug` Ideally, a very short \(1-3 words\) summary of this lesson. Used for searching.
* `tags` A list of keywords that are included in this lesson. Used for searching.

The remaining sections are explained in separate documents:

* The `endpoints` section is explained in [endpoints](endpoints.md).
* The `connections` section is explained in [connections](connections.md).
* The `stages` section is explained in [stages](stages.md).

