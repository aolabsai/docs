---
title: Building an Architecture
excerpt: ''
deprecated: false
hidden: true
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
In order to build an agent, we first need an architecture that will define that agent's structure. We do that with our [Arch](https://github.com/aolabsai/ao_arch) library.

```python python
from ao_arch import Arch

arch = Arch(
  arch_i,
  arch_z,
  arch_c=[],
  connector_function="full_conn",
  connector_parameters=(),
  description=""
)
```

The first things we need to figure out when building an agent is how inputs and outputs are structured. When we're feeding data into the agent or reading the output, depending on the case we may convert to/from other types, such as to/from ints.

`arch_i` describes how inputs to the agent are structured, a list of integers is expected, for example `[5]` if we simply want 5 neurons or if we want multiple channels `[5, 5, 5]`.

`arch_z` describes how outputs from the agent are structured, again a list of integers is expected, e.g. `[4]`

`connector_function` determines how connections are formed between neurons, there are a couple predefined options you can choose from, or you can try writing one yourself.

`connector_parameters` are arguments for the connector function, which are used in forming connections between neurons

`description` is a string description you can attach to an Arch, it does not affect Arch or Agent behavior.
