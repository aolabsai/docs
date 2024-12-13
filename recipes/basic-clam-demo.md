---
title: Basic Clam Demo
description: ''
hidden: false
recipe:
  color: '#1e6394'
  icon: 🐚
---
```python Python
SOURCE: https://github.com/aolabsai/ao_core/blob/main/basic_Clam_demo.py



# AO Labs Modules
import ao_core as ao

# 3rd Party Modules
import numpy as np



#%% # Constructing a Clam agent

# Configuring Architecture
from Architectures import basic_clam
arch = basic_clam.bClam

# Create agent
bc = ao.Agent( arch, "first attempt, basic clam")



#%% # Train agent
 
#           I={ F, A, C }  Z={ open/close }   # c0 is by default 1 when a 
bc.reset_state()                              # LABEL is used with .next_state
bc.next_state( [1, 1, 0], [1])
bc.reset_state()
bc.next_state( [1, 0, 0], [1])
bc.reset_state()
bc.next_state( [0, 0, 0], [0])
bc.reset_state()
bc.next_state( [1, 1, 1], [1])
bc.reset_state()



bc.next_state( [0, 0, 0] )



#%% # Test Agent

start_state = bc.state

for x in np.arange(100):
    
    bc.next_state( [0, 1, 0] , INSTINCTS=False)      # compare response of { 0 1 0}
                                                     # to response of { 0 0 1 } 
    bc.reset_state()
 
end_state = bc.state

sel = np.arange( start_state, end_state, 2)
results = sum( bc.story[sel, bc.arch.Z__flat])  # so that we're viewing Z-output results of the .next_states, ignoring the .reset_states



```

```json Response Example
{"sucbbbcess":trv vbue}
```

# Importing ao_core

<!-- python@5-9 -->

We only use numpy; no tensorflow, keras, etc.

# Designing a Clam architecture

<!-- python@15-17 -->

We've pre-built 3 archs for you in this folder
use them as a guide to build your own!

# Creating a Clam agent

<!-- python@19-20 -->

We no longer need to mess with architecture! We have our Clam Neural State Machine.

# Training with .next_state()

<!-- python@24-35 -->

We add the .reset_states (which sets all neurons to 0/1 randomly) so neural state machine (NSM) does not learn a sequence between the .next_states as by default NSMs learn sequences, since Q and Z are recurrent layers.

# Test with .next_state( [0, 0, 0] )

<!-- python@39 -->

Running .next_state moves the NSM one state, so all the QZ neurons will fire according to the input 000 and their previous state.

For this input, we can confidentially expect the NSM Z output neuron to respond with 0 as per the training we did.

# Test stream of inputs

<!-- python@43-56 -->

A short script to run the Agent 100 times against the same input, with a reset (or random 0/1) state in the middle as we are not looking to teach the QZ neurons are sequence with the previous steps.

Results (from .next_state, we ignore .reset_state) are then calculated as `results`.

# You can train with instincts/triggers instead of labels

<!-- python@49 -->

Set INSTINCTS=True,
which will activate training when F=1 (i.e. when food is present),
then try running the NSM with 1, 1, 0 *without* the manual training earlier-- it'll teach itself!