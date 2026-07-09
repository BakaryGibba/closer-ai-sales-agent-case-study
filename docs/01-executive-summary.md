[Back to README](../README.md)

# 01 Executive Summary

## Overview

Closer is an AI sales copilot for live client conversations. It combines an Electron desktop assistant, realtime transcription, document-grounded retrieval, AI-generated coaching, customer/session memory, and an admin dashboard.

The project demonstrates practical AI engineering across desktop software, retrieval-augmented generation, realtime assistance, dashboard operations, and hallucination risk management.

## Product Narrative

Salespeople need useful support during conversations, not after the meeting ends. Closer listens to context, retrieves relevant product knowledge, and provides the salesperson with a concise coaching signal: what is known, what is missing, what to ask next, and whether a claim needs correction.

## Engineering Value

| Capability | Engineering Signal |
| --- | --- |
| Electron overlay | Cross-platform desktop UX, global shortcuts, capture workflow |
| Live transcription | Realtime streaming and incremental context handling |
| RAG | Document parsing, structured chunking, embeddings, vector retrieval |
| Guardrails | False-premise correction and out-of-catalog alerts |
| Dashboard | Operational view for customers, sessions, documents, and users |
| Multi-tenant roadmap | Configurable prompts, scoring, chunking, and vector isolation |

## Screenshot

![Closer dashboard overview](../screenshots/dashboard-overview.png)

The dashboard overview shows how individual desktop coaching becomes team-level operational visibility.
