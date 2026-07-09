[Back to README](../README.md)

# 02 Business Problem

## Problem

Sales representatives often need to process product knowledge, customer context, compliance constraints, and live objections at the same time. Generic AI chat tools are too detached from the conversation, while static sales playbooks are too slow to search during a call.

Closer addresses that gap by creating a live copilot for discovery, coaching, and grounded recommendations.

## Stakeholders

| Stakeholder | Need |
| --- | --- |
| Sales rep | Ask better questions and avoid incorrect product claims |
| Sales manager | Review sessions, KPIs, and coaching quality |
| Customer success/admin | Manage documents, customers, and users |
| Organization | Keep recommendations grounded in approved knowledge |

## Why This Is Hard

- Meeting context changes in realtime.
- Product recommendations can be high-stakes.
- Reps need short, readable coaching, not long model output.
- Uploaded documents must constrain the assistant.
- Different industries need different scoring logic and prompts.

## User Journey

```mermaid
journey
    title Closer Sales Copilot Journey
    section Before Meeting
      Admin uploads product documents: 4: Admin
      Rep opens customer profile: 4: Sales Rep
    section During Meeting
      Desktop app captures transcript/context: 5: Sales Rep
      AI suggests next discovery question: 5: Sales Rep
      AI flags false product claim: 5: Sales Rep
    section After Meeting
      Session saved for review: 4: Sales Manager
      Dashboard updates KPIs and memory: 4: Sales Manager
```

## Screenshot

![Closer live sales coach](../screenshots/desktop-coach.png)

The live coaching surface shows the core product promise: concise guidance during the meeting, not after it.
