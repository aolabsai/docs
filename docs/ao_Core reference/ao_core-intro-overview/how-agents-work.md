---
title: How Agents Work
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
After agent instantiation, all operations are carried out at the Agent level (an Agent's Architecture is immutable). Those operations are quite simple; the main ones are listed below.

# Agent Methods

## `agent.next_state`

the main method! Given a binary string as input in the proper shape (FAC=3 for the clam, 28x28=784 for MNIST), .next_state advances the agent to the next state and returns an output. Labels, instincts, and other learning and control settings can be applied.

# Agent Attributes

## `agent.state`

counter for the agent’s current state; incremented +1 by state methods `.next_state` et al

## `agent.story`

displays the agent’s binary memory of all neuron activity (how the neurons fired, 0 or 1); a numpy array in `shape:[states, agent.arch.all_neurons]`

## `agent.metastory`

shape and indices correspond to .story however contains metadata of neuron activity (why the neurons fired; useful for debugging).

## `agent.arch`

access to the Architecture that underpins the agent

## `agent.notes`

if included during agent instantiation