---
title: ao.Agent.state
excerpt: >-
  ***attribute*** :  `ao.Agent.state`


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
Stores the count of the current state as an integer.

The value is incremented by the `.next_state` method.

# Example
[block:code]
{
  "codes": [
    {
      "code": ">>> agent.state\n10\n\n>>> angent.next_state(INPUT)\n>>> agent.state\n11\n",
      "language": "python"
    }
  ]
}
[/block]