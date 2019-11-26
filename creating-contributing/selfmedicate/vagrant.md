# Vagrant Environment

For maximum compatibility across operating systems, we deploy selfmedicate in a Vagrant environment, so that it can run in a consistent, properly configured virtual machine with all of the dependencies needed.

{% hint style="info" %}
Running Self-Medicate within this Vagrant environment is the only supported option today. Linux users may wish to run the Self-Medicate script directly, to bypass the first layer of virtualization.

You're welcome to go this route, of course, but you'll be on your own. You'll also want to make sure Docker, `kubectl` and minikube are all installed.
{% endhint %}

These instructions will spin up a virtual machine, so first, you'll need a hypervisor. We support [Virtualbox](https://www.virtualbox.org/wiki/Downloads) as it is widely supported across operating systems as well as the automation we'll use to get everything spun up on top of it.

Next, you'll need [Vagrant](https://www.vagrantup.com/docs/installation/). Vagrant allows us to define a virtual environment in the selfmedicate repository that automatically contains all of the software dependencies needed to make Antidote work.

{% hint style="info" %}
The Self-Medicate `Vagrantfile` starts a VM with 8GB of RAM and 2 vCPUs by default. While this is not a strict requirement, it's a reasonable default. You're free to edit this if you know what you're doing.
{% endhint %}

Vagrant's [`vagrant-vbguest`](https://github.com/dotless-de/vagrant-vbguest) __should also be installed. You only need to run this once.

```text
vagrant plugin install vagrant-vbguest
```

To start the Vagrant environment for selfmedicate, run:

```text
vagrant up
```

{% hint style="info" %}
Selfmedicate is designed to do as much work as possible up-front, so that your development experience can be as positive as possible, and this includes downloading a bunch of large-ish image files. As a result, the first time you run this command can take some time. BE PATIENT. 
{% endhint %}

Once this is done, the environment should be ready to access at the URL shown by the script.

If you need to pause your work, you can use the `vagrant suspend` command to suspend the Vagrant machine. Use `vagrant resume` when you're ready to resume.

Finally, to interact with selfmedicate, you'll need to open an SSH connection to the Vagrant machine:

```text
vagrant ssh
```

The rest of the selfmedicate instructions will take place within this environment.

