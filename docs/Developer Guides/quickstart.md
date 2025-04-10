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
# TODO: add link to python API wrapper where appropriate

We welcome your feedback at v0.1.4 of our API and code.

Before your endeavor to build an Agent custom to your application, run through this guide to get familiar with our system, and please let us know if you make it through by pinging us on [discord](https://discord.com/invite/Zg9bHPYss5)!

Before starting, you should understand a bit about how our agents' inputs and outputs are structured. Inputs and outputs to our agents are sequences of 0s and 1s. These 1s and 0s could represent flags or conversions from numbers, for example a 5 could be converted to its binary representation of 101 for an input or label. If you want an agent to take in numbers converted to binary and know they'll be between 0 and 5, you could do that with 3 neurons.

<br />

# Step 1) Pick a reference design to use as a template

We have 3 Agents to start you off, each configured with an Arch relative to its application.

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}></th>
      <th style={{ textAlign: "left" }}></th>
      <th style={{ textAlign: "left" }}></th>
      <th style={{ textAlign: "left" }}></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        [Basic Clam](https://aolabs.streamlit.app/)
      </td>
      <td style={{ textAlign: "left" }}>
        [App Code](https://github.com/aolabsai/archs/blob/main/Applications/HelloWorld-BasicClam/Clam_App.py)
      </td>
      <td style={{ textAlign: "left" }}>
        [Arch](https://github.com/aolabsai/archs/blob/main/0_basic_clam.py)
      </td>
      <td style={{ textAlign: "left" }}>
        a simple Agent that can associate A or B with output without labels
      </td>
    </tr>
    <tr>
      <td style={{ textAlign: "left" }}>
        [NetBox Device Discovery](https://aolabs-netbox.streamlit.app/)
      </td>
      <td style={{ textAlign: "left" }}>
        [App Code](https://github.com/aolabsai/archs/blob/application/Netbox_devicediscovery/Applications/Netbox/Device_Discovery/Main_Page.py)
      </td>
      <td style={{ textAlign: "left" }}>
        [Arch](https://github.com/aolabsai/archs/blob/main/2_netbox-device_discovery.py)
      </td>
      <td style={{ textAlign: "left" }}>
        a scaled up version of the Basic Clam that learns to predict a network device's role from its manufacture, type, and site; learns with labels
      </td>
    </tr>
    <tr>
      <td style={{ textAlign: "left" }}>
        MNIST Benchmark
      </td>
      <td style={{ textAlign: "left" }}>
        Coming Soon
      </td>
      <td style={{ textAlign: "left" }}>
        [Arch](https://github.com/aolabsai/archs/blob/main/1_basic_MNIST.py)
      </td>
      <td style={{ textAlign: "left" }}>
        *streamlit application coming soon*; a single-channel Agent trained on input-output image-label pairs to identify 0-9 from the handwritten numbers of the
        [MNIST database](https://en.wikipedia.org/wiki/MNIST_database).
      </td>
    </tr>
  </tbody>
</Table>

<br />

# Step 2) Fork an Arch and modify it to suit your application

Modify the Arch script to suit your application needs. This involves changing the number of input, output, and control neurons to match your data model. The Arch script is also where you define custom triggers for learning through instinct control neurons.

Here's a tutorial to walk you through the steps:

<TutorialTile backgroundColor="#8701f4" emoji="🛠️" id="66d6cda01fab5100441176ff" link="https://docs.aolabs.ai/v0.1.2/recipes/create-a-custom-arch" slug="create-a-custom-arch" title="Create a custom Arch" /> 

Designing your own Arch is something we're especially happy to help with! [Chat on discord](https://discord.gg/Zg9bHPYss5) or book a [meeting](https://calendly.com/aee/meeting).

<br />

# Step 3) Upload your Arch to our API with the [kennelCreate](ref:kennelcreate) call

The API needs an arch before you can start creating and using agents. To send an arch to our API you'll need to use our kennelCreate call. That can be done with a POST request or through our python API wrapper. 

If you send in your request would look something like this. Our [kennelCreate](ref:kennelcreate) page can give you an idea of how you'd use it in a couple different languages.
```json
{
  "kennel_name": "my kennel"
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

# Step 4) Then use [Agent invoke](ref:agentinvoke) to dynamically create and use Agents

Agents are created dynamically as you call them (in other words, if you invoke an Agent that doesn't exist yet, it'll be created). Build as many Agents as you need, per-user or otherwise. Agents maintain their own persistent memory.

<br />

> 👍 You're ready to add Agents to your application!

# Now, what will you build?

Here are some high-level sketches of applications we're exploring as within scope of v0.1.4.

<HTMLBlock>{`
<iframe width="768" height="432" src="https://miro.com/app/live-embed/uXjVM92gM2Y=/?moveToViewport=151636,-78346,14005,5440&embedId=26026240606" frameborder="0" scrolling="no" allow="fullscreen; clipboard-read; clipboard-write" allowfullscreen></iframe>
`}</HTMLBlock>
