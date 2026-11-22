# Repolex Knowledge Graph of BurntSushi/same-file

RDF knowledge graph data for [BurntSushi/same-file](https://github.com/BurntSushi/same-file), parsed by [repolex](https://repolex.ai).

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
rlex download BurntSushi/same-file
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5799cd323b8eefd17a089c950dac113f66c89c9e
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 5799cd323b8eefd17a089c950dac113f66c89c9e.nq.gz
│   └── repolex
│       └── 5799cd323b8eefd17a089c950dac113f66c89c9e
│           └── chunk-001.nq.gz
├── blob
│   ├── 1078695d98bd7408ce96ce75bf4c041d3c84a8c6.nq.gz
│   ├── 2c45fdf8dd793da26bcd1bcc866fd685f1cc6ab7.nq.gz
│   ├── 3303149e523a4cb762a54e2b73b67f2f3c105769.nq.gz
│   ├── 42828fafcf772d5b19aea191d1e108aec8bf5048.nq.gz
│   ├── 68a49daad8ff7e35068f2b7a97d643aab440eaec.nq.gz
│   ├── 69247399770e82f75abc3bd49a89a03e53ae4919.nq.gz
│   ├── 6ba948a4c873c5915c56248ff8e5774b52e5c7f0.nq.gz
│   ├── 6bfbdea0d60b7f01949a5b4d869e6a855e28bb8d.nq.gz
│   ├── 79a6b86414313a0f3f2f41ea79a3070d30817d88.nq.gz
│   ├── 9fdfc46a8fca6dac7b71cc8d10546a752ba3a8c0.nq.gz
│   ├── aa37a218b97e5f6ad37a74a62b50727279a5e460.nq.gz
│   ├── bb9c20a094e41b7632d63bcff20c0b4b95e80777.nq.gz
│   ├── ed7ccf50906bdb2088a538542efe91e25ebcc353.nq.gz
│   └── fb3d19ff8fa732c350a7557fe8c366c6aef66949.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 5799cd323b8eefd17a089c950dac113f66c89c9e.nq.gz
├── filetree
│   └── 5799cd323b8eefd17a089c950dac113f66c89c9e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 24 files
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

[BurntSushi/same-file](https://github.com/BurntSushi/same-file)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
