# Preview Your Changes

> Note also that this service will only work once all of the image requirements for your content have been satisfied. If you are planning to add or modify curriculum endpoint images, please read "[NRE Labs Endpoint Images](../other-resources/nre-labs-endpoint-images.md)" first, as this must be handled separately, before any content contributions can be made. This preview service will not work properly unless this is done.
>
> Please [post to the forums](https://discuss.nrelabs.io/c/antidote-support/5), or to the relevant Pull Request if you have issues with this documentation or the preview service.

The NRE Labs curriculum repository is powered by a helpful "Preview Service". This is designed to make it easy to see your new content in action before it's merged to `master`, by building a fully functional version of the NRE Labs site on your own subdomain, using your branch/fork. This is the only officially supported mechanism for previewing NRE Labs contributions, not only because of its simplicity \(all you need to do is open the PR\) but also because it allows you to preview content that makes use of the full catalog of Endpoint Images in the NRE Labs curriculum \(some of these contain commercial software and are not publicly available for download\).

There are a few things that are required before this part of the pipeline becomes useful/usable:

* All images used by your lesson must have already been merged to `master` and available via the nightly build. If not, please see "[NRE Labs Endpoint Images](../other-resources/nre-labs-endpoint-images.md)" for more.
* Your branch of the curriculum must pass all CI checks. This includes a set of tests for ensuring the CHANGELOG is updated, basic spellchecks pass, and that the curriculum passes Antidote validation tests. This will appear as a set of checks by TravisCI near the bottom of the conversation pane in your Pull Request.

If any of these are not true, the remainder of this document, and the preview service in general will not be useful for you. So please ensure these prerequisites have been met first before continuing - otherwise any generated previews may not work properly, or may not be generated at all.

Once all of the above have been addressed, the NRE Labs Preview Service will automatically generate a live preview of your changes, and post these details via a comment in your Pull Request.

![](../.gitbook/assets/screenshot-from-2020-04-20-15-45-39.png)

Provided the above requirements continue to be met, you can continue to push commits to your pull request, and previews will be generated for you. This allows you to easily iterate on your content within the pull request, and see your updates quickly.

## Identifying Issues

If you expand the `Details` drop-down in the preview bot comment, you'll notice a few links to additional resources that may help you troubleshoot any problems with your lesson:

* **Logs** - this is a link to a GitHub Gist that contains logs from all of the various antidote components, such as antidote-core. This may provide some answers if you are not able to see your content in the preview instance's lesson catalog.
* **Inspect Traces** - this is a link to a [Jaeger](https://www.jaegertracing.io/) instance which collects traces on interactions with the provisioned instance of Antidote for your content. If you are able to see your content in the preview instance's lesson catalog, but are encountering some kind of problem when trying to launch a lesson, this may contain useful information.



