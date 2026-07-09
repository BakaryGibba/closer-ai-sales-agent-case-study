[Back to README](../README.md)

# 08 Data Model

## Data Model Summary

Closer's dashboard data model centers on organizations, users, customers, sessions, documents, and relationship memory. The multi-tenant roadmap extends this with tenant-specific AI configuration, prompts, quadrant logic, vector namespaces, and hallucination thresholds.

## Conceptual ERD

```mermaid
erDiagram
    ORGANIZATION ||--o{ USER : has
    ORGANIZATION ||--o{ CUSTOMER : owns
    ORGANIZATION ||--o{ DOCUMENT : owns
    CUSTOMER ||--o{ SESSION : participates_in
    SESSION ||--o{ COACHING_EVENT : contains
    CUSTOMER ||--o{ RELATIONSHIP_MEMORY : accumulates
    ORGANIZATION ||--o| TENANT_AI_CONFIG : configures

    ORGANIZATION {
        int id
        string name
        string industry
    }

    USER {
        int id
        int organization_id
        string email
        string role
    }

    CUSTOMER {
        int id
        int organization_id
        string name
        string segment
    }

    SESSION {
        int id
        int customer_id
        int user_id
        datetime started_at
        string status
    }

    DOCUMENT {
        int id
        int organization_id
        string name
        string status
    }

    TENANT_AI_CONFIG {
        int organization_id
        string vertical
        json quadrant_config
        float hallucination_threshold
    }
```

## Multi-Tenant Direction

The project identifies a key future requirement: remove hardcoded financial-services assumptions and make the assistant configurable by tenant and industry.

## Screenshot

![Closer customer profile](../screenshots/customer-profile.png)

The customer profile illustrates how sessions become durable relationship memory, priorities, and warning signals.
