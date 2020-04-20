# Contributing Your Content

Once you've followed the previous steps, you're ready to actually build a lesson and contribute it upstream.

> Contributions of any kind are welcome. New lessons are cool, but so are modifications, additions, or even minor fixes to existing content. No contribution is too small!

## Content Development

You'll want a local copy of the Antidote stack running locally so you can rapidly test and iterate on the changes you've made. Ironing out all of the bugs locally before you submit a pull request makes the review process much smoother. This was covered in the previous step.

Next thing you'll want to do is bookmark the [Antidote Object Reference](../../antidote/object-reference/). All curriculum resources, such as lessons, are defined "as-code", meaning they are all defined using simple text files stored in Git. This documentation is vital for knowing what kind of things you can use to create an awesome lesson, so read that carefully, and follow the instructions there, whether you're creating a new lesson, or modifying an existing one.

Finally, you'll definitely want to download [`syrctl`](), the command-line tool that will serve as your best friend when contributing to the NRE Labs curriculum. With this tool, you can easily create a new lesson skeleton, or validate existing lesson content, so you don't have to wonder if you've built a lesson correctly.

At this point, you're ready to make the changes to your copy of the NRE Labs curriculum. Make commits, and push them to your fork as you see fit. Try to keep commit messages relevant and descriptive.

## Get It Reviewed and Merged

Eventually, you'll arrive at the point where the content you're able to see in your local copy of Antidote looks like it's ready for prime time. You've made all the changes you plan to make, and you've added them to your fork via pushed commits. At this point, you're ready to [open a pull request](https://github.com/nre-learning/nrelabs-curriculum/pull/new).

The link above will prompt you to specify your fork and branch you wish to "pull from" into the main NRE Labs curriculum. Select the appropriate fork and branch, and then fill out the description for the pull request. If you are opening this PR in response to an issue \(whether you opened it or not\) and you feel it addresses everything in that issue, you can say `Closes <insert link to issue here>` in your description, and when the PR is merged, the referenced issue\(s\) will be closed automatically.

At this point, the next step is for a reviewer to approve or make suggestions for a second round of edits for your content. Note that the goal for **each and every review** is not to nitpick or make it difficult to contribute to NRE Labs, but rather to ensure the content is reflected in the best light possible. Be patient and willing to adapt to feedback. It might be useful to take a peek at the [curriculum review standards](curriculum-standards.md) as that covers everything that a curriculum reviewer will be looking for.

> If you are a maintainer or creator for an open source project in the infrastructure or automation space, the Antidote project would love to have you. We feel very strongly that if you're maintaining an open source project, that you should have the right of first refusal for representing it in the NRE Labs curriculum. Please get in touch with us [on the community forums](https://discuss.nrelabs.io) and we'll make every effort to bring you up to speed with the environment so that you can show off your project on the site.

