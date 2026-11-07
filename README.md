# Repolex Knowledge Graph of plotly/dash-ai-chat-tutorial

RDF knowledge graph data for [plotly/dash-ai-chat-tutorial](https://github.com/plotly/dash-ai-chat-tutorial), parsed by [repolex](https://repolex.ai).

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
rlex download plotly/dash-ai-chat-tutorial
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9dea428e9de7102c92fdbdf027927ce86ee126a2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9dea428e9de7102c92fdbdf027927ce86ee126a2
│           └── chunk-001.nq.gz
├── blob
│   ├── 1a43202e28b143d60fce2b4585e2aaa3a32beb61.nq.gz
│   ├── 385a1a7f972e7e52e8c58060e4f06c38a8d88cf4.nq.gz
│   ├── 392fdbcbde2a40400c9375bbbc4a8597b46f9620.nq.gz
│   ├── b15e2344986c44f8a6b75da3d34b8124e6950798.nq.gz
│   └── c02cd61c1dd4e981f8291fe8e766d3752e2c830a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9dea428e9de7102c92fdbdf027927ce86ee126a2.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 11 files
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

[plotly/dash-ai-chat-tutorial](https://github.com/plotly/dash-ai-chat-tutorial)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
