# Contribute Your Content

Contributing to the curriculum is fairly straightforward, but you should consider the guidance in this document to ensure you spend your time wisely. The last thing we want is for you to dedicate days or even weeks of your time to building a lesson only to find out someone is already working on something similar.

> Contributions of any kind are welcome. New lessons are cool, but so are modifications, additions, or even minor fixes to existing content. No contribution is too small!

Contributing to the NRE Labs Curriculum should follow a four-step lifecycle. This ensures that lesson quality remains high and contributors' time is not wasted.

![](https://github.com/nre-learning/nrelabs-docs/tree/09d474a672ed4021f6dac96449c0748f5acf39f0/creating-curriculum-content/assets/lifecycle.png)


## Step 3 - Put It Together

Okay. You've determined that you have a good idea for a lesson, and no one else is working on it. Let's get you started!

As is common on Github-based projects, direct commit access to the main NRE Labs curriculum repository is not permitted. To be able to commit new or modified curriculum content, you first need to [fork the NRE Labs curriculum repository](https://github.com/nre-learning/nrelabs-curriculum/fork) This allows you to create a copy of the curriculum at a location of your choosing \(usually underneath your own Github username\) that you have permissions to push to. Once you have your fork, you can clone from there and start making commits as you add or change lesson content.

Next - you'll want a local copy of the Antidote stack running locally so you can rapidly test and iterate on the changes you've made. Ironing out all of the bugs locally before you submit a pull request makes the review process much smoother. For more info, see the :ref:`selfmedicate <selfmedicate>` documentation.

Next thing you'll want to bookmark is the documentation on :ref:`curriculum definitions <curricula>`. All curriculum resources, such as lessons, are defined "as-code", meaning they are all defined using simple text files stored in Git. This documentation is vital for knowing what kind of things you can use to create an awesome lesson, so read that carefully, and follow the instructions there, whether you're creating a new lesson, or modifying an existing one.

Finally, you'll definitely want to download :ref:`syrctl <syrctl>`, the command-line tool that will serve as your best friend when contributing to the NRE Labs curriculum. With this tool, you can easily create a new lesson skeleton, or validate existing lesson content, so you don't have to wonder if you've built a lesson correctly.

At this point, you're ready to make the changes to your copy of the NRE Labs curriculum. Make commits, and push them to your fork as you see fit. Try to keep commit messages relevant and descriptive.

## Step 4 - Get It Reviewed and Merged

Eventually, you'll arrive at the point where the content you're able to see in your local copy of Antidote looks like it's ready for prime time. You've made all the changes you plan to make, and you've added them to your fork via pushed commits. At this point, you're ready to `open a pull request <https://github.com/nre-learning/nrelabs-curriculum/pull/new>`\_ \(PR\).

The link above will prompt you to specify your fork and branch you wish to "pull from" into the main NRE Labs curriculum. Select the appropriate fork and branch, and then fill out the description for the pull request. If you are opening this PR in response to an issue \(whether you opened it or not\) and you feel it addresses everything in that issue, you can say `Closes <insert link to issue here>` in your description, and when the PR is merged, the referenced issue\(s\) will be closed automatically.

At this point, the next step is for a reviewer to approve or make suggestions for a second round of edits for your content. Note that the goal for **each and every review** is not to nitpick or make it difficult to contribute to NRE Labs, but rather to ensure the content is reflected in the best light possible. Be patient and willing to adapt to feedback. It might be useful to take a peek at the :ref:`curriculum review standards <curriculum-reviewers>` as that covers everything that a curriculum reviewer will be looking for.

> If you are a maintainer or creator for an open source project in the infrastructure or automation space, the Antidote project would love to have you. We feel very strongly that if you're maintaining an open source project, that you should have the right of first refusal for representing it in the NRE Labs curriculum. Please get in touch with us using any of our :ref:`community channels <community>` and we'll make every effort to bring you up to speed with the environment so that you can show off your project on the site.

