[Back to README](../README.md)

# Diagrams

This folder contains editable Mermaid source files. GitHub renders the Mermaid diagrams embedded in the Markdown docs; these `.mmd` files can also be exported to PNG/SVG for presentations.

| Mermaid Source | Optional Export | Purpose |
| --- | --- | --- |
| [`architecture.mmd`](architecture.mmd) | `architecture.png` | Desktop, AI, retrieval, dashboard, and API architecture |
| [`ai-workflow.mmd`](ai-workflow.mmd) | `ai-workflow.png` | Transcript-to-coaching AI workflow |
| [`rag-flow.mmd`](rag-flow.mmd) | `rag-flow.png` | Document ingestion and retrieval |
| [`dashboard.mmd`](dashboard.mmd) | `dashboard.png` | Dashboard route/API structure |
| [`data-model.mmd`](data-model.mmd) | `data-model.png` | Conceptual entities and relationships |
| [`multi-tenant.mmd`](multi-tenant.mmd) | `multi-tenant.png` | Tenant configuration and vector isolation roadmap |

## Export Guidance

Use Mermaid CLI if you need images:

```bash
mmdc -i diagrams/architecture.mmd -o diagrams/architecture.png
```

Do not add real customer names, transcripts, credentials, or private tenant data to diagrams.

