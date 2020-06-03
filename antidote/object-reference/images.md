# Images

To understand images within NRE Labs, the first place you should probably look is the set of [existing images in the NRE Labs curriculum](https://github.com/nre-learning/nrelabs-curriculum/tree/master/images). Familiarize yourself with the images that are there, and take a look at what they have in common.

Next, you should read the document on [NRE Labs Endpoint Images](../../other-resources/nre-labs-endpoint-images.md) to understand some of the higher-level principles and processes for Images within the NRE Labs curriculum. This document will assume you've read that and have decided to build your own image.

Once finished with this document, you can open a Pull Request to the NRE Labs curriculum to add a new folder to the [images directory,](https://github.com/nre-learning/nrelabs-curriculum/tree/master/images) with all of the files mentioned below.

## Building an Image

In Antidote and NRE Labs, Endpoint Images are just Docker images that we use within the context of a lesson. As a result, the vast majority of what you need to know to build an Endpoint image is contained in any reasonable Docker tutorial, especially content that focuses on building images. For now, start with tutorials like the ones below, and learn the basics of Docker images:

* [Docker: Getting Started](https://docs.docker.com/get-started/)
* [Dockerfile Best Practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)
* [Interactive Katacoda Lesson on Docker](https://www.katacoda.com/courses/docker/2)

Some tips for building an image:

* **Keep it lightweight** - don't import the entire internet into your image. If your image needs more than 4GB of memory to run, and more cores than you have fingers, you've made a wrong turn. Include only that which is nece
* **Keep it simple** - Endpoints in NRE Labs are for learning - they're not meant to be highly-available or fault-tolerant. Deploy the simplest version of your software when building images - the [StackStorm](https://github.com/nre-learning/nrelabs-curriculum/tree/master/images/stackstorm) image is a good example of this - all services running in a single container. This is **fine**.
* **Use trusted, lightweight base images** - Default to using trusted images like `debian` or `centos` as your base image. This not only helps to keep image size down, but also helps us keep a handle of what's running in our images. Use [multi-stage builds](https://docs.docker.com/develop/develop-images/multistage-build/) if you need to keep the final image size to a reasonable number.
* **Include the entire source** - in addition to the required files listed below, any scripts, configs, or misc. files needed to run "docker build" must be provided in any Pull Request. The only exception to this is [Large or Sensitive Files](images.md#large-or-sensitive-files).

Note also that in most cases, images need to be built to be interactive. Anything configured within the [Endpoints](lessons/endpoints.md) and [Presentations](lessons/presentations.md) sections of a lesson definition will require some kind of network access, such as a running HTTP or SSH server. Even lesson endpoints that don't have explicit presentations will still have some kind of server, such as an API. Make sure you've considered this in building your image - some kind of network access will be necessary at runtime.

## Required Files

There are a few extra files needed by every image that are specific to NRE Labs:

### Makefile

Images are automatically built using our back-end CI/CD workflows, and require a Makefile to be put in place that supports a particular way of being called. You may include steps of your own if needed, but at a minimum, the Makefile **must** contain the following \(please insert your own image name\):

```text
# SHELL=/bin/bash

TARGET_VERSION ?= latest

all: docker

docker:
	docker build --pull --no-cache -t antidotelabs/<image name here>:$(TARGET_VERSION) .
	docker push antidotelabs/<image name here>:$(TARGET_VERSION)
```

### Dockerfile

All images must also come with a [Dockerfile](https://github.com/nre-learning/nrelabs-curriculum/blob/master/images/utility/Dockerfile). This allows us to build our own image, rather than directly using a third-party image. All necessary steps to customize this base image should be done here.

### Image Definition

To use an image within NRE Labs, images must come with a meta-data file called `images.meta.yaml`. This is similar to the [meta-data file for lessons](lessons/) but much simpler.

The best way to create a new image definition is using the [`antidote` command-line interface](../the-antidote-cli/), using the `antidote image create` subcommand. This will walk you through an interactive wizard that creates a new image definition with all the relevant fields. Note that this doesn't automatically provide any other required files, like Makefiles or Dockerfiles. You're still on the hook for doing this.

Read the below for an example image definition, with comments in-line:

```yaml
---

# Uniquely identify the image
slug: stackstorm

# Brief description of the image
description: stackstorm

# Should this image be run with privileges? (assume no)
privileged: false

# Username and password for connecting via an SSH presentation
sshUser: antidote
sshPassword: antidotepassword

# Username and password used for configuration scripts
configUser: antidote
configPassword: antidotepassword

# List of network interfaces for this image
networkInterfaces:
  - 'eth0'
```

## Large or Sensitive Files

Occasionally, such as for [commercial software](../../other-resources/nre-labs-endpoint-images.md#commercial-software), we need to include sensitive files in the build process. This might be a commercial network operating system image, or perhaps a license file.

If your image requires a large file \(pretty much anything over 10MB\) that already exists somewhere else on the internet, rather than trying to put it in the lesson directory, add a step to your Dockerfile or Makefile to download those files from their original location \(preferably with integrity verification using SHA256 hash or similar\). 

If you have a large or sensitive files you wish to include in an NRE Labs image, but don't want those files to be publicly available, the NRE Labs project also maintains a private cloud storage bucket that is accessible only within our build system, and these are downloaded during the build process. [Get in touch with us](https://discuss.nrelabs.io/) and we'll help you figure out a way to get these into the curriculum safely.

