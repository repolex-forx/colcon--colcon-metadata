# Repolex Knowledge Graph of colcon/colcon-metadata

RDF knowledge graph data for [colcon/colcon-metadata](https://github.com/colcon/colcon-metadata), parsed by [repolex](https://repolex.ai).

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
rlex download colcon/colcon-metadata
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e9e5c2dbe535cda30b98e1b4bd457cfd5c0c1089
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e9e5c2dbe535cda30b98e1b4bd457cfd5c0c1089
│           └── chunk-001.nq.gz
├── blob
│   ├── 03ef61290adf0b581be05f32ece6109514c172e3.nq.gz
│   ├── 0f17157ed42b486a0c57cbffddd97987a4844e6b.nq.gz
│   ├── 1794afb987da483964e41119b773eefdabaad643.nq.gz
│   ├── 1981d89ef889fd3dfed7ba32b2f354616bff7e0f.nq.gz
│   ├── 2386477313004d4b3e1d217b744bb6cf6c3f3719.nq.gz
│   ├── 25d208dbd6810054dbe0ee3db7c7dcd802546be7.nq.gz
│   ├── 326bb66d4c74f0cf8cf0dfc4e79909001f37da84.nq.gz
│   ├── 3399134af0abcc2e6a441f0cafd6c11a918226e3.nq.gz
│   ├── 3450da102a0ec9fdfd92570dee2c5c4a0b2f4129.nq.gz
│   ├── 3df67e9ba1dfa1e76dca599df8e5b72cae7567b4.nq.gz
│   ├── 403553675bc25d08958ae60903af2d4baf67d408.nq.gz
│   ├── 41d1bf1258629214994288f9ca4302acbac1062b.nq.gz
│   ├── 458d5a717ddbdf5ee594d423f6e48580ed6b1e30.nq.gz
│   ├── 4bfa5809e958b96e7ce5aec9321923cbefa77320.nq.gz
│   ├── 71fca3bf29bac9dddf52825c89d7e5132ff97539.nq.gz
│   ├── 80e11d64db1f85cac7618a6119278d2dea8675f0.nq.gz
│   ├── 8d315d51e4f6e4f533a08823b5cc3627e9540cc2.nq.gz
│   ├── a07d31d29b070c6413532f1f6ba1745e45d31fb2.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── da1ecaf5e80bc3802e2d44f042744163710402c7.nq.gz
│   ├── dffe460f162da9929178a7ce342532e7ba896425.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e6ed464c37cf1093c2c611815f773c8a6e4e5c22.nq.gz
│   ├── e82fd0b0abbf1472480d19d468efe7819276e80d.nq.gz
│   └── f2927614ebfb7c95f2c9145c53460bd679a3864a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e9e5c2dbe535cda30b98e1b4bd457cfd5c0c1089.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 33 files
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

[colcon/colcon-metadata](https://github.com/colcon/colcon-metadata)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
