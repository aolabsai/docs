---
title: Connector Functions
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
* full\_conn
  * TODO
* forward\_full\_conn
  * TODO
* forward\_forward\_conn
  * TODO
* rand\_conn
  * connections between neurons are formed randomly when using this connector function
  * `param\_1: int` number of connections between neurons in the input layer and neurons in the internal layer
  * `param\_2: int` number of connections between neurons within the internal layer
  * `param\_3: int` number of connections between neurons in the internal layer and output layer
  * `param\_4: int` number of connections between neurons within the output layer
* nearest\_neighbour\_conn
  * connects neurons to their nearest neighbors
  * `param\_1: int` number of neighbors to connect to along the x/y axes
  * `param\_2: int` number of diagonal neighbors to connect to
  * `param\_3: int` x dimension size of grid
  * `param\_4: int` y dimension of grid
  * `param\_5: bool` True if output neurons are connected to corresponding input neurons
  * `param\_6: int` number of random connections between internal and output neurons (optional if input size mathches output size, required if they do not match)
* rectangular\_conn
  * TODO
  * `param\_1: int` distance along x-axis for forming connections
  * `param\_2: int` distance along y-axis for forming connections
  * `param\_3: int` x dimension size of grid
  * `param\_4: int` y dimension size of grid
  * `param\_5: bool` True if output neurons are connected to corresponding input neurons
  * `param\_6: int` number of random connections between internal and output neurons (optional if input size matches output size, required if they do not match)