# Hacking Instructions

There are two main components to the Antidote platform:

* Antidote-web
* Syringe

These are separate mostly because they use very different technologies, and therefore have very different processes for getting up and running with the code. Read on for details:

### Hacking on Antidote-web

[Antidote-Web](https://github.com/nre-learning/antidote-web) is Antidote's web front-end. It's the user interface through which the learning takes place.

This is a part of the project undergoing some severe changes currently, and if you're interested in getting involved, it's best to reach out on our community forums, and someone will help you out. Stay tuned for more detailed development info to be posted here.

### Hacking on Syringe

[Syringe](https://github.com/nre-learning/syringe) is an application written in Go which provides orchestration for lesson resources on Kubernetes, while providing an API for the web front-end to consume.

To build Syringe, you'll need to install the version of Go specified in [Syringe's Dockerfile](https://github.com/nre-learning/syringe/blob/master/Dockerfile#L1). Whatever version of Go is used there, is the currently/officially supported version.

Once done, enter the Syringe repository. There are a few things you can do here. To simply compile Syringe binaries, including `syrctl` and all of the server-side binaries, run:

```text
make
```

You can also execute Syringe's tests with:

```text
make test
```

This is the same command executed by the CI pipeline, so this is a good way to know if your tests will pass before actually pushing anything.

You can also build Syringe's docker container with:

```text
make docker
```

This includes a `docker push` step, so if you want to push this image to your own repository for testing, you'll need to edit the push target, or comment that line out in the Makefile.

