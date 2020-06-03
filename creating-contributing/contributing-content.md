# Open a Pull Request

The NRE Labs curriculum is maintained on [GitHub](https://github.com/nre-learning/nrelabs-curriculum). As is the case with many open source projects, contributing to the NRE Labs curriculum involves a workflow called "Fork and Pull". This workflow involves making your own copy of the curriculum \(known as a "fork"\), making changes there, and then submitting a Pull Request to bring your changes back into the main curriculum repository.

If you're not familiar with Git, we actually [have a lesson that you might find useful](https://nrelabs.io/labs/?lessonSlug=git-version-control&lessonStage=0). It's not specific to the NRE Labs curriculum, but if you're totally new to Git, it deals with all of the fundamentals you'll need to return to this document and follow the instructions to contribute to the curriculum.

If you've followed the [First Steps](getting-started.md), you have already used the `antidote`CLI tool to bootstrap and validate your new content. It is now time to push these changes to GitHub, and open a Pull Request. This will allow you to use the [Preview Service](preview-your-changes.md) to see your new content in action, as well as eventually get this content merged into the main curriculum repository.

> Before you get started, please ensure you've [added your SSH key to your GitHub profile](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account). These instructions will assume that you've already done this, and will use SSH-based URLs for cloning and pushing commits.

## Create a Fork and Branch

The instructions in [First Steps](getting-started.md) already mentioned the creation of a "Fork", which is your own copy of the curriculum, but we'll quickly overview it again. You may have heard previously that this term has a little bit of a negative connotation in open source. In this case, it's totally fine - forking is a common way of contributing to a Github repository. In short, "Forking" creates a copy of a repository so that you can push directly to it. To do this, click the "Fork" button in the top right of any repository:

![](../.gitbook/assets/fork.png)

Next, GitHub will ask you where you want to place the fork. Remember, this is like making a copy, so it's asking where you want the copy of that repository to go. Usually, people select their own username. Doing that will result in a repository under your own GitHub username like so:

```text
https://github.com/<your username here>/nrelabs-curriculum
```

Now that you have created a fork, you need to create a **local** copy of that fork so that you can actually work with the files. This is called ["cloning" the repository](https://git-scm.com/book/en/v1/Git-Basics-Getting-a-Git-Repository#Cloning-an-Existing-Repository). There are a few ways to do this, but the easiest is to simply copy the URL of your forked repository, and type the following into a terminal window:

```text
git clone git@github.com:<your username here>/nrelabs-curriculum.git
```

This will result in a new directory at your current path called`nrelabs-curriculum`. Next, enter this directory and create a new branch \(replacing `new-branch-name`with the name of your choice\):

```text
cd nrelabs-curriculum/
git checkout -b new-branch-name
```

## Commit and Push

Once you've made some changes, you might be wanting to save your progress in Git so that you can track your progress. It's generally good practice to [`make commits`](https://git-scm.com/book/en/v1/Git-Basics-Recording-Changes-to-the-Repository#Committing-Your-Changes) somewhat often so that if you make mistakes, you can roll back easily.

Once you've made some commits, you'll want to `push` them. This ensures that the branch you have locally is replicated to your fork:

```text
git push origin <your branch>
```

## Create a Pull Request

Once you have commits pushed, you can open a Pull Request, which is a way of saying "I have changes in my fork that I would like you to pull into the main repository". You can do this immediately, or after you feel like you're finished with the work. Opening a Pull Request early, before you're finished with the work, is totally fine, as any subsequent commits pushed to your branch will update the Pull Request. In addition, there are ways to open a Pull Request that lets folks know you're not quite finished with the work - this is totally fine, and in fact encouraged.

> Again, if you haven't read the [NRE Labs Curriculum Standards](https://github.com/nre-learning/nrelabs-curriculum/blob/master/CONTRIBUTING.md), please do so now. If you haven't posted this elsewhere, your Pull Request description **must** provide an outline of intended content. This will make it much easier for maintainers to help you build the best content possible.

If you navigate to the GitHub page for your fork, you'll notice that there's a little bar that says you're X commits ahead of the main repository, with some buttons next to it that let you open a Pull Request:

![](../.gitbook/assets/branchchanges.png)

Make sure the correct branch is selected in the drop-down to the left, and then click "Pull Request" on the right. This will take you to the upstream repository to open a new Pull Request:

![](../.gitbook/assets/pullrequest.png)

Be descriptive here - let folks know what you're working on and what state it's in. Feel free to use the description to summarize any outstanding work you have to do, if you're not quite finished.

## Fixing Problems

When you open a Pull Request, there are a number of automated processes that take place. First, a series of automated checks run on your contribution to ensure it meets basic technical standards. The Antidote CLI tool is used to validate the syntax of all curriculum resources, and a few additional scripts kick off to do basic housekeeping things like ensuring the CHANGELOG is updated.

If any of these checks fail, the GitHub status checks will indicate this failure. Reviews or automated reviews won't take place until these checks pass, so if you see a failure, click through to the TravisCI build information to see where the failure happened.

![](../.gitbook/assets/screenshot-from-2020-04-20-15-45-57.png)

Once your Pull Request is open, you're ready to start using the [Preview Service](preview-your-changes.md) to see a live preview of your changes.

