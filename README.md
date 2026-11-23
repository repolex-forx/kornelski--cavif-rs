# Repolex Knowledge Graph of kornelski/cavif-rs

RDF knowledge graph data for [kornelski/cavif-rs](https://github.com/kornelski/cavif-rs), parsed by [repolex](https://repolex.ai).

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
rlex download kornelski/cavif-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e6abcbc6d689cac933492f4b141917d63361596a
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── e6abcbc6d689cac933492f4b141917d63361596a.nq.gz
│   └── repolex
│       └── e6abcbc6d689cac933492f4b141917d63361596a
│           └── chunk-001.nq.gz
├── blob
│   ├── 021e5aec8df87f078f5c610522064066b5651ef7.nq.gz
│   ├── 0897941873402e5427baa5740af2f8de752b34e3.nq.gz
│   ├── 16cfaa91259397baef67258fcd9b0c7afa14f36c.nq.gz
│   ├── 1fecced2b4333bd7c371904b515d088aceb19a85.nq.gz
│   ├── 2c96eb1b6517f2617f9ddeae9f07f5fd7bd7ddef.nq.gz
│   ├── 41f5d513b9d45d8a7696cf0d5db7ef47943055b8.nq.gz
│   ├── 5de37b3280f7bebb7eb662f2ac88c515da3b3b3c.nq.gz
│   ├── 5f6cf7fd50caab558af111521c3e5a18c6975806.nq.gz
│   ├── 7d9fa2401c025bfee35f66127081986ae4856648.nq.gz
│   ├── 9543bd0881f8bc76f48908d35fc79d482bcbe1ed.nq.gz
│   ├── 9d131b6d503ab25130e774100fa1671d77d01b59.nq.gz
│   ├── afcd5f4cc280fe4b92eb33eb124da34cc970bc04.nq.gz
│   ├── b4aa326e8c759f3baf541ecc8bca0ed2eef0c8cf.nq.gz
│   ├── bf160182d3d52be55cb3befb103285387862634d.nq.gz
│   ├── ea5b60640b01f74e295037aa8a6b7d4ea278a739.nq.gz
│   └── f89a211f32b9dbc5475b5ee08ded1fd668f08602.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── e6abcbc6d689cac933492f4b141917d63361596a.nq.gz
├── filetree
│   └── e6abcbc6d689cac933492f4b141917d63361596a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 26 files
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

[kornelski/cavif-rs](https://github.com/kornelski/cavif-rs)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
