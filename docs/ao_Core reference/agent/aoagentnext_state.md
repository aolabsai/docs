---
title: ao.Agent.next_state( )
excerpt: >-
  ***method*** :  `ao.Agent.next_state( INPUT, LABEL=[], INSTINCTS=False,
  Cpos=False, Cneg=False, print_result=False )`


  [[source](https://github.com/aolabsai/ao_core/blob/a289502a9f80a5e76581732a7938e93cef8e1363/ao_core.py#L68)]
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Given an INPUT, this method advances the agent to the next state; this means firing all neurons (constituting a state) and incrementing `agent.state` by 1.

And, optionally, in order of the arguments--

- **to train with labelled data** (ie. with a clean input\<>output pair), provide the output as LABEL; the agent's output neurons will match the LABEL and the agent will record the INPUT\<>LABEL as a positive learning event.

- **to train more autonomously**, without specifying labelled data, set INSTINCTS as `True`; when an agent's INPUT triggers any instinct conditions, the agent will record INPUT and its previous output as a learning event.

- **to force train positively** (i.e. train without a label or instinct), set Cpos as `True`; the agent will record INPUT and its previous output as a positive learning event

- **to force train negatively (do opposite)** (i.e. train without a label or instinct), set Cneg as `True`; the agent will record INPUT and its previous output as a negative learning event

- Finally, the result (of the output neurons only) can be printed in the console if `print_result=True.` 

The net result of `.next_state()` operations is stored in agent attributes `.story` and `.metastory`.

# Parameters

- **INPUT : _binary list or np.array of size matching agent.arch.I\_\_flat_**  
          The input in binary to agent for one state.

- **LABEL : _binary string of size matching agent.arch.Z\_\_flat, optional_**  
           Used to train the agent with the INPUT\<>LABEL pair provided; the output neurons will match the provided LABEL, too.

- **INSTINCTS : _bool, optional_**  
           True value activates instinct neurons, so that training will automatically occur when INPUT matches the conditions of any instinct neurons as specified in `agent.arch`.

- **Cpos : _bool, optional_**  
           True value force trains that agent with INPUT\<>previous_output.

- **Cneg : _bool, optional_**  
           True value force trains that agent with the inverse of INPUT\<>previous_output.

- **print_result : \_bool, optional_**  
           True value prints out the response of the output neurons to the console.

- **{DD ; Hamming ; Default} : _bool, optional_**  
           True value(s) activate different neuron-level firing rules; neurons can fire according to 3 rules: a weighted approximation (DD), a weightless method using Hamming distance, and random by default.

> 🚧 Neuron-level setting
> 
> Keep them all as `True` is sufficient for most applications.