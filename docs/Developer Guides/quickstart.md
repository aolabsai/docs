---
title: Quick Start Steps
excerpt: Taking you from a reference design to running Agents
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---

We welcome your feedback at v0.1.4 of our API and code.

Before you start building an Agent custom to your application, run through this guide to get familiar with our system, and please let us know if you make it through by pinging us on [discord](https://discord.com/invite/Zg9bHPYss5)!

Before starting, you should understand a bit about how our agents' inputs and outputs are structured. Inputs and outputs to our agents are sequences of 0s and 1s. These 1s and 0s could represent flags or conversions from numbers, for example a 5 could be converted to its binary representation of 101 for an input or label. If you want an agent to take in numbers converted to binary and know they'll be between 0 and 5, you could do that with 3 neurons.

<br />

# Step 1) Determine the input-output structure of your agent

Inputs and outputs need to be structured in a way the system can interpret and the agents need to be built to handle those inputs and respond with an appropriate output.

Since these agents operate on binary data we'll start with determining how many digits will be in the agent's input and output. The two variables we'll focus on are `arch_i` and `arch_z`, determining the best `connector_function` can come after testing some things out.

This boils down to choosing an appropriate number of neurons for the input and outputs. Here's a simple example using our [python api wrapper](doc:ao_pyth-docs).
```python
#simple example
import ao_pyth as ao

arch_i = [3]
arch_z = [1]

api_key = "my_key"

arch = ao.Arch(arch_i=arch_i, arch_z=arch_z, api_key=api_key, kennel_name="my_kennel")
agent = ao.Agent(Arch=arch, api_key=api_key)

response = agent.next_state(INPUT="111", LABEL="1")
output = response["story"]
state = response["state"]
```

Designing your own Arch is something we're especially happy to help with! [Chat on discord](https://discord.gg/Zg9bHPYss5) or book a [meeting](https://calendly.com/aee/meeting).
## Examples

If you simply want binary flags for the presence of an input, you could do something like the basic clam. If you want to convert integer ids into inputs you could do something like the [netbox device discovery example](https://github.com/aolabsai/ao_loop1/blob/main/archs/2_netbox-device_discovery.py). If you want to work with images, you should take a look at the [MNIST example](https://github.com/aolabsai/ao_loop1/blob/main/archs/1_basic_MNIST.py).

<br />

# Step 2) Upload your Arch to the API with the [kennelCreate](ref:kennelcreate) call

The API needs an arch before you can start creating and using agents. To send an arch to our API you'll need to use our kennelCreate call. That can be done with a POST request or through our [python API wrapper](doc:ao_pyth-docs).

If you send your data through requests, the JSON would look something like this. Our [kennelCreate](ref:kennelcreate) page can give you an idea of how you'd use it in a couple different languages.
```json
{
  "kennel_id": "my_kennel"
  "arch": {
    "arch_i": "[1, 1, 1]",
    "arch_z": "[1]",
    "connector_function": "full_conn"
  },
  "email": "name@example.com",
  "description": "the simplest, atomic arch reference design, our hello, world",
  "permissions": "free and open as the sea!"
}
```

> 📘 If you don't have an API key, [request one on discord](https://discord.gg/nHuJc4Y4n7).

<br />

# Step 3) Then use [Agent invoke](ref:agentinvoke) to dynamically create and use Agents

Agents are created dynamically as you call them (in other words, if you invoke an Agent that doesn't exist yet, it'll be created). Build as many Agents as you need, per-user or otherwise. Agents maintain their own persistent memory.

The JSON for invoking an agent would look something like this, and could be sent using the same methods you use for the kennel create call. Examples can be generated for multiple languages on our [agentInvoke](ref:agentinvoke) page.
```json
{
    "kennel_id": "my_kennel",
    "agent_id": "agent_1",
    "email": "name@example.com",
    "INPUT": "000",
    "LABEL": "0",
}
```

<br />

> 👍 You're ready to add Agents to your application!

# Now, what will you build?

Here are some high-level sketches of applications we're exploring as within scope of v0.1.4.

<HTMLBlock>{`
<iframe width="768" height="432" src="https://miro.com/app/live-embed/uXjVM92gM2Y=/?moveToViewport=151636,-78346,14005,5440&embedId=26026240606" frameborder="0" scrolling="no" allow="fullscreen; clipboard-read; clipboard-write" allowfullscreen></iframe>
`}</HTMLBlock>
