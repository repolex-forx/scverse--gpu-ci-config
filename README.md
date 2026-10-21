# Repolex Knowledge Graph of scverse/gpu-ci-config

RDF knowledge graph data for [scverse/gpu-ci-config](https://github.com/scverse/gpu-ci-config), parsed by [repolex](https://repolex.ai).

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
rlex download scverse/gpu-ci-config
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d877dcfddbcda55c8bfbe0c21490814f2f23e6f5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d877dcfddbcda55c8bfbe0c21490814f2f23e6f5
│           └── chunk-001.nq.gz
├── blob
│   ├── 01e842ee07a8b3fb1f9f51c3ea2bd4d60ea5a07d.nq.gz
│   ├── 11965977cd0e477632d406e339bc55d05addc583.nq.gz
│   ├── 13505d522b3ced237eaded3a5f646f83a8590f0d.nq.gz
│   ├── 16d65c73f55691bab0e10d51d5f59bbc78e57608.nq.gz
│   ├── 210a4ba7dcd626f689adde710db636a76ae2259d.nq.gz
│   ├── 34fdb2464e5e4495148846477de54a60b119f144.nq.gz
│   ├── 400dfd7e94a5ce63c4ecee4214e32ec257b22a90.nq.gz
│   ├── 62f464718f6bf43eeae877c0968d4a0a4297dcbd.nq.gz
│   ├── 6930e502c819b56e48318dc8d274b67269017fa1.nq.gz
│   ├── 7539c5b71275841b15ad8c2f1f050c2e2127a0b2.nq.gz
│   ├── 9cbb9b7c4e39ff2b928bcd62b2d0316e944caee5.nq.gz
│   ├── 9fc36fa8109b70fcd952d2b40054c440d52a3843.nq.gz
│   ├── a0367779cf62d62eb43d26be8bf8844cbba467f7.nq.gz
│   ├── a16c1849f103d65e6ec8090a8665f564828134e0.nq.gz
│   ├── ba06b1dfa4429ed1f14d43b15c27687d9d092c39.nq.gz
│   └── c4f45b67a0d976b8d07f91080ad6b2f552d99a8b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d877dcfddbcda55c8bfbe0c21490814f2f23e6f5.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[scverse/gpu-ci-config](https://github.com/scverse/gpu-ci-config)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
