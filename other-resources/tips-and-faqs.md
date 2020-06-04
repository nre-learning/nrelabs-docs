# Tips and FAQs

## How are you running network devices in this thing?

Everything in Antidote is executed in Kubernetes, so everything has to be a container. On the surface, this may seem like a barrier to being able to run virtual networking images, which are commonly available as virtual machines. Indeed, a common misconception is that the two models are mutually exclusive, but they're not.

At the end of the day, a container is just a highly configured process, and QEMU can execute virtual machines easily with a single command. We build all of this into a container image, so that in essence, when the container is started, the virtual machine is started as well.

See :ref:`architecture <architecture>` for more details on this and other aspects of images within Antidote.

## Do you only support Junos?

Definitely not. In fact, the underlying Antidote platform doesn't care at all what operating system a lesson endpoint uses, only that it's accessible via the ports described in a [Presentation](../antidote/object-reference/lessons/presentations.md).

[As of v1.1.0](https://github.com/nre-learning/nrelabs-curriculum/releases/tag/v1.1.0), the NRE Labs curriculum includes and makes use of a Cumulus VX image as well, and we have plans to add even more in the near future. Any other networking vendor that is interested in donating a virtual image for their kit and is willing to abide by the project's [governance document](https://github.com/nre-learning/proposals/blob/master/governance.md) and the [code of conduct](https://github.com/nre-learning/proposals/blob/master/codeofconduct.md) is welcome to participate in the project.

## 

