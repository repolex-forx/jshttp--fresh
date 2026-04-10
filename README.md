# Repolex Knowledge Graph of jshttp/fresh

RDF knowledge graph data for [jshttp/fresh](https://github.com/jshttp/fresh), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download jshttp/fresh
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f185ef1376c0337d366f9e35bda92b053983fd81
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── f185ef1376c0337d366f9e35bda92b053983fd81.nq.gz
│   └── repolex
│       └── f185ef1376c0337d366f9e35bda92b053983fd81
│           └── chunk-001.nq.gz
├── blob
│   ├── 0972d12525f64251988e7240411690cff1b8582f.nq.gz
│   ├── 1434ade75d1fc4faf25a6ac5daed813e12eaed28.nq.gz
│   ├── 250e50b602f756eff17b38e4b9fe9b6180b8c3cf.nq.gz
│   ├── 2cd213c1cd8cafbee719bca7ed995d51136cbbcb.nq.gz
│   ├── 3bfd85a781a3738609cbf0fa57a1e9bda276b9ec.nq.gz
│   ├── 43c97e719a5a824700932f72e6e7e6748ce45d01.nq.gz
│   ├── 5d7e2157f31d97514c00437582b77d3686b12ebd.nq.gz
│   ├── 62562b74a3b5a79e82ca417b02e0f597d85f5e2f.nq.gz
│   ├── 9808c3b2b6602da61eb4afcb4caf33368e3e2bd4.nq.gz
│   ├── a7df8152945ac696cdea7436b2afac0e6c2b1ae1.nq.gz
│   ├── cf3015fb3b6ee818a7e76aff5854cde130fc5fe0.nq.gz
│   ├── e2d8b680f8ef0813f97af2cbebe75ec787e39617.nq.gz
│   ├── ebedc035fbc3911ada5ad8e69f3a38e6e820ce4a.nq.gz
│   ├── fc3dea7b4ae085168714ffb7b7fbe01646e858a5.nq.gz
│   ├── fd3888acb4dd7a0cdb0dae0761c593c95802d6be.nq.gz
│   └── fd79c5b525a9d373331b39a48eaced9003877f1a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── f185ef1376c0337d366f9e35bda92b053983fd81.nq.gz
├── filetree
│   └── f185ef1376c0337d366f9e35bda92b053983fd81.nq.gz
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

## Source repository

[jshttp/fresh](https://github.com/jshttp/fresh)

---
*Parsed on 2026-04-10 by [repolex](https://repolex.ai)*
