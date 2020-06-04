# Connections

In Antidote, [Lesson Endpoints](endpoints.md) are spun up as containers within a Kubernetes cluster. As a result, they all have a single `eth0` network interface by default. However, as NRE Labs is designed to teach complex infrastructure topics, often a single network interface is not enough. This document will explain how we use a concept called "Connections" to provide multiple interconnections directly between Lesson endpoints.

Imagine you have a lesson definition with three endpoints: `vqfx1`, `vqfx2`, and `vqfx3`. You can think of these like nodes in a graph topology, as all networks are. So, if Endpoints are nodes, then the edges, or the connections between these nodes, are `connections`:

```text
connections:
- a: vqfx1
  b: vqfx2
- a: vqfx2
  b: vqfx3
- a: vqfx3
  b: vqfx1
```

This is a simple list of connections from `a` to `b`. The first connection is from `vqfx1` to `vqfx2` and so on. Antidote will create virtual networks for each Connection, and then attach Endpoints to them.

## How will these networks show up in my lesson?

The way these networks will be made available will depend on how the image is built. If a native container, `net1`, `net2`, and so forth. If a VM-in-container, it could be anything. In the future we may go with a solution like Kata containers by default, which could also add a wrinkle.

At the moment, the best place to know which network interfaces will be available to you is to consult the the image metadata files, which includes a list of network interfaces that the image makes available to be used. This is an ordered list, and interfaces are consumed in order of the Connections that reference that endpoint.



