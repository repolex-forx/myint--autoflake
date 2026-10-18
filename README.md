# Repolex Knowledge Graph of myint/autoflake

RDF knowledge graph data for [myint/autoflake](https://github.com/myint/autoflake), parsed by [repolex](https://repolex.ai).

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
rlex download myint/autoflake
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8b019503c6fdb4e59df8293ec7d3115b4ebaec0b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8b019503c6fdb4e59df8293ec7d3115b4ebaec0b
│           └── chunk-001.nq.gz
├── blob
│   ├── 042e9195238d1996dd6e6c7ae88ecc72026870c6.nq.gz
│   ├── 0b3d9400e150450b8220ccc5327080321ba1dc94.nq.gz
│   ├── 1a424026a2aeffe4fe42ecff1888dbe3431a3901.nq.gz
│   ├── 5e704b4949d9f8869ff6b4877e0629112a9ef617.nq.gz
│   ├── 69ee414d28c953f948d8eb4776100c3bb7b8f583.nq.gz
│   ├── 73e5153da57f82eed92bd46f00d7907c2a265355.nq.gz
│   ├── 7515033434e746674538e0fac1adca8b921e95ce.nq.gz
│   ├── 8c7b09949f2b07beeeda1e201ef5e26bfa525ef9.nq.gz
│   ├── 8d513fbfd5817863194a0957e0a7331e0f31dd00.nq.gz
│   ├── 915894de017de4edf50c069ee8ec34ceaefe483b.nq.gz
│   ├── 93fbd999f3b79d2eea95a988a8a22b71c5927362.nq.gz
│   ├── 99a2df2f441a4532eb0c5d0e834a3957729ce396.nq.gz
│   ├── 9b80f4d014629b6fe930df912211b4ce3be476c6.nq.gz
│   ├── e002980528d7b475e079caeeea074a83d041a29c.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f6f87a3ab2bff090801342868a4456654765d968.nq.gz
│   └── fcf28f1fbe5f8585aa6593a8e0b6581bb8961aaf.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8b019503c6fdb4e59df8293ec7d3115b4ebaec0b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[myint/autoflake](https://github.com/myint/autoflake)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
