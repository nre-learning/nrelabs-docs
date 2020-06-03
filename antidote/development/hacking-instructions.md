# Hacking Instructions

There are two main components to the Antidote platform:

* Antidote-web
* Syringe

These are separate mostly because they use very different technologies, and therefore have very different processes for getting up and running with the code. Read on for details:

### Hacking on Antidote-web

[Antidote-Web](https://github.com/nre-learning/antidote-web) is Antidote's web front-end. It's the user interface through which the learning takes place.

This is a part of the project undergoing some severe changes currently, and if you're interested in getting involved, it's best to reach out on our community forums, and someone will help you out. Stay tuned for more detailed development info to be posted here.

### Hacking on Antidote-Core

TBD - while antidoted normally relies on kubernetes to operate, you can disable the scheduling service via config if you want to do some API testing.

antidoted needs nats at dev time

```text
docker run --rm -d -p 4222:4222 -p 6222:6222 -p 8222:8222 --name nats-main nats
```

[Antidote-core](https://github.com/nre-learning/syringe) forms the collection of back-end services that provide orchestration for lesson resources, while providing an API for the web front-end to consume.

To build antidote-core, you'll need to install the version of Go specified in [the Dockerfile](https://github.com/nre-learning/syringe/blob/master/Dockerfile#L1). While other versions of Go **should** work, the version listed there is the currently/officially supported version.

Within the antidote-core repository, compile binaries with:

```text
make
```

You can also run tests with:

```text
make test
```

You can also build the antidote-core docker container with:

```text
make docker
```

