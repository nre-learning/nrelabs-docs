# Lessons



## Lessons

Lessons are the quintessential curriculum resource. When Syringe starts, it looks for lesson definitions within the configured curriculum directory, loads them into memory, and serves them directly via its API. These lesson definitions are written in YAML. A reasonably complete example is shown below. Don't worry about understanding it for now - below the example, we'll explain the beginning of the file, which describes some metadata about the Lesson. We'll also link to other documents which go into detail on Endpoints, Connections, and Stages.

```text
---
lessonName: Network Unit Testing with JSNAPY
lessonId: 12
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

endpoints:
- name: linux1
  image: antidotelabs/utility
  presentations:
  - name: cli
    port: 22
    type: ssh

- name: vqfx1
  image: antidotelabs/vqfx-snap1
  configurationType: napalm-junos
  presentations:
  - name: cli
    port: 22
    type: ssh

- name: vqfx2
  image: antidotelabs/vqfx-snap2
  configurationType: napalm-junos
  presentations:
  - name: cli
    port: 22
    type: ssh

- name: vqfx3
  image: antidotelabs/vqfx-snap3
  configurationType: napalm-junos
  presentations:
  - name: cli
    port: 22
    type: ssh

connections:
- a: vqfx1
  b: vqfx2
- a: vqfx2
  b: vqfx3
- a: vqfx3
  b: vqfx1

stages:
  - id: 1
    description: No BGP config - tests fail

  - id: 2
    description: Correct BGP config - tests pass
```

If you're feeling overwhelmed, don't worry. This file can be broken up into sections, and we'll do this to explain it, piece by piece. For now, let's just focus on the top portion:

```text
---
lessonName: Network Unit Testing with JSNAPY
lessonId: 12
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

This section contains metadata about this lesson. This isn't directly concerned with the actual content you're trying to convey through a lesson, but it's very valuable for helping users find the content, and use it within their learning journey. Below is a table which describes each field:

> Some of these fields are required, some aren't. Some have a length requirement, and others don't. For guidance here, you should definitely get up to speed with the [`syrctl`]() tool. That tool has a validation function you can run on a curriculum, and it will let you know if anything needs fixed.

* `lessonName` The human-readable name for a lesson. Kind of like a blog post title.
* `lessonId` A unique ID for this lesson. You can assign this yourself, as long as it's unique in this curriculum.
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

