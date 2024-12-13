---
title: Conceptual Summary
excerpt: >-
  A deeper explanation of our approach to AI at aolabs with a comparison to the
  status quo
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: >-
    If this made sense to you, go straight to the clam.


    If you are still unsure how our neural state machines are different than
    current AI techniques, try our MNIST benchmark.


    If you are completely confused, or if still unconvinced that dogs are
    different than deep reinforcement learning, best for us to talk! Learning
    comes from integrating differences.
  pages:
    - type: basic
      slug: basic-clam
      title: Basic Clam
    - type: basic
      slug: mnist-benchmark
      title: MNIST Benchmark
    - type: basic
      slug: contact-us
      title: Contact Us
---
## Problem-Solution Formulation

### The Status Quo

Designing an AI algorithm today involves extracting features from data to build a proper input to output mapping for a given task-- images to labels (CNNs); game state to best performing game move (RL); text prompt to text response (LLMs); text prompt to image response (image generators). 

Thus, the bottlenecks are now in data (Andrew Ng is very eloquent on this subject of data-centric AI). And the dream of most people, of course, is an AI that can perform across a range of tasks as general as expected from at least humans.

With the great AIs we have today-- ChatGPT or other LLMs, genAI, even robotics-- who gets to decide what is training data for these machines? Who gets to pre-train them and what guarantee is there that the bias of the pre-training will match the expectations of the user? Who is setting the context for _your_ AI experience?

At a higher level, we can definitively say that intelligence involves somehow determining what data should be used for training, as that's an aspect of intelligence we exercise when building AI, yet this aspect is neglected in our artificial design of intelligence which remains limited by our ability to define its data.

### Our Approach

In the tradition of great technology, we’re asking you to think differently.

The AI you are here with us to explore is a form of intelligence by association. To be more specific, intelligence of self-association.

Where status quo AI is a learned input-output mapping in the form of a parametric function, our system is in the form of a state machine. It is based on an antecedent to backpropagation involving weightless neurons developed at Imperial College in the last AI winter. 

To summarize, our AIs are neural state machines that learn to associate input-output pairs relative to their own dynamic inner states (that are determined by their instincts set by the designer) such that as agents they can be classically conditioned to perform general behaviors. Our v0.1.0 is currently at the level of a clam. Going up the phylogenetic tree underpins our whole methodology and is built into our open source strategy.

> 📘 New AI with Old Research
> 
> Quite some unpacking is needed as this code is based on years of research from a branch of algorithm that divergent from deep learning back in the 1980s, so thank you for being patient with the rest of this guide.

### The Comparison: Input-Output Mappings vs. Associations

With the state-of-the-art machine learning techniques referenced above, the objective frame of reference that determines what is a proper learned input-output mapping is outside of the AI system--

| Input       | Output        | Objective Frame of Reference | Algorithm              |
| :---------- | :------------ | :--------------------------- | :--------------------- |
| Images      | Labels        | Labelled training data       | Convolutional NNs      |
| Game state  | Game move     | Game score                   | Reinforcement Learning |
| Text prompt | Text response | Human-level text corpus      | Large Language Models  |

Our systems learn a unique input-output mapping in the same form, though more aptly it is now called an association because the objective frame of reference is preserved as part of the learned mapping--

| Input | Output | Objective Frame of Reference | Algorithm  |
| :---- | :----- | :--------------------------- | :--------- |
| A     | Action | Instinct trigger F           | AO Labs AI |

Where **A** and **Action** are arbitrary input-output pairs, and **instinct F** is something like "food" set by a designer as a trigger for learning or reward. F can then be paired with A for training purposes. A comparison to biological intelligence is helpful at this point--

> 🚧 Not convinced of this comparison?
> 
> Or maybe this seems similar to reinforcement learning? [Let's dig into that here before you continue, please.](https://docs.aolabs.ai/docs/on-the-differences-from-reinforcement-learning)

### Lessons from Biological General Intelligence

First we'll consider a dog as a grounding thought experiment, then we'll move down our phylogenetic tree to our v0.1.0 clam.

Consider, 

| Input       | Output | Objective Frame of Reference | Algorithm            |
| :---------- | :----- | :--------------------------- | :------------------- |
| Finger snap | Sit    | Treats                       | Hypothetical Pet Dog |
| A           | Action | Instinct trigger F           | AO Labs AI           |

where, if the system was a dog, A is the snapping of the fingers, Action is when the dog sits, and F is food given to condition proper action[^2].

Thus the dog learns this snap-sit behavior from the trainer who paired F and A, such that Action has come to be paired with A in the dogs internal state; the dog is more likely to respond with Action to A as opposed to other things C in the environment.

Importantly, the dog learns this association with respect to F, the instinct of F being a part of the dog. Thus, the dog is an **agent** with a necessarily vested interest in its “intelligent” act, not simply an input-output policy or model of intelligent acts measured externally as structured data. The dog as an agent is not optimizing for an externally set objective function[^1], but instead it is seeking to optimize its internal state, constantly, at every level of its being; only through human training does the dog’s optimization around its internal state come to hold the human-desired intelligent association of snap-sit, "roll over"-rolls over, etc.

It is important to note, the human training must act on the dog's instincts (through treats, etc.) otherwise it would have no effect or substance to the dog. That humans can also understand the chain of associations which underpin a dog’s intelligent behavior (like ball-fetch) is why we can trust dogs in ways where current AI systems would only be input-output blackbox mappings (eg. deep learning).

## v0.1.0 in context

### Clams!

Of course, dogs are extremely complicated agents, and the above association is clearly an extreme over-simplification. Luckily even much simpler creatures, down to worms, display the same associative behavior we are interested in isolating in our code. In our research, we find a suitable starting point farther down our phylogenetic tree.

We initially focused on worms, specifically C Elegans, as they can also be classically condition to learn a variety of associations all while having a fixed number of neurons (all C Elegans has 302 neurons).

However it is helpful to start with an even simpler creature than worms, the humble _clam_-- clams in the wild usually close up when they sense shadows, due to predation and other factors (a shadow might be a predator coming by!). Clams in captivity, though, have learned to stay open around shadows; they come to associate, relative to their own experiences, shadows with humans dumping food in their tanks.

The simplest formulation of this experiment is our basic clam, our "hello, world" program, and it works very well. We're excited to have you try it out. The code is in our repository, [folder Demos](https://github.com/aolabsai/ao_core/tree/main/Demos). Check out the [Basic Clam guide](https://docs.aolabs.ai/docs/basic-clam), and we also have a [step-by-step code walk-through should you get lost](https://docs.aolabs.ai/recipes/basic-clam-demo).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ec388cc-Clam.png",
        "Clam.png",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]

### MNIST

If this didn’t make sense yet, please take a look at our MNIST benchmark guide.

If a clam takes in multiple input channels (or types, such as shadows, temperature, vibration, plankton/food level, etc.) and more or less one output type (open/close), then MNIST is like a simple 1 channel clam, as MNIST involves 1 input type of 28x28 pixel input to one output type of 0-9 digits.

MNIST is like a one channel clam.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1c48974-MNIST_Arch.png",
        "MNIST Arch.png",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]

***

### Footnotes

[^1]\: Viewed this way, AI systems that rely on external cost or objective functions are like dogs that are fetching the stick for the stick itself-- quite absurd, or in the case of AI, as good as we can structure the data (big data sticks), beyond which we question robustness (hallucinations) and qualia.

[^2]\: Ball-Fetch was the previously used example, however a few people, notably @futha have pointed out that certain dogs have a strong instinctual drive to seek our objects without needing training from humans with treats. And certainly dogs also co-evolved with humans (domestication), so no doubt they have instinctual responses to the impressions we can give off (i.e. they can read our expressions and tones of voice). That's why starting with simpler creatures, clams and C Elegans, is necessary.