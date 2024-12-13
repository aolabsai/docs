---
title: Building an Agent
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
Now that we've gone through the process of [Building an Architecture](doc:building-an-architecture)let's build and use an agent.

Assuming you have an arch, building an agent is simple, as seen below.

```python
from ao_core import Agent
agent = Agent(arch, save_meta=False)
```

Now let's say we have an agent that takes in 3 integer inputs and outputs  an integer. We'd need to convert the inputs into an appropriate format before feeding them into the agent. When feeding input into the agent with a label, that is treated as training. If a label is not included, it is treated as inference. Output is in the format of a list of binary values, so you may want to convert it into an int after calling `next_state`.

```python
x=5
y=7
z=4

label = format(3, '010b')

formatted_input = format(x, '010b') + format(y, '010b') + format(z, '010b')

#when label is included, it is treated as training the agent
agent.next_state(formatted_input, LABEL=label)

#reset agent between nonsequential calls
agent.reset_state()

#inference on input
response = agent.next_state(formatted_input,
                            DD=True,
                            Hamming=True,
                            unsequenced=True)
```