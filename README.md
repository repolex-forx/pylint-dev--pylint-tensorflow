# Repolex Knowledge Graph of pylint-dev/pylint-tensorflow

RDF knowledge graph data for [pylint-dev/pylint-tensorflow](https://github.com/pylint-dev/pylint-tensorflow), parsed by [repolex](https://repolex.ai).

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
rlex download pylint-dev/pylint-tensorflow
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 244dd47dc14e737b66e47e296b275fee1fc6a2ee
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 244dd47dc14e737b66e47e296b275fee1fc6a2ee
│           └── chunk-001.nq.gz
├── blob
│   ├── 278dd38ee1788d3ce8467471951dbad0b4e4ddca.nq.gz
│   ├── 4ee6d015f3e85def3f7c7e3fbdfa6a2fb872d7a1.nq.gz
│   ├── 56fbef5143bdc242eee0c69e4ddc4bed5c4a263d.nq.gz
│   ├── 60fe087555c2145cbce82d30167ba6fe8cbe877e.nq.gz
│   ├── 61adbec74f22ddfa952c4ec8a445ca206d752c01.nq.gz
│   ├── 69f1089b9ef2e98cca9cd5ab111815b0d4e85630.nq.gz
│   ├── 79cb2c38d84ca3138dc25e811b9ca08e551a52aa.nq.gz
│   ├── 7e1b4ef54bf235ebb1a1e947f9c9cca3de9bc68a.nq.gz
│   ├── 809d5e1800d76f262355e07be3705d41392eb171.nq.gz
│   ├── 98e0f3f7ac7ea05379d8bbac127f8972b470f609.nq.gz
│   ├── abf697df5381ddf82ae008d33f386e0ab857ad17.nq.gz
│   ├── bbe6fc2fd06abf514ca9f3cf7cfa134479d35644.nq.gz
│   ├── d17d08fd63a9ff63f91baaa4cb3f266bbca0b2f5.nq.gz
│   ├── ddc0e789e68a29394a818f40b7b01e35204165b2.nq.gz
│   ├── e49521e1d34abd4567febebb8fef1870e06fda51.nq.gz
│   └── feb3dd851b748d14dcf86fd07bd15b58c4da5fbf.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 244dd47dc14e737b66e47e296b275fee1fc6a2ee.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 23 files
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

[pylint-dev/pylint-tensorflow](https://github.com/pylint-dev/pylint-tensorflow)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
