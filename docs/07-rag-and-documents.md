[Back to README](../README.md)

# 07 RAG And Documents

## RAG Summary

Closer indexes uploaded product or knowledge documents into Qdrant. The retrieval layer uses Ollama embeddings and structured chunking to make product names, compliance sections, fit maps, and methodology chunks searchable during live coaching.

## Document Flow

```mermaid
flowchart TD
    Upload[Upload PDF document] --> Parse[Extract text]
    Parse --> Structure{Structured markers found?}
    Structure -->|Yes| Markers[Chunk by CHUNK markers]
    Structure -->|No| Headings{Target segment headings?}
    Headings -->|Yes| ProductChunks[Chunk by product sections]
    Headings -->|No| Fallback[Character chunking]
    Markers --> Embed[Generate embeddings]
    ProductChunks --> Embed
    Fallback --> Embed
    Embed --> Store[Store vectors and payload in Qdrant]
    Query[Live query] --> Search[Vector search with score threshold]
    Search --> Context[Catalog-grounded context]
```

## Retrieval Design

| Design Choice | Reason |
| --- | --- |
| Structured chunk types | Keeps product, compliance, methodology, and fit-map knowledge distinguishable |
| Product name payloads | Makes recommendations traceable to exact catalog products |
| Score threshold | Reduces low-confidence retrieval from feeding the model |
| Local embeddings | Supports privacy-conscious document processing |

## Screenshot

![Closer documents page](../screenshots/documents.png)

The documents view shows how administrators upload product PDFs into the Qdrant-backed knowledge base.
