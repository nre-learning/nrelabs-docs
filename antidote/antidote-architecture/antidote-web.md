# Antidote Services

The Antidote platform is composed of two services:

* `antidote-web`
* `antidoted`

Antidote-Core is where the real work gets done in the Antidote project. It's responsible for taking in lesson definitions via [a YAML file](../object-reference/lessons/) and any configs, scripts, etc used in the lesson, and providing them to the front-end via its API.

## Configuring Antidote

Antidote is configured through a YAML file. Since typically Antidote is deployed within Kubernetes, the ideal way to do this is through a ConfigMap.

If you're using [antidote-selfmedicate](https://github.com/nre-learning/antidote-selfmedicate) __to spin up an instance of Antidote yourself, a configuration file is provided for you.

\(should have a sample config file in the antidote-core repo, and just link to it here\)

