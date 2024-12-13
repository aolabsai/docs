---
title: Architecture for MNIST
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: building-an-agent
      title: Building an Agent
---
Let's make an architecture for [MNIST](https://en.wikipedia.org/wiki/MNIST_database)  as an example. In case you aren't aware, MNIST is a handwriting recognition database consisting of 28x28 images of digits written out.

MNIST images are grayscale, with the int value of each pixel being between 0 and 255, which can be fully represented by 8 bits.

There are 10 output classes in MNIST representing the digits 0 through 9, that can be fully covered by 4 bits/neurons.

```python Python
arch_i = [8 for _ in range(28*28)]
arch_z = [4]
```

Next you'd need to choose a connector function and matching parameters, let's just use random connections.

The meaning behind parameters depends on the connector function. For `rand_conn` the first parameter is the number of connections between the input and internal layer, the second is the number of connections between neighbors in the internal layer, the third is the number of connections from the internal layer to the output, and the fourth is the number of connections between the neurons in the output layer.

```python Python
connector_function = "rand_conn"
connector_parameters = [392, 261, 784, 4]
```

Putting all of this together, we'd get.

```python
from ao_arch import Arch

arch_i = [8 for _ in range(28*28)]
arch_z = [4]
connector_function = "rand_conn"
connector_parameters = [392, 261, 784, 4]

arch = Arch(arch_i,
            arch_z,
            connector_function=connector_function,
            connector_parameters=connector_parameters
           )

```