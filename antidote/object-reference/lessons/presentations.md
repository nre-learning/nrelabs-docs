# Presentations

At this point, hopefully you understand how :ref:`Endpoints <endpoints>` provide a basis for creating an interactive learning experience. However, there's no interactivity unless those Endpoints are made accessible somehow to the learner. Enter Presentations.

## Defining a Presentation

You can specify a list of Presentations on an Endpoint to indicate how you want that Endpoint to be "presented" to the learner. A simple example is shown below. In this case, we're offering a single Presentation for an Endpoint, that provides SSH terminal access to that endpoint over port 22:

```text
endpoints:
- name: linux1
  image: antidotelabs/utility
  presentations:
  - name: cli
    port: 22
    type: ssh
```

As you can see, each Presentation in the list has three fields for you to specify:

* `name` - The name of the presentation. This can be whatever you want, as long as it's relatively short and

  unique for that endpoint.

* `port` - The port that Antidote should use to access the container for this Presentation.
* `type` - This controls the type of presentation being offered. Currently supported options are `ssh` and `http`.

You can get creative with Presentations. First and foremost, you probably noticed that the `presentations` attribute is plural form, and provided as a YAML list. This is because you can have multiple Presentations to the same Endpoint:

```text
endpoints:
- name: linux1
  image: antidotelabs/utility
  presentations:
  - name: cli1
    port: 22
    type: ssh
  - name: cli2
    port: 22
    type: ssh
  - name: web
    port: 80
    type: http
```

These will all be shown as individual tabs in the web front-end, and they will be disambiguated via their Presentation name. For instance, the example above will result in tabs `linux1-cli1`, `linux1-cli2`, and `linux1-web`.

Finally, in some cases you don't want **any** presentations. A common example of this is some kind of endpoint that you need to access from another Endpoint via REST API. You want to provide a Presentation to the user to execute some kind of tool or script, but the Endpoint offering the REST API merely needs to exist in the environment and respond to queries.

In this case, merely omit the `presentations` field entirely, but note that in this case`additionalPorts` becomes a required field, and must specify at least one port.

```text
endpoints:

- name: linux1
  image: antidotelabs/utility
  presentations:
  - name: cli
    port: 22
    type: ssh

- name: restapi
  image: antidotelabs/utility
  additionalPorts: [80]
```

Because the above Endpoint `restapi` didn't have any presentations, we needed to ensure at least one port was provided in `additionalPorts`. The learner can then access the `linux1` endpoint and use the tooling in that Endpoint to access the REST API of `restapi`.

## Presentation Options

There are some implementation details for each of the available presentation types specified in the `type` field that you should be aware of.

### SSH

**Usage:** `type: ssh`

This one is pretty straightforward. A very common use case for interacting with Endpoints is to provide an interactive CLI \(Command Line Interface\) terminal in the Antidote front-end. This is accomplished by connecting directly to the Endpoint via SSH, and using that connection to provide the experience to the web.

As long as your Endpoint is configured to listen on the port you specify in the Presentation for SSH connections with the username `antidote` and `antidotepassword`, Antidote will take care of connecting it to the user on the front-end.

### HTTP 

**Usage:** `type: http`

Not all content is best shown via the CLI. Sometimes you want to be able to show some kind of web-based portal that's running on an Endpoint, such as a self-service application, which interacts with other Endpoints on the back-end.

In this case, the `http` type can be used. A tab will be opened for this Presentation, but instead of a terminal, the tab contents will show the web application you provide in the Endpoint \(in an `iframe`\). A few considerations for this option:

* HTTPS is not currently supported. We need to iron out a few wrinkles in the implementation first, and we'll support either protocol, very soon. For now, use HTTP, and the Antidote load balancer will serve the content from a reverse proxy that provides HTTPS.



