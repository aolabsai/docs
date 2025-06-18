---
title: About Identra
excerpt: >-
  An API for top-of-funnel job applicant fraud detection
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: Try an API call now
  pages:
    - type: endpoint
      slug: identra
      title: Playground & Reference
---

WIP https://docs.google.com/document/d/1irTbf9SqdYZaAhM01jEbRgRwzbrxe-YtkYR_xCI_yto/edit?usp=sharing


Identra is a machine learning API that takes in candidates’ resumes and responds with a fraud likelihood score from 0-100%. This score is derived from checking and cross-referencing social proof (LinkedIn and GitHub), communication information (email and phone), and essential semantic information (extracted via an LLM), serving as a first-pass assessment of a candidate’s likelihood of being fraudulent.

Identra is built to save you time and energy in the genAI-driven fraud arms race.

Identra is simple to use:

  Input candidate – in the form of a .docx or .pdf resume
  Output fraud score from 0-100% + assessment information

Refer to our developer playground and full API reference [here](doc:identra).


## Pricing

Identra is currently free to use while in preview. To deploy at scale for your application, say hi to our team to discuss pricing and deployment options.


## Identra use-case

Identra is a top-of-funnel identity flagging tool designed to detect AI-generated fake and synthetic candidates as soon as they create an account or submit an application. By identifying these profiles early in the hiring process, teams can avoid unnecessary evaluations, saving an average of 3,000 minutes per open role each month. Mistakenly hiring fraudulent candidates can cost companies up to $250,000 USD per role and significantly increase the risk of malicious activity.

## How Identra is trained

Identra is trained on a dataset of resumes of both fake and real candidates that’s curated to ensure maximum variance. To improve performance for your specific application, you can further train Identra on your own data, details here. Indentra combines various 3rd party APIs to find and check candidates’ information with a proprietary lightweight AI layer that learns the implicit fraud patterns against the patterns found in real candidates, using the learned heuristics to infer likelihood of fraud of new incoming resumes.


## Fine-tuning and further training on private data

We can spin up private versions of Identra on-demand. Performance improves when you train Identra on your specific datasets. Reach out to set this up.


## Authentication

[Say hi on discord](https://discord.gg/mE3WBFaMQy) to get your API key.