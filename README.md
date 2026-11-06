# Repolex Knowledge Graph of sphinx-contrib/cmakedomain

RDF knowledge graph data for [sphinx-contrib/cmakedomain](https://github.com/sphinx-contrib/cmakedomain), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/cmakedomain
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── df970be527b41842939d2368195ab3aed8428428
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── df970be527b41842939d2368195ab3aed8428428
│           └── chunk-001.nq.gz
├── blob
│   ├── 21bd2391dd94e407eb2fe22a4691f4911afdadd6.nq.gz
│   ├── 4cbd247d30c1a9f3881181cdca4b52dcf1f94c7c.nq.gz
│   ├── 8e7e2bc0d26ebc39199523caf9850ff62f3d650a.nq.gz
│   ├── 926cc7b14c1ecdca8d3c7ae299350d98a3f9c905.nq.gz
│   ├── 993f837214c1a0b9179e2b10e2fa2cb7a85359fa.nq.gz
│   ├── a028f58239a7470b57cb5c956aad9b025ff07f53.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   └── bfb9f4b5e992f8af7ca8153e93dab5c67e47976f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── df970be527b41842939d2368195ab3aed8428428.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 14 files
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

[sphinx-contrib/cmakedomain](https://github.com/sphinx-contrib/cmakedomain)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
