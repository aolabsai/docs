---
title: Configuring an Arch
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
At minimum, an Arch is created with the following information (the examples in the sub-bullet points are from our [Hello, World Basic Clam Agent](https://github.com/aolabsai/archs/blob/main/Architectures/basic_clam.py).

- **Description:** a name for your Arch  
  `description = "Basic Clam"`
- **Number of Input Neurons:** how many input neurons and in how many channels  
  `arch_i = [1, 1, 1]     # 3 neurons, 1 in each of 3 channels, corresponding to Food, Chemical-A, Chemical-B (present=1/not=0)`
- **Number of Output Neurons:** how many output neurons and in how many channels  
  `arch_z = [1]           # corresponding to Open=1/Close=0`
- **Number of Control Neurons:** neurons which control training  
  `arch_c = []            # 4 control neurons are included in the default first channel-- 0-label, 1-force_positive, 2-force_negative, 3-default pleasure instinct triggered when I**flat[0]=1 and Z of previous step Z**flat[0]=1`
- **Neuron Connections:** determines how neurons are connected  
  `connector_function = "full_conn"`
  - Options are:
    - `full_conn` to fully connect all neurons (so that each neuron will associate all other neurons with its firing pattern), i.e. Q to all I and Q; Z to all Q and Z
    - `forward_full_conn` to fully connect the neurons input-wise, i.e. Q channel to _all_ I and itself; Z channel to all Q and itself
    - `forward_forward_conn` to fully connect the neurons forward only, i.e. Q channel to _corresponding_ I channel and itself; Z channel to all Q and itself
    - Of course, you can specify a unique connection strategy by writing a function similar to the options above, or by manually connecting neurons in the [Arch datamatrix](https://docs.aolabs.ai/docs/aoarchitecturedatamatrix)

Once an Agent is created, its Arch cannot be changed; in other words, Agents have a fixed configuration (necessary for their inner-state to remain consistent and useful).