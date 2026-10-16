# Agent Memory Lab
### MemPalace · Graphiti · FalkorDB · SQLite · Python · MCP

**An engineering case study of a local, persistent AI memory architecture: from early experiments to an informed migration decision.**

[Architecture](docs/ARCHITECTURE.md) · [Experiment log](docs/EXPERIMENTS.md) · [Security](SECURITY.md) · [Next generation: Cognee](https://github.com/SantiagoFeliu/cognee-persistent-memory-stack)

## Why this exists
Agents can reason within a session but often lose decisions, relationships and operational context between sessions. This lab documents an earlier approach to persistent memory, combining a memory retrieval layer with a temporal knowledge graph and an agent-facing query interface.

**Status: historical architecture / educational documentation.** This repository is **not** a turnkey deployment, a benchmark, or a mirror of the original system. Exact versions, commands and measured results must be recovered from evidence before they are published as verified. No real memory records or production configurations are included.

## Architecture at a glance

```text
                   Local AI agents
                          |
                  MCP / query adapter
                          |
                 Python orchestration
                   /            \
          Memory retrieval    Graph queries
             MemPalace          Graphiti
                |                  |
        Persistent storage       FalkorDB
             (SQLite*)         (graph DB)
                   \            /
                  Audit / history
```
*SQLite represents the historical persistence/control layer; exact responsibilities and integration points require source-level confirmation.*

## What to learn
1. **Ingest:** normalize example records, assign stable identifiers, and preserve provenance.
2. **Remember:** store retrievable facts and decisions without confusing them with instructions.
3. **Connect:** model entities and relationships for graph exploration.
4. **Retrieve:** combine semantic recall and graph traversal through an agent-facing interface.
5. **Audit:** distinguish historical, current, inferred and verified information.
6. **Evolve:** evaluate operational complexity, reliability and maintenance before selecting a long-term stack.

## Documentation
| Document | Purpose |
|---|---|
| [Architecture](docs/ARCHITECTURE.md) | Component boundaries and illustrative flow |
| [Experiment log](docs/EXPERIMENTS.md) | Historical phases, evidence status and lessons |
| [Security policy](SECURITY.md) | Privacy and safe deployment boundaries |
| [Synthetic examples](examples/README.md) | Safe example records and intended experiments |

## Scope and honesty
- **Documented:** a local-memory engineering approach involving MemPalace, Graphiti, FalkorDB, Python, SQLite and MCP.
- **Not claimed:** a validated public installer, exact historical compatibility, comparative performance superiority, or reproducible results without test artifacts.
- **Transition:** a later Cognee-based implementation was preferred for operational needs; see the companion repository for that architecture.

## License
MIT. Third-party components retain their own licenses and terms. This repository does not distribute their source code.
