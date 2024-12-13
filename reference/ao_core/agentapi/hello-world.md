---
title: Hello, World!
excerpt: >-
  Invoke our simplest Agent first to familiarize yourself with what an Agent can
  do
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: Go to the Agent invoke POST API call
  pages:
    - type: endpoint
      slug: agentinvoke
      title: Agent invoke
---
Our simplest Agent is a 4-neuron system we think of as a Clam.

This Agent can learn to associate 3-to-1 inputs-to-output, imagined to be like a clam faced with an input pattern of F A B to which it learns when to Open/Close, all represented in binary (hence the 4 binary neurons-- 1 for each FAB and open/close).

The first input (F) is set to trigger the Clam Agent's instincts, as Food would, so you can train it by including F=1 in the inputs \_without \_explicitly specifying an output label. The Agent self-labels-- i.e. it repeats the output that resulted in Food.

Here's a visual--

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/42221ed-Artboard_102x.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "500px"
    }
  ]
}
[/block]

**Your _Hello, World_ challenge**-- using the Agent Invoke API call or through this [front-end demo](https://aolabs.streamlit.app/) if you need a visual, can you train/retrain the Clam Agent as per your will? Can you do so using only Food (F) _instead_ of output labels?

Then you can master bigger, more evolved Agents that can self-associate beyond 3-to-1!

> 👍 9 neurons & beyond!  :rocket:
> 
> _It's just 1 config _(the Arch) to create Agents customized to the number of inputs, outputs, and reward signals in your application data model and to get started we have a \[[repo of arch reference designs](https://github.com/aolabsai/archs).

### Clam Agent Arch in Depth

The basic Clam Agent has 3 binary inputs (FAB are 1-present or 0-not present, 011, etc.) with 1 binary output (1-open or 0-closed mouth). There are also 3 binary neurons in its middle layer, and 2 neurons as the control (1 for learning with labels, 1 for learning with instincts, for 9 neurons total. [Here is a full guide on the clam's Arch,](https://docs.aolabs.ai/docs/basic-clam) and you can view or fork the [Agent Arch python file here](https://github.com/aolabsai/archs/blob/main/basic_clam.py).