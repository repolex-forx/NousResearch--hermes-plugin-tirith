# Repolex Knowledge Graph of NousResearch/hermes-plugin-tirith

RDF knowledge graph data for [NousResearch/hermes-plugin-tirith](https://github.com/NousResearch/hermes-plugin-tirith), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-plugin-tirith
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 77405987e6c0ba4e1ae45a954abaa0ce20fbf0c5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 77405987e6c0ba4e1ae45a954abaa0ce20fbf0c5
│           └── chunk-001.nq.gz
├── blob
│   ├── 5700b997827973cb0eb6d84a2782bb08a5872434.nq.gz
│   ├── 5a586926183474cb62f37000225821c7074e219b.nq.gz
│   ├── 653917b7ae4645596e16bfb336433d7c4c5f36c6.nq.gz
│   ├── 75c61823b87164dde85ad0f2c78c300e011cc8a2.nq.gz
│   ├── 7de177aa7458557601b4e47d415a7be7f21c681b.nq.gz
│   ├── a1a5447fed90f6b8c7c6aa113d8568df2b0c48df.nq.gz
│   ├── afb1b2a9ed01aca153a134bd8c9cce5d1de31ead.nq.gz
│   ├── b0d1c323c4ce0e1ec794eb089d891af7075070d7.nq.gz
│   ├── e0f11c3013923efa1155029fda862716aa94ae25.nq.gz
│   └── e7b2d2857d3a7160312590a6a30ca1a277d0b94d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 77405987e6c0ba4e1ae45a954abaa0ce20fbf0c5.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 16 files
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

[NousResearch/hermes-plugin-tirith](https://github.com/NousResearch/hermes-plugin-tirith)

---
*Parsed on 2026-10-09 by [repolex](https://repolex.ai)*
