# Experiment history and engineering decisions

This is an educational account of the exploration, not a synthetic benchmark dressed up as real measurements.

## Phase A — persistent recall
**Question:** Can an agent recover context across sessions without loading an entire conversation archive?

Approach: experiment with MemPalace as a persistence and retrieval layer; evaluate relevance, repeated ingestion and continuity.

## Phase B — connected knowledge
**Question:** Can relationships between projects, actors, decisions and events be queried explicitly?

Approach: introduce Graphiti and FalkorDB for entity and relationship exploration.

## Phase C — unified access
**Question:** Can agents query the memory layer without depending on implementation-specific details?

Approach: route retrieval through Python and an MCP-oriented interface; keep audit/control state separate from user-facing answers.

## Phase D — operational evaluation
Evaluation dimensions: ingestion repeatability, retrieval fidelity, recoverability, graph consistency, maintenance overhead, isolation and security.

## Phase E — architecture evolution
The subsequent Cognee architecture was selected for the author's operational requirements. **This is a design decision, not proof that Cognee is universally faster or better than MemPalace or Graphiti.** A credible comparison requires the same dataset, hardware, workloads, metrics and versions.

## Evidence register
| Claim | Status |
|---|---|
| MemPalace and Graphiti were part of earlier local-memory exploration | Historical project context; implementation details to be verified |
| FalkorDB, SQLite, Python and MCP were considered/integrated in the architecture | Historical project context; exact topology to be verified |
| Specific record counts, throughput, latencies and success rates | **Not published: source evidence pending** |
| Public example installation passes end-to-end tests | **Not yet implemented** |

## How to reproduce the methodology
Use only synthetic records; document exact dependency versions; run cold-start and restart tests; insert duplicates; verify retrieval with known answers; test stale decisions; record errors; publish machine-readable test results before asserting PASS.
