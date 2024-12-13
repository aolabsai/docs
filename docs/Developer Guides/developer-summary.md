---
title: Developer Summary
excerpt: Get started with our AI as a developer
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: >-
    Familiarize yourself with our approach to AI by trying our `Hello, World`
    toy application, a clam-level general intelligence.


    Or jump straight into the steps to spinning up your own Agents.
  pages:
    - type: basic
      slug: basic-clam
      title: '"Hello, World," a Clam-level AGI'
    - type: basic
      slug: building-your-own-agents
      title: Quick Start Steps
---
Traditionally, to build AI, one must provide a lot of quality training data that defines the learning objective of the model (eg. with ChadGPT, the objective is to predict the next token, or a AlphaGo with its objective of victory in Go). Instead, with our code, you build AI Agents that learn 1) continuously, with no gap between training and inference, and even 2) autonomously, through instinct-like triggers instead of labels (you can think of instincts as triggers for a method for the Agent to apply its own label). [The research and concept behind our approach is described here](https://docs.aolabs.ai/docs/concept).

The potential for your application is to add a weightless AI layer that continuously learns, so you can train it on local or individual end-user data, while also maintaining training transparency (not a blackbox). For your end-users, the result is a more personalized *and tunable* AI experience, because you can create unique Agents for each one to train their own separately.

**How it works:** You build Agents by first specifying how many input and output neurons you need to model your data, how they're connected, and how they learn (through labels or instinct-like triggers) in an Arch, and then you can run Agents on your data, through one method/API call for training and inference. Our [Quick Start Steps](doc:building-your-own-agents) walk you through this.

> 🚧 At v0.1.2, building with our AI is easy but unorthodox, especially compared to using a pre-trained model or LLM, so roll up your sleeves-- we're doing foundational work here.
