---
title: How Architectures Work
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
> 🚧 Work in Progress is strong here
>
> This class is currently not well defined at all and is very manual right now. Not even sure if it’s the right data structure. We’ve included 2 architectures in our repo to start things off (for the 9-neuron basic clam and for 1573-neuron MNIST arch). Please modify those files to make custom architectures; we’d be very curious to see what you come up with, and if it can be helpful in refining the core code and Architecture class especially.

Agents are made of up 4 core layers that determines the overall topology:

Input layer - agent.arch.I - number of neurons determined by application input data (eg. 3 for the basic clam, or 28x28 for MNIST).

Inner Layer - agent.arch.Q - usually mirrors agent.arch.I in topology

Outer Layer - agent.arch.Z - number neurons and their shape determined by application output needs

Control Layer - agent.arch.C - analogous to instincts; C neurons fire according to designer set triggers (eg. in the basic clam, with input FAC, if F=food, a C control neuron could be \{if agent.arch.I[F] > x, C = 1} )

This information is stored in the arch file; "neuron shape" refers to the connections of neurons.
