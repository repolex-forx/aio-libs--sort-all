# Repolex Knowledge Graph of aio-libs/sort-all

RDF knowledge graph data for [aio-libs/sort-all](https://github.com/aio-libs/sort-all), parsed by [repolex](https://repolex.ai).

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
rlex download aio-libs/sort-all
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0caa98df16fd6d9f6b8d043eca559c2e1face450
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0caa98df16fd6d9f6b8d043eca559c2e1face450
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b2f7b0655f41276d418ca8302dbaec8b7e7e829.nq.gz
│   ├── 201724e006f855331e5dbc41e8b69be98be31529.nq.gz
│   ├── 25a324901766865c059af3c9af2a17d2b4655165.nq.gz
│   ├── 3c1a0d3013022310d9a092eda6c1b9d5a4989d18.nq.gz
│   ├── 4be291baac61c4ba77a0d9b6c22391bfdabaf392.nq.gz
│   ├── 4fd42667830a086df8dbabab7d64f89dbb776645.nq.gz
│   ├── 59b9e9d574241a5a65a560bb780080f33fb86776.nq.gz
│   ├── 606849326a4002007fd42060b51e69a19c18675c.nq.gz
│   ├── 73a934e290552160cae50050c11decfb440a065a.nq.gz
│   ├── 75becf75f7d9fe831d8c6fe9fd36d5076c306a39.nq.gz
│   ├── 898dc90bea5379f720a84d022c96828de5473780.nq.gz
│   ├── 9179b31d8080ff573c9eccae5f2a0535c8defa1f.nq.gz
│   ├── b08969e29b8966fd26337c924a10e0ed5c5f9775.nq.gz
│   └── b6e47617de110dea7ca47e087ff1347cc2646eda.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0caa98df16fd6d9f6b8d043eca559c2e1face450.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[aio-libs/sort-all](https://github.com/aio-libs/sort-all)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
