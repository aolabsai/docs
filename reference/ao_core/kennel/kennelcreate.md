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
A Kennel is a collection object used to keep track of Agents in our API and associated cloud (AWS) backend; Agents are child to a Kennel.

Kennels are initialized with with an Arch, which you provide through a raw Github link, like this [example for our Basic Clam Agent](https://gist.github.com/mi3law/8012fc6e6adceab35d03fd3e5da8db34#file-0_basic_clam-py) for the `arch_URL` parameter.

> 📘 Start with a reference design
> 
> You can find 2 more Archs to fork and modify to suit your application in our [open ao_arch repo](https://github.com/aolabsai/ao_arch/blob/main/Architectures/0_basic_clam.py).//

What goes into an Arch and how do you create one? [Read our Archs guide](https://docs.aolabs.ai/docs/arch).

> 🚧 Need help?
> 
> Designing an Arch is a unique step in our approach; usually you're using a pre-trained model, or at best tuning some hyperparameters. [Reach out if you need any sort of help!](https://discord.gg/nHuJc4Y4n7)