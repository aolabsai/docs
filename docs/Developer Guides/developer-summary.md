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
    Jump straight into the steps to spinning up your own Agents.
  pages:
    - type: basic
      slug: building-your-own-agents
      title: Quick Start Steps
---

Traditionally, AI is built with a lot of training data that defines the input and objective of the model, such as using prior text to predict the next token with ChatGPT or moving towards victory based on the state of a board with AlphaGo. Instead, with our library or api, you can build AI Agents that learn continously and semi-autonomously through instinct-like triggers. 

Continuous learning with our library comes from the smaller difference between training and inference with a weightless neural network approach. With this, your application can continuously train agents as they're used and tune each agent to distinct users and purposes. For your end-users, the result is a more personalized AI experience, because you can create unique Agents for each user to train their own separately.

Learning semi-autonomously is a more advanced feature and occurs through instinct-like triggers instead of labels (you can think of instincts as triggers for a method for the Agent to apply its own label). [The research and concept behind our approach is described here](https://docs.aolabs.ai/docs/concept).

**How it works:** You build Agents by first specifying how many input and output neurons you need to model your data, how they're connected, and how they learn in an Arch, and then you can run Agents on your data, through one method/API call for training and inference. Our [Quick Start Steps](doc:building-your-own-agents) walk you through this.


> 🚧 At v0.1.4, building with our AI is easy but unorthodox, especially compared to using a pre-trained model or LLM, so roll up your sleeves-- we're doing foundational work here.
