---
title: Building an Architecture
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: architecture-for-mnist
      title: Architecture for MNIST
    - type: basic
      slug: building-an-agent
      title: Building an Agent
---
An Arch, short for neural architecture, defines how an agent is configured. This definition consists of the input and output structure and how the agent's neurons are connected to each other.

Defining inputs and outputs is simple-- the two primary variables you use here are `arch_i` and `arch_z`. `arch_i` defines the input structure and `arch_z` defines the output structure. They both expect lists of numbers of neurons in channels; channels represent a class of features as groupings of neurons, eg. if one of your inputs is cars, then 10 neurons can encode for 2^10=1048 different cars, and if your output is rating then 10 neurons can encode for 0-100%. In cases where your data model does not have clear features, you may not need channels and a list with a single integer using something like `[10]` will work fine. The total number of input and output neurons is the sum of the integers in their list.


```python python
from ao_core import Arch

arch = Arch(
  arch_i,
  arch_z,
  connector_function="full_conn",
  connector_parameters=(),
  description=""
)
```

The first things we need to figure out when building an agent is how inputs and outputs are structured. When we're feeding data into the agent or reading the output, depending on the case we may convert to/from other types, such as to/from ints.

`arch_i` describes how inputs to the agent are structured, a list of integers is expected, for example `[5]` if we simply want 5 neurons or if we want multiple channels `[5, 5, 5]`.

`arch_z` describes how outputs from the agent are structured, again a list of integers is expected, e.g. `[4]`.

`connector_function` determines how connections are formed between neurons, there are a couple predefined options you can choose from, or you can try writing one yourself. The default and simplest option here is `full_conn`, which is a good place to start when trying things out with an Arch and agents.

`connector_parameters` are arguments for the connector function, which are used in forming connections between neurons.

`description` is a string description you can attach to an Arch, it does not affect Arch or Agent behavior.

> 📘 Designing your own Arch is quite simple. You can view some [visual representations of Archs in our template editor](https://miro.com/app/board/uXjVM_kESvI=/?share_link_id=677487521831) to get started.
