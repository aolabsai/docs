---
title: Agent invoke
excerpt: >-
  post an input (with optional learning modes instinct and label) to agent to
  evoke its output
api:
  file: ao_core.json
  operationId: agentInvoke
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: >-
    Try our `Hello, World` Agent, pre-loaded on our API at kennel_id
    `v0.1.2dev/TEST-BedOfClams`. There's also a frontend app to get a feel for
    this Agent.
  pages:
    - type: basic
      slug: basic-clam
      title: '"Hello, World," a Clam-level AGI'
    - type: link
      title: '"Hello, World" Demo App'
      url: https://aolabs.streamlit.app/
---
From a **Kennel**, invoke a specific **Agent** with an **Input** to get its **Output**

Agents are trained with labels or flags for C-Positive or C-Negative. 

Training occurs if a label or C-flag is in the post request, otherwise it infers based on the input and prior state.

### Learning via Labels

If there is a label in a request, the Agent's Output will match the Label, and the Agent will learn to associate the Input with the Output-Label, weighted against Agents' past associations.

### Learning via C-Positive and C-Negative
The C-Positive and C-Negative flags are the CP and CN boolean flags in a control object in a request.

When training with C-Positive, the agent trains on the supplied input and the previous output.

When training with C-Negative, the agent trains on a flip of the supplied input and a bit flip of the previous output. 

### Training Notes:
* When training, the priority order is labels > C-Negative > C-Positive.
* If the trigger is positive (pleasure) then it reinforces the associated behavior; if the trigger is negative (pain), the Agent will do the opposite of output next time, diminishing or disassociating the behavior.

### Miscellaneous Functions (request)

* Agent Deletion (delete_agent): Removes the agent from the database and temporarily stores it in buffer storage for potential recovery.
* agent Retrieval (retrieve_agent): A deleted agent can be restored from buffer storage if needed.
* Fetching Agent History (story): Retrieves the previous states of an agent. 

> 📘 Sequenced Learning
>
> By default, Agents learn sequenced or time series data-- their next move is informed by their immediate past action. 
>
> If your data isn't in a stream or consistent sequence, such as a table of information (the Netbox example), then set **`US = True`** to introduce a random binary state as reset between Agent invocations.
