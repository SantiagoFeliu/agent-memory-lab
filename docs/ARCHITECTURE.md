# Architecture — historical design and reference boundaries

> Conceptual reconstruction. Do not treat this diagram as a verified copy of a production deployment.

## Layers
| Layer | Technology / role | Notes |
|---|---|---|
| Agent interface | MCP-compatible adapter | Access control and tool contracts depend on deployment |
| Orchestration | Python | Ingestion, retrieval routing, validation and logging |
| Memory | MemPalace | Persistent recall experiments; confirm historical version from original records |
| Knowledge graph | Graphiti | Entity and relationship exploration |
| Graph store | FalkorDB | Graph database backing graph experiments |
| Persistence / control | SQLite | Local state, audit and/or memory backend depending on historical phase |
| Host | Linux | Local-first execution and service lifecycle |

## Illustrative data path
```text
Synthetic input -> validate -> normalize -> identify -> memory ingestion
                                                   -> graph ingestion
Agent query -> adapter -> memory recall + graph traversal -> provenance -> answer
```

## Design concerns
- **Idempotency:** re-ingesting the same record should not silently multiply records.
- **Provenance:** every retrieved fact needs an origin, timestamp and verification status.
- **Temporal validity:** an old decision must not override a newer decision by accident.
- **Separation:** memory retrieval, graph extraction and agent permissions are different concerns.
- **Failure handling:** record partial ingestion, retry boundaries and recovery steps.
- **Observability:** count inputs, accepted records, duplicates, failures and retrieval quality.

## Verification still required
Historical API calls, package versions, service units, SQL schemas, Node.js adapters and performance measurements are **not provided** here because they have not been independently validated for public reuse. Never infer that a conceptual component diagram is executable code.
