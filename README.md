# Repolex Knowledge Graph of datasette/datasette-export-database

RDF knowledge graph data for [datasette/datasette-export-database](https://github.com/datasette/datasette-export-database), parsed by [repolex](https://repolex.ai).

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
rlex download datasette/datasette-export-database
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ca3ba4fa052ee9b74a1c021e3744fa86156bb42e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ca3ba4fa052ee9b74a1c021e3744fa86156bb42e
│           └── chunk-001.nq.gz
├── blob
│   ├── 06b0ae393088f2fa3d30c250dbba954dad462640.nq.gz
│   ├── 0821c7b6e240b0f9397d80795e4b16e546097e9a.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 28adbceb9b4260cf2aaa4d65b679fe5e0ece29f8.nq.gz
│   ├── 29dafe9560c8491b19e61f9b0a1072ff8c7cdb4d.nq.gz
│   ├── a8a8424459f17f70e6d662f220b8c853c88de20e.nq.gz
│   ├── ab7b6637a9e370963e19074cb84d81b71726954b.nq.gz
│   └── eb22e74eaaaf0edc4aa2c0f8900a55750d1660f9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ca3ba4fa052ee9b74a1c021e3744fa86156bb42e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 16 files
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

[datasette/datasette-export-database](https://github.com/datasette/datasette-export-database)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
