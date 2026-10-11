# Repolex Knowledge Graph of bottlepy/bottle-memcache

RDF knowledge graph data for [bottlepy/bottle-memcache](https://github.com/bottlepy/bottle-memcache), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download bottlepy/bottle-memcache
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1d4ed714ccb401c3094f120d64b1427fd255e25f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1d4ed714ccb401c3094f120d64b1427fd255e25f
│           └── chunk-001.nq.gz
├── blob
│   ├── 43d268a36f446e3e2cd1f349e49f54818b9cd85b.nq.gz
│   ├── 526f7b4344b6ed7912669654697e89ed9a91c92b.nq.gz
│   ├── 8b7a409c5f59ed83b1346e35cf3d6230449732b9.nq.gz
│   ├── b917afbbdd4e1c4f16ab0ef920a1e74af8e024b9.nq.gz
│   └── d546de17222d2ad492abb8375cb59d2c3c3207bc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1d4ed714ccb401c3094f120d64b1427fd255e25f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 13 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[bottlepy/bottle-memcache](https://github.com/bottlepy/bottle-memcache)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
