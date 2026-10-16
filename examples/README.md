# Safe synthetic dataset

The following records are entirely fictional. They are **examples of data shape**, not exports from a real agent.

See [sample_memory.jsonl](sample_memory.jsonl).

Suggested exercises:
1. Ingest records with stable `id` values.
2. Query the latest decision for project `ORION-DEMO`.
3. Extract a relation between a fictional project and its component.
4. Re-ingest the same file and check for duplicates.
5. Compare results before and after a simulated restart.

There is intentionally no production connector or historical ingestion script here. Do not execute untrusted installation scripts or expose database/MCP ports to the public Internet.
