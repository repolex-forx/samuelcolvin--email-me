# Repolex Knowledge Graph of samuelcolvin/email-me

RDF knowledge graph data for [samuelcolvin/email-me](https://github.com/samuelcolvin/email-me), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/email-me
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c1c82606724f01f14eda71036c072d340dc259bd
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c1c82606724f01f14eda71036c072d340dc259bd
│           └── chunk-001.nq.gz
├── blob
│   ├── 06f993c5614e5b0c1f48718c22924913f8689afa.nq.gz
│   ├── 0a22260c776d86e2af1f9c5c1be72469452a2ebe.nq.gz
│   ├── 3a5e2c71a2fa1bd0d3f01b70737aefba5d8f8e53.nq.gz
│   ├── 4b9fcdb2b88e4a15ec08b67e06e9c025827be03c.nq.gz
│   ├── 4c5f2067e39fc25d9553143dacc5f4c1aacac23c.nq.gz
│   ├── 527fb9bb4451ee19dbb68d41a74cd5ed4b9a66cc.nq.gz
│   ├── 66df5fa7c156a37c605b973b22d62dcd366ae537.nq.gz
│   ├── 7c532f92d550c2a55c11f0dfee6b8df2010f95d7.nq.gz
│   ├── 8893e28efff0a090872991626d1b6af5f79b0256.nq.gz
│   ├── 907db86122e5d9d08e6e9f9ef73117353c8d8b34.nq.gz
│   ├── bf110f1102e35a9647413c032adedace0ff31f58.nq.gz
│   └── dbda739367c4af9e00393850091aa42c40c4fa9d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c1c82606724f01f14eda71036c072d340dc259bd.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 18 files
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

[samuelcolvin/email-me](https://github.com/samuelcolvin/email-me)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
