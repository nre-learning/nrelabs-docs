# Antidote Release Process

The Antidote platform is comprised of multiple subprojects, which all need to be coordinated to release the Antidote platform as a cohesive unit. The lifecycle of a release of the Antidote platform is performed in four discrete steps, which are outlined in the following sections.

### 1 - Release Kickoff

A post will be created in the [Project Management](https://discuss.nrelabs.io/c/project-management/10) forum topic to notify everyone that the work on this release has begun, with the title "Release Kickoff...". This forum thread should serve as the center of all release planning discussions, and all are welcome to participate. If you have something you think should be included in or excluded from the release plan, speak up there.

In this first kickoff, we'll begin gathering ideas for things we want to get done in this release. These will be retrieved from various sources:

* First we start with the [Antidote v1.0 Roadmap](https://github.com/nre-learning/proposals/blob/master/antidote-v1.0/roadmap.md).

  Are there any milestones for the upcoming release we need to hit?

* Second, we comb through the issues for the repos and triage accordingly. Which are ready to

  be worked on, or are most imminent, according to complexity labels?

While the kickoff is meant to get a starter list together, it's likely that more ideas will come up at any time in the release cycle. This is normal, and expected. However, the first week of a release cycle should strive to ensure the really important things are well-documented and if possible, assigned.

A project plan for the release that represents the work discussed in the previous week will be posted to the [nre-learning org's projects list](https://github.com/orgs/nre-learning/projects) and presented to attendees. This is a kanban-board style project planning tool that allows all to easily see the state of work for a given release.

> Not all work fits neatly into a release plan, and that's okay. Contributions of any kind can reasonably take place at any time. The purpose of a release plan isn't to put limits on the work that can be done for a release, but rather to ensure that the important things that really **need** to get done are accounted for. If you want to work on something that's not explicitly asked for in the release plan, that's totally fine.

### 2 - Development Work

Once a release cycle is kicked off, the only thing left to do is....do the work! At this point, a relatively complete list of things to do for this release should be captured in a Github project, which will be linked to in the community forum kickoff post. Contributors can use this as a guide, or do other work they think is useful.

The [Platform Development Guide](./) should be consulted repeatedly to ensure you're on the right track with respect to platform contributions. All of those guidelines apply here. It's important for contributions to follow this lifecycle, so that release managers can properly coordinate work across the project.

### 3 - Testing Phase

Once the tasks identified for this release have been finished, we will freeze `master` for all platform projects and begin a round of end-to-end testing.

The [test curriculum](https://github.com/nre-learning/antidote-test-curriculum) has been constructed for the purpose of testing all of the Antidote platform features. This curriculum should be updated to ensure not only compatibility with any platform changes, but also that all of the features of the platform are suitably used and tested.

A forum topic will be posted to [Platform Project Management](https://community.networkreliability.engineering/c/platform-project-management) with the title "Testing Antidote Release vX.X.X". This will contain a link to the testing procedure, and a summary of the CHANGELOG at that point in time, so that new features can be tested properly. For a minimum of seven days from the date of the post, contributors should submit feedback to this forum thread, or as Github issues.

### 4 - Release and Deployment

Once the testing phase has completed, the NRE Labs Ops team will execute a workflow that creates a release for all relevant platform projects. This will create docker images for everything with appropriate tags, as well as provide compiled binaries for Syringe.

After the release is finished, it's entirely up to those in charge of the [NRE Labs curriculum release process](../../other-resources/curriculum-release-process.md) when or if this platform release is used in production for the NRE Labs site.

In the following week \(or at most two\), the cycle will repeat, and a new release kickoff will take place.

