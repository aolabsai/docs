---
title: ao_core Intro
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
Traditionally to build AI, one must provide a lot of quality training data that defines the objective of the model (eg. with chatGPT, the objective is to predict the next token). Instead, with our code, you build AI agents that learn more autonomously, through their own methods of acquiring training data (instinct methods); like animals, they learn against their past experience of reward.

The result is AI that **continuously learns** while maintaining **training transparency (not a blackbox)** and is small enough to **run locally**. For your endusers, the result is a personalized AI experience they can trust like their pets.

Building our AI is easy-- you build agents (by specifying their neurons, connections, instincts) and then run them on your data (abstracted as an environment for the agents, depending on your data). Building this into your app is an effort we'll support any way we can-- thank you for building with us! We need the feedback.

There are only 2 primary classes and 1 method involved in building AIs of the AO Labs sort--

## Building Agents

### `ao.Agent`

a class which creates an agent given an architecture.

### `ao.Arch`

a class used to specify the number and type of neurons, their topology, and their connections; like a fixed configuration file for each agent.

An agent is an instantiation of ao.Agent class necessarily initialized with an ao.Arch instance, as follows:

`agent = ao.Agent( arch, notes=[] )`

## Using Agents

When you have an agent, it can be given inputs and will return outputs, all in binary; it will learn by changing its inner lookup table according to its instincts or labelled data through the following method--

### `agent.next_state( )`

Both training and inference/application happen through the .next_state method. If a LABEL is included with the input, or if the INPUT triggers any of the agent's instincts, learning occurs in the affected neurons, as follows:

`agent.next_state( INPUT, LABEL=[] )`