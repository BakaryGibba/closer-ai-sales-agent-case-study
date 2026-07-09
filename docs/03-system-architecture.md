[Back to README](../README.md)

# 03 System Architecture

## Architecture Summary

Closer has two main surfaces: a desktop Electron copilot for live work and a dashboard for operational management. The desktop app communicates through an IPC bridge to helpers for screenshots, audio, documents, sessions, AI providers, vector retrieval, and authentication.

```mermaid
flowchart LR
    subgraph Desktop["Electron Desktop App"]
        Overlay[Transparent Overlay UI]
        IPC[Preload IPC Bridge]
        Shortcuts[Global Shortcuts]
        Capture[Screenshot and Audio Capture]
        Coach[Live Meeting Coach]
        Launch[Protocol Launch Bridge]
    end

    subgraph AI["AI and Retrieval"]
        LLM[Gemini / OpenAI / Groq / Ollama]
        Embed[Ollama Embeddings]
        Qdrant[(Qdrant Vector Store)]
        Docs[Document Parser and Chunker]
    end

    subgraph Dashboard["Team Dashboard"]
        Web[React Dashboard]
        API[Express API]
        DB[(Postgres or Local Dev DB)]
    end

    Overlay --> IPC
    IPC --> Shortcuts
    IPC --> Capture
    IPC --> Coach
    IPC --> Docs
    Docs --> Embed --> Qdrant
    Coach --> Qdrant
    Coach --> LLM
    Launch --> API
    Web --> API --> DB
    API --> Launch
```

## Boundaries

| Boundary | Why It Exists |
| --- | --- |
| Electron IPC | Keeps renderer UI separate from privileged desktop capabilities |
| AI provider abstraction | Supports cloud and local model choices |
| Vector helper | Keeps retrieval, chunking, embeddings, and Qdrant isolated |
| Dashboard API | Gives teams operational views beyond the desktop assistant |
| Launch protocol | Connects dashboard context to the desktop app |

## Screenshot

![Closer desktop assistant queue](../screenshots/desktop-queue.png)

The desktop queue shows the Electron copilot surface that connects live transcript, customer context, documents, history, and model controls.
