[Back to README](../README.md)

# 13 Future Improvements

## Roadmap Summary

Future work should focus on production-grade multi-tenancy, tenant configuration UX, evaluation automation, observability, and deeper privacy controls.

## Recommended Improvements

| Area | Improvement | Benefit |
| --- | --- | --- |
| Tenant configuration | Admin UI for vertical templates, quadrant logic, and thresholds | Enables self-service onboarding |
| Vector isolation | Per-tenant Qdrant collections or namespaces | Prevents cross-tenant document bleed |
| Citation UX | Show source document and section for every claim | Improves trust and compliance |
| Evaluation suite | Automate hallucination benchmark runs in CI | Makes prompt/model changes safer |
| Local-first mode | Expand Ollama and local transcription support | Strengthens privacy posture |
| Observability | Trace retrieval, model calls, and coaching outcomes | Speeds debugging and quality review |
| Role governance | Fine-grained admin permissions | Reduces misconfiguration risk |

## Future Architecture

```mermaid
flowchart LR
    Tenant[Admin Tenant Config] --> Templates[Validated Prompt Templates]
    Tenant --> Quadrants[Configurable Readiness Rules]
    Tenant --> Thresholds[Hallucination Thresholds]
    Templates --> Coach[Live Coach Runtime]
    Quadrants --> Coach
    Thresholds --> Retrieval[Scoped Retrieval]
    Retrieval --> TenantVectors[Per-Tenant Vector Collection]
    Coach --> Eval[Evaluation Suite]
```

## Screenshot

![Closer model selector](../screenshots/model-selector.png)

The model selector represents the current provider-control foundation that can evolve into tenant-specific AI configuration.
