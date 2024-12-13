---
title: vs Reinforcement Learning
excerpt: RL is our closest cousin and warrants a deeper look
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Status Quo -- Extrinsic Reinforcement, Supervised-Learning, Pre-Training

In reinforcement learning, the reward or loss function is ex machina to the learning Agent; see the diagram below from the [Reinforcement Learning Gymnasium project](https://gymnasium.farama.org/content/basic_usage/#:~:text=The%20classic%20%E2%80%9Cagent%2Denvironment%20loop%E2%80%9D%20pictured%20below%20is%20simplified%20representation%20of%20reinforcement%20learning%20that%20Gymnasium%20implements.), an off-shoot of OpenAI.

**In effect,** the reward is determined by a human-set loss or objective function (eg. Pong: -1 point if ball lands outside, +2 points if scores on opponents side, etc.). 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/779485a-Artboard_163x.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "400px"
    }
  ]
}
[/block]

### Effectiveness & Limitations

RL Policies tend to work as well as we can measure the environment and score it (eg. why AlphaGo was possible; Go scores can be calculated and the whole game state is visible). In this way, RL mimics aspects of evolutionary learning, that which ultimately resolves into our genes, context-free (like weights of a deep RL system).

## Our Approach-- Intrinsic Reinforcement, Self-Learning, Live-Training

Our approach is a different perspective. It enables Agents that learn via induction in that the reward comes from their own methods, representing the Agent as referent in the learning, grounding the learned input-output associations.

**In effect**, the reward is determined by an Agent's lookup table, which is an Agent's past history of states, annotated by C-neurons as pain or pleasure for negative or positive reinforcement. 

- The human designer determines the Agent's reward function **_at once remove_**, through pre-setting the C neurons.  
- The reward is a function of the C neurons and an Agent's live experience in an environment, allowing it to be live-trained, as any activations of C neurons (like instincts) will trigger the Agent to self-associate by adding the observation-action (input-output) pair associated with its C activations to its lookup table (to repeat if pleasurable and avoid if painful).
- Human control at a higher level of abstraction through Agent learning at lower level.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f40bf07-Artboard_173x.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "500px"
    }
  ]
}
[/block]

### Effectiveness & Limitations

AO Agents tend to work as well as the Agent Arch reflects its environmental application. If that sounds circular, it's because it is-- we need to be thoughtful about how to design an Agent, or otherwise search through many, many Agent designs (hello again, evolution). However, given a proper Arch, an Agent's learning mimics aspects of learning in singular lifetimes, that which ultimately resolves somewhere in the individual being of the Agent (its brains, feelings, bodies), preserving the Agent as part of the learning, capturing the context.

## Building AI Top-Down vs Bottom-Up

In a sense, we're talking about symbolic AI vs pure connectionist systems, as our Agents have a definite symbolic shape defined in their Arch while also being neural networks. Approaching AI this way requires thoughtfulness regarding the design of the Agent --that its Arch reflects its environmental application-- instead of models hinged on training data.

That we're talking about a hybrid symbolic-connectionist approach implies a bottom-up direction to our development, as we need to build from the bottom-up, iteratively from simple agent Archs, like our _hello, world_ clam-level Agent to more complicated varieties. Phylogenetics is a helpful guide here.