---
title: Create kennel
excerpt: Upload an Arch to spawn Agents
api:
  file: ao_core.json
  operationId: kennelCreate
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: Run Agents from your newly created Kennel using the invoke API call
  pages:
    - type: endpoint
      slug: agentinvoke
      title: Agent invoke
    - type: basic
      slug: arch
      title: About Arch
    - type: link
      title: Archs repo & reference designs
      url: https://github.com/aolabsai/archs
---
A Kennel is a collection object used to keep track of Agents in the API and cloud backend; Agents are child to a Kennel.

kennels are created with a set of parameters defining their structure and how neurons are connected to each other.
- `arch_i` is a list of numbers of input neurons. Input neurons can be grouped in channels so you could have an arch_i of `[10]` or `[2, 3, 5]`.
- `arch_z` is a list of numbers of output neurons. Output neurons can also be grouped in channels so you could have an arch_z of `[10]` or `[2, 3, 5]`.
- `connector_function` is the method of connecting neurons
- `connector_parameters` are parameters for the connector function, these depend on the function as some take no parameters

> 📘 Start with a reference design
>
> You can find 2 more Archs to fork and modify to suit your application in our [open ao\_arch repo](https://github.com/aolabsai/ao_arch/blob/main/Architectures/0_basic_clam.py).//

What goes into an Arch and how do you create one? [Read the Archs guide](https://docs.aolabs.ai/docs/arch).

> 🚧 Need help?
>
> Designing an Arch is a unique step in our approach; usually you're using a pre-trained model, or at best tuning some hyperparameters. [Reach out if you need any sort of help!](https://discord.gg/nHuJc4Y4n7)
