---
title: agent
excerpt: Overview & main specifications
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: If this doesn't make sense, go to one of our summaries.
  pages:
    - type: basic
      slug: developer-summary
      title: Developer Summary
    - type: basic
      slug: concept
      title: Conceptual Summary
    - type: basic
      slug: basic-clam
      title: '"Hello, World," a Clam-level AGI'
    - type: endpoint
      slug: agentinvoke
      title: Agent invoke
---
Agents are **neural state machines** comprised of weightless neurons, that is, binary nodes that are in state 0 or 1.

Agents are configured by their Arch, which sets the number of neurons and how they're connected (which neurons affect which). 

You invoke Agents and train them to associate input states with particular output states by providing labels, or through a method for Agents to acquire their own labels (like instincts), or at forced moments, as Agents learn by self-associating (in other words, Agents maintain an inner-state, accessible through Agent History).
