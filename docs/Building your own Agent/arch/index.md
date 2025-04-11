---
title: About Arch
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
An Arch, short for neural architecture, defines how an agent's structure. This definition consists of the input and output structure and how the agent's neurons are connected to each other.

Defining inputs and outputs is simple, the two primary variables you use here are `arch_i` and `arch_z`. `arch_i` defines the input structure and `arch_z` defines the output structure. They both expect lists of numbers of neurons in channels, channels are groupings of neurons within the architecture they matter more for some connector functions than others. In cases where you don't need channels you can have a list with a single integer use something like `[10]`.The total number of input and output neurons is the sum of the integers in their list.

[Connector functions](doc:connector_functions) determine how neurons are connected. The simplest option here is `full_conn`, which is a good place to start when trying things out with an Arch and agents

Configuring your own Arch is quite simple. You can view some [visual representations of Archs in our template editor](https://miro.com/app/board/uXjVM_kESvI=/?share_link_id=677487521831) to get started.
