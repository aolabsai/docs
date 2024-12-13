---
title: Create a custom Arch
description: >-
  Set the right number of input, output, and control (learning) neurons for your
  application
hidden: true
recipe:
  color: '#8701f4'
  icon: 🛠️
---
```python Python
## // Netbox- Device Discovery -- Reference Design #2
# Source: https://github.com/aolabsai/archs/blob/main/2_netbox-device_discovery.py
# 
# For interactive visual representation of this Arch:
#    https://miro.com/app/live-embed/uXjVM_kESvI=/?moveToViewport=139623,-44894,15015,11297&embedId=159693252308

description = "NetBox Device Discovery - a relational autocomplete"
arch_i = [10, 10, 10]               # a scaled up Basic Clam, with 3 input channels with 10 neurons each, corresponding to device Mfg, Type, and Site (from IDss to 10-digit binary)
arch_z = [10]                       # 10 neurons in 1 channel to encode device Role IDs
arch_c = []
connector_function = "forward_full_conn"
# device mfg, type, and site are stored as strings (names) with associated unique IDs
# using 10 binary neurons to encode integer IDs means we can encode up to 2^10 = 1048 unique binary values.

# To maintain compatability with our API, do not change the variable name "Arch" or the constructor class "ao.Arch" in the line below (the API is pre-loaded with a version of the Arch class in this repo's main branch, hence "ao.Arch")
Arch = ao.Arch(arch_i, arch_z, arch_c, connector_function, description)


import requests
url = "https://7svo9dnzu4.execute-api.us-east-2.amazonaws.com/v0dev/kennel"
payload = {
    "kennel_name": "NetBox Device Discovery TEST",  # give it a unique name
    "arch_URL": "https://raw.githubusercontent.com/aolabsai/archs/main/2_netbox-device_discovery.py",
    "description": "the simplest, atomic arch reference design, our hello, world",
    "permissions": "free and open as the sea!"
}
headers = {
    "accept": "application/json",
    "content-type": "application/json",
    "X-API-KEY": "weBuildBottomUpAGIsForAll"
}
response = requests.post(url, json=payload, headers=headers)

print(response.text)

```

```json Response Example
{
  "kennel_id": "v0.1.2dev/NetBox Device Discovery TEST",
  "developer_id": "v0.1.2dev",
  "kennel_name": "TEST-Clamologist2",
  "description": "the simplest, atomic arch reference design, our hello, world",
  "arch_string": "arch_string upload SUCCESSFUL",
  "permissions": "free and open as the sea!",
  "agents": "newly created Kennel with no Agents yet! Get started with POST /kennel/agent"
}
```

# Pick a template

<!-- python@1-2 -->

Start with a reference design from our [Archs repo](https://github.com/aolabsai/archs) or with our [demo apps](https://www.aolabs.ai/demos); there are 3 to get you started.

For this recipe, we're starting with the architecture for the NetBox Device Discovery Agent.

# Set the number of the input neurons (I)

<!-- python@4 -->

How many different types of data do you have in your input? That's how many input channels you need, each its own element in the `arch_i` array. For this example, we need 3 channels, for device Manufacturer, Type, and Site IDs.

How much input variance is there in each channel? You'll need enough neurons to encode your data in binary. For this example, we're using 10 neurons for each channel, allowing for 2^10 = 1024 unique IDs per channel.

# Set the number of output neurons (Z)

<!-- python@9 -->

Similar to the input-- how many different types of data do you have in your output. For this example, our output is the Device's Role ID, so we will use 1 channels with 10 binary neurons (encoding for 2^10 =1024 unique IDs).

# What about control (instinct) neurons?

<!-- python@10 -->

For the NetBox application, whenever a new device is added, its role is inputted by a human, so we have *Label* to drive learning.

For an Agent that uses Instincts to learn more automatically, refer to our Basic Clam Agent.

# How should the input and output neurons be connected?

<!-- python@11 -->

You can connect channels to each other through a number of ways, see here for details.

Start with `"full_conn"` (fully connecting all neurons); you can make the connections more sparse later.

For this example, we used `"forward_full_conn"`, connecting each channel to its corresponding input, and all output to each input.

# Leave this line as-is to ensure compatibility with our API

<!-- python@15-16 -->

The Arch class is open source; you can dig into it to modify the number of middle layer (Q) neurons, add instinct neurons, and connect neurons in different ways.

# Host your Arch on GitHub using the raw URL

<!-- python@23 -->

Our API will pull your Arch from a GitHub raw URL. You can fork and pull request our Archs repo, a chance for us to give you feedback and ensure your Arch and Agents works as you intend.

# Run the API call to create your kennel

<!-- python@19-34 -->

Give it a unique name!

If a kennel with your chosen name already exists, you'll get an error.

# You're ready to create/deploy Agents!

<!-- python@ -->

Your next step: https://docs.aolabs.ai/reference/agentinvoke

Use `kennel_id: "v0.1.2dev/NetBox Device Discovery TEST"` (change to whatever you named your kennel).