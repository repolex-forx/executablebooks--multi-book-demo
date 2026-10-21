# Repolex Knowledge Graph of executablebooks/multi-book-demo

RDF knowledge graph data for [executablebooks/multi-book-demo](https://github.com/executablebooks/multi-book-demo), parsed by [repolex](https://repolex.ai).

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
rlex download executablebooks/multi-book-demo
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 763fa31e4dae22eecfc23896c54332057426c060
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 763fa31e4dae22eecfc23896c54332057426c060
│           └── chunk-001.nq.gz
├── blob
│   ├── 0f4e9f2c038fed0baaff46e5bf3e1e1696b7aa2a.nq.gz
│   ├── 5b4ae96cf1dbaf6ca63a92a8310dd30f395200fc.nq.gz
│   ├── 67afeb0c04c9861f607cb38297b9ec4bd633eecd.nq.gz
│   ├── 69a454459afa623c41f9dc4849d05d7dd7e8686b.nq.gz
│   ├── 7f5996342babd763b700be46b55e307a16e9dde5.nq.gz
│   ├── 839e8dfd18a553f82f60dff717c38847e703fdda.nq.gz
│   ├── 874b83265bf791f0f0172674838f5ac71480fe4b.nq.gz
│   ├── a3d524e669488f579b3cd0c90a00d9dc31bbc511.nq.gz
│   ├── ade1def9497b3d2a29800697403ca40d999590c1.nq.gz
│   └── d4bb2cbb9eddb1bb1b4f366623044af8e4830919.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 763fa31e4dae22eecfc23896c54332057426c060.nq.gz
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

[executablebooks/multi-book-demo](https://github.com/executablebooks/multi-book-demo)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
