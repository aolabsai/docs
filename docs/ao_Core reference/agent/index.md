---
title: ao.Agent
excerpt: |-
  ***class*** :  ao.Agent(arch, notes=[])

  [[source](https://github.com/aolabs-ai/aolabs_core)]
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
The main workhorse of ao\_core and all agent level operations.

An Agent instance, or agent, is a neural state machine made up of weightless neurons of specific number and shape determined by arch, an instance of ao.Architecture.

### Parameters

* **arch :*ao.Architecture instance***\
          Specifies the number of neurons and shape (from their connections and arrangement relative to each other)

* **notes :*str, optional***\
           Any useful notes, to more easily identity agents if creating many for an application as is often the case.

### Examples

## Methods

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        method
      </th>

      <th style={{ textAlign: "left" }}>
        function
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        `next_state( INPUT, LABEL=[] )`
      </td>

      <td style={{ textAlign: "left" }}>
        Returns the next state, through each neuron firing according to the input and their memory.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        `reset_state( )`
      </td>

      <td style={{ textAlign: "left" }}>
        Returns the next state as a reset state (all neurons fire randomly).
      </td>
    </tr>
  </tbody>
</Table>

### Attributes

* **agent.state :*int***\
          counter for the agent’s current state; incremented +1 by methods .next\_state and reset\_state

* **agent.story :*binary array***\
          displays the agent’s binary memory of all neuron activity (how the neurons fired, 0 or 1); a numpy array in shape (states, agent.arch.all\_neurons)

* **agent.metastory :*str object array***\
          shape and indices correspond to .story however contains metadata of neuron activity (why the neurons fired; useful for debugging).

* **agent.arch :*ao.Architecture instance***\
          access to the Architecture that underpins the agent

### Notes
