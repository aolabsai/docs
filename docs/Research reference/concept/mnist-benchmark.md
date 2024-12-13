---
title: MNIST Benchmark
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
If the example of the clam does not make sense, it is helpful to consider how our AI applies to MNIST, a popular computer vision benchmark ([see wiki](https://en.wikipedia.org/wiki/MNIST_database)).

If a clam takes in multiple input channels (or types, such as shadows, temperature, vibration, plankton/food level, etc.) and more or less one output type (open/close), then MNIST is like a simple 1 channel clam, as MNIST involves 1 input type of 28x28 pixel input to one output type of 0-9 digits. The main point is that it would be absurd to expect a 1 channel MNIST algorithm, even the ones at 99.87%+ accuracy ([see world leaderboard](https://paperswithcode.com/sota/image-classification-on-mnist)), to have any understanding of what a number is, because the meaning of a number is not contained solely in the visual information of that number. That's why we're building our AI from the bottom-up.

Despite this, we still benchmarked our AI against MNIST as it provides a helpful way to experiment with different connection strategies of neurons, a major component of an Agent's Arch that determines its output. While at UC Berkeley 2020-21, we worked on an MNIST paper [see abstract here](https://docs.google.com/document/d/1p3FvYYPsD9XunJg2Dfaw0wLvnxIUspPsMvBi8acp0EI/edit?pli=1) (unsubmitted), and the MNIST Agent (described below) is also available in our Archs repo [here](https://github.com/aolabsai/archs/blob/main/basic_MNIST.py).

![](https://files.readme.io/1bc3910-Basic_Architecture3x.png)
