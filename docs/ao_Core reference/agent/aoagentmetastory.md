---
title: ao.Agent.metastory
excerpt: |-
  ***attribute*** :  `ao.Agent.metastory`

  [[source]]
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
A numpy array (object data type) that stores the entire associated meta-history of an agent.

The shape is the same as `agent.story`, though the information stored is not the neuron's binary state, but the associated metadata in text strings.

Presently metastory is not exposed in the API; request it and we'll re-prioritize.