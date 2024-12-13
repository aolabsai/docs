---
title: Weightless Neural Networks
excerpt: This page is due to be cleaned up soon; for now, refer to the papers below-
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Our Agents are powered by so-called Weightless NNs, in contrast to weighted systems where weights are set via backpropagation and gradient descent. This was a technique developed at Imperial College by [Igor Aleksander](https://en.wikipedia.org/wiki/Igor_Aleksander) before the last AI winter, since forgotten, which we have adapted in python as part of our ao_core.

[Paper # 3 - Iconic Training and Effective Information -- Igor & Gamez 2009](https://drive.google.com/file/d/1lV7XFPFgBQvjS3VFVkW0kZQT5YV1pHzy/view) -- read this first, the highlighted parts, which are essentially a summary of the 2nd paper below. Other parts of this paper are not relevant (integrated information and effective information are their own things, you'll notice from the abstract). This paper was also the inspiration for the MNIST benchmark included in our v0.1.0 (except the paper used 98x98 pixel images of famous faces whereas we used MNIST data). 

[Paper # 1 - Binary neural systems- combining weighted and weightless properties -- Igor, Clarke, Braga, 1994](https://drive.google.com/file/d/1YED8y3pc7sX-DJxRkyFkQE86uZ0i0y7m/view) -- Igor Aleksander wrote this paper to formalize WNNs; it goes into great depth and is the primary reference we use for WNNs (same info is included in this book). I highlighted a part that stands out. Quite dense, serves as a reference.  
Highlighted quote from pg 6--** "However, it is important to note that as far as the function of the element is concerned, _the need for hidden units and error backpropagation has been removed_, the node can perform all possible input-output functions."**

[Paper # 0 - Artificial Neuroconsciousness -- Igor Aleksander 1995 (IWANN)](https://drive.google.com/file/d/0BwRvCpL7WdEgQjFmTVB3dncyVUE/view?resourcekey=0-qPvp64bjT_gUCZTbDlCZKA)-- Igor Aleksander's attempt of extrapolating WNNs to AGI, which he called artificial consciousness. Spiritual reference of sorts.