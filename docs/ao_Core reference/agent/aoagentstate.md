---
title: ao.Agent.story
excerpt: >-
  ***attribute*** :  `ao.Agent.story`


  [[source](https://github.com/aolabsai/ao_core/blob/a289502a9f80a5e76581732a7938e93cef8e1363/ao_core.py#L48)]
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
A numpy array (integer data type) that stores the entire history of an agent in binary.

The shape is states by neurons; the rows of the array represent states and the number of columns is set by the total number of neurons of the agent.

# Example
[block:code]
{
  "codes": [
    {
      "code": ">>> agent.story.shape\n[100000, 9]      # using our basic clam as the example\n\n>>> agent.story[11, 2]\n[0, 1, 0, 0, 1, 1, 0, 1, 0]     # displays the 12th state of the 3rd neuron",
      "language": "python"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "The number of rows is preallocated to `100000` and is populated in descending chronological order (so the oldest state is indexed first)."
}
[/block]