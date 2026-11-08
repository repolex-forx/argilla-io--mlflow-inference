# Repolex Knowledge Graph of argilla-io/mlflow-inference

RDF knowledge graph data for [argilla-io/mlflow-inference](https://github.com/argilla-io/mlflow-inference), parsed by [repolex](https://repolex.ai).

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
rlex download argilla-io/mlflow-inference
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 83aa0246adfd6f452bd27e5cc8a052ce2a9d2bf2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 83aa0246adfd6f452bd27e5cc8a052ce2a9d2bf2
│           └── chunk-001.nq.gz
├── blob
│   ├── 16bf7e84d7b78246a1a0b68ca0897979904f1f28.nq.gz
│   ├── 1d4e7389d3a3afc6a269e7e2ef175cea4d2b857e.nq.gz
│   ├── 21d733af932c27a1da4b224c8e7e5d7101c31b9e.nq.gz
│   ├── 39c589ebd363be8021bd8693d06939d05d5bd492.nq.gz
│   ├── 3e88b3354268e1d74d018efff31e5d93242f1d63.nq.gz
│   ├── 42ff2026c7fdbd1e3894c95184b506a4d9d35dc3.nq.gz
│   ├── 5f247e2aa91a190df80f04f3519c6badb5d034c6.nq.gz
│   ├── 6406efa212a2efec61f0572bf6105d5a59890f05.nq.gz
│   ├── 790c8bda44bc6847e126c956da8958e182924a48.nq.gz
│   ├── 7cbb327a3badc74f08605e6a962f3c3141148525.nq.gz
│   ├── 7e95c8fd5aa949957606e4335203099a64eb6e1e.nq.gz
│   ├── 8827e712bf9c1e6114eee3763c05ae4fe1f19ba8.nq.gz
│   ├── 8dfe81b1dfeb216fcf27b32a077ca837bcf5ec9f.nq.gz
│   ├── 9b34a14449906bd8eb1776eee405b3dfb25e1930.nq.gz
│   ├── d66a068dfc6d469fdba8ef828ef369df352d4c04.nq.gz
│   ├── d8ea29c247411de202fae75a9741c1449ba875aa.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e7bd7c764f89e43355c567acfbe2587fb89d2e67.nq.gz
│   └── fc88ef30ebfc08081eaecbc3cf8bb8421f62153d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 83aa0246adfd6f452bd27e5cc8a052ce2a9d2bf2.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 25 files
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

[argilla-io/mlflow-inference](https://github.com/argilla-io/mlflow-inference)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
