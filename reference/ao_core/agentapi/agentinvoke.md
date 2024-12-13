---
title: Agent invoke
excerpt: >-
  post an input (with optional learning modes instinct and label) to agent to
  evoke its output
api:
  file: ao_core.json
  operationId: agentInvoke
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: >-
    Try our `Hello, World` Agent, pre-loaded on our API at kennel_id
    `v0.1.2dev/TEST-BedOfClams`. There's also a frontend app to get a feel for
    this Agent.
  pages:
    - type: basic
      slug: basic-clam
      title: '"Hello, World," a Clam-level AGI'
    - type: link
      title: '"Hello, World" Demo App'
      url: https://aolabs.streamlit.app/
---
From a **Kennel**, invoke a specific **Agent** with an **Input** to get its **Output**

There are 2 training modes-- manual learning with Labels or automatic learning through triggering Instincts.

### Manual Learning (via Labels)

If **`LABEL = "a label in binary"`** is provided, the Agent's Output will match the Label, and the Agent will learn to associate the Input with the Output-Label, weighted against Agents' past associations.

### Automatic Learning (via Instincts)

When **`INSTINCTS = True`**, if Input triggers Agent's Instincts, the Agent will learn to associate the current Input with *its previous Output* as from the Agent's perspective it was the previous output that lead it to the input which triggered its instincts. **In other words, training without labels! The Agent self-labels, self-associates.** 

### Training Notes:

* Labels override Instincts.
* If the trigger is positive (pleasure) then it will reinforce the associated behavior; if the trigger is negative (pain), the Agent will do the opposite of output next time, diminishing or disassociating the behavior.
* You pre-program instincts in Agent Arch, triggered by fixed/static conditions on Input or other neurons instead of pre-training; [details here](https://docs.aolabs.ai/docs/arch-config).

> 📘 Sequenced Learning
>
> By default, Agents learn sequenced or time series data-- their next move is informed by their immediate past action. 
>
> If your data are not in a stream or consistent sequence, such as a table of information (our Netbox example), then set **`US = True`** to introduce a random binary state as reset between Agent invocations.
