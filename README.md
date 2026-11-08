# Repolex Knowledge Graph of zenml-io/rust-pipeline

RDF knowledge graph data for [zenml-io/rust-pipeline](https://github.com/zenml-io/rust-pipeline), parsed by [repolex](https://repolex.ai).

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
rlex download zenml-io/rust-pipeline
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c7e8ed504c935d870f123c23de5023a92a46a6f9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c7e8ed504c935d870f123c23de5023a92a46a6f9
│           └── chunk-001.nq.gz
├── blob
│   ├── 17289eb663d70ec3007211b8b1b8db91994674e8.nq.gz
│   ├── 2d00290e6c948e96e99d3276538047b807ff9bfa.nq.gz
│   ├── 393aa4a924a69511663fdf288e80de9f3d3969ce.nq.gz
│   ├── 3cd01d662c668b8923d4bf7571bd4fd3017c4f55.nq.gz
│   ├── 43977d24709831b7d44e7caba769c4f9330ef742.nq.gz
│   ├── 4b719003999f7fd6dbe4e38d36481365af6b5a97.nq.gz
│   ├── 6fb46017d25f913e210f115bb9b7d377435c384b.nq.gz
│   ├── 71094508fc470abfcfd8cb2bada1d5d3db4cae56.nq.gz
│   ├── 78a624d8c319ee66c183c2957ff7858b3ae6751a.nq.gz
│   ├── 7d73c0fa5033bb965522bf08754e5ef7f9b15e0f.nq.gz
│   ├── 81dbfe1dcd86df598cda896848582909a0674ed6.nq.gz
│   ├── 94b786302969f6401febc0c2c75d8f95b6f9eb14.nq.gz
│   ├── bb578c0b2ecab585c4187300a2676d662efb4d74.nq.gz
│   ├── c1d9ec76b3ad72231c64624d15035e4c6aebd6c6.nq.gz
│   ├── d0849658d95996256d4de660f2b822cb14f8e533.nq.gz
│   ├── d6306464c35794155fd38108dce433a20876f958.nq.gz
│   ├── e8ea3ae4fe50a602493865037f47d75411b1bbb2.nq.gz
│   └── f856d4d95ccbed1353bd98a0b332a9738fd9c80a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c7e8ed504c935d870f123c23de5023a92a46a6f9.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 24 files
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

[zenml-io/rust-pipeline](https://github.com/zenml-io/rust-pipeline)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
