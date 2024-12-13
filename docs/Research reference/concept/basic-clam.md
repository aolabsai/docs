---
title: '"Hello, World," a Clam-level AGI'
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
## v0.1.1 in context

### Framing our thought experiment

Clams take in multiple inputs, and have very basic outputs, and on this basis they learn and be classically conditioned.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2fb634b-Artboard_182x.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "500px"
    }
  ]
}
[/block]

Of course their instincts come into play. We consider a simplification of the clam by taking only 3 inputs and 1 output. 

Of the 3 inputs, let the 1st input be signal for the presence of Food, 2nd for chemical A, and 3rd for chemical B.

If the Clam has an instinctual response-- if its mouth was open, and Food was present, the pleasure instinct is triggered and the Clam repeats what it did that lead it to pleasure (i.e. the clam keeping its mouth open).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f514986-Artboard_102x.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "500px"
    }
  ]
}
[/block]



### Designing our Basic Clam

With the addition of instincts, we can now close the loop and begin designing our system in code.

Following our core architecture--

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b9f5c74-Artboard_112x.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "800px"
    }
  ]
}
[/block]



For the Clam--

I - Input Layer - We will use 1 binary (0/1) neuron for _each_ input (so Input=[1,1,0] means Food and A but not C, etc.).

Q - State Layer (corresponds to hidden or inter-neurons) - Mirrors I in shape; so also 3 binary neurons.

Z - Output Layer - 1 binary neuron, for 1=Open / 0=Close

C - Control Layer (corresponds to instincts) - 1 binary neuron, for 1=Pleasure / 0=Null

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5467c2e-Artboard_132x.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "500px"
    }
  ]
}
[/block]



So we'd need, at minimum, 9 neurons, as below (there are 2 C neurons to account for both labels and instincts).

We fully connect the neurons (so all Q are connected to all I and Q; and Z is connected to all Q and Z). C is connected to QZ neurons.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1dd1a64-Artboard_142x.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "500px",
      "caption": "For a better visual, please visit the miro board below."
    }
  ]
}
[/block]

[block:html]
{
  "html": "<iframe width=\"768\" height=\"432\" src=\"https://miro.com/app/live-embed/uXjVM_kESvI=/?moveToViewport=89203,-49112,16073,14223&embedId=897296881779\" frameborder=\"0\" scrolling=\"no\" allow=\"fullscreen; clipboard-read; clipboard-write\" allowfullscreen></iframe>"
}
[/block]



Consider,  
F : food,  
    A : shadow,  
    C : other env stimuli

   output : open/close

Given FA as input (food and shadow), the clam should then learn to respond more to A than C in the absence of F.

that is, after training on:  
     A \<> open -- F  
the system should learn an association such that  
     A \<> open  
     should be more likely to occur than  
     C \<> open

The atomic case of this is 3 input neurons (one for each FAC) and 1 output neuron (open/close). The relevant source code for the Clam Agent Arch is in the [repo here](https://github.com/aolabsai/archs/blob/main/basic_clam.py).