# Repolex Knowledge Graph of glue-viz/glue-openspace

RDF knowledge graph data for [glue-viz/glue-openspace](https://github.com/glue-viz/glue-openspace), parsed by [repolex](https://repolex.ai).

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
rlex download glue-viz/glue-openspace
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c75fd25b24f459e0b0e83a7b4e18cfe3f1ccfb31
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c75fd25b24f459e0b0e83a7b4e18cfe3f1ccfb31
│           └── chunk-001.nq.gz
├── blob
│   ├── 0782c29bfda959fb832ef25b4feba120701a94a6.nq.gz
│   ├── 2e0ba64fec2f7e3f7bc16bd135e93e5a06aa3caf.nq.gz
│   ├── 2eaafd4680a77c0becc0ae3def95f84d1be1a1d6.nq.gz
│   ├── 386534bc3c00a6773ef6e2ccaa02c97bcaec4520.nq.gz
│   ├── 3f68dd8c84b5625a54494e1703068df12925658f.nq.gz
│   ├── 52a3ad095926de8ddb1c57d36a94d8f87d25e75e.nq.gz
│   ├── 68bc040ad3902f11045879459cb5f99046bc4d69.nq.gz
│   ├── 6a56a2327f8e271c882e1391d68896102cc30c99.nq.gz
│   ├── 714059ab50f3bd2df2837fb0aa0987eff012f0e2.nq.gz
│   ├── 729f7e99635910f228935099f3978d16de7b1729.nq.gz
│   ├── 74667e3daa62b274fc8f0f33a879e780bab03c7b.nq.gz
│   ├── 8d445604a95ac6a51874b6a1cbc812920719839a.nq.gz
│   ├── adb1c92eac1944d7a1ae830946a2ec648c734ac0.nq.gz
│   ├── cabf023c81bafe3b384c174b9b9fa6aa8cf4b471.nq.gz
│   ├── cdb0add835f6687456504bb2f3c0d5b136420686.nq.gz
│   ├── f15282391d7d0aa3461c862c84a05a7456bac4dc.nq.gz
│   ├── f1ea6b3b1a0408438a8747dbd01fd327ee703b8d.nq.gz
│   └── fa621660315376a6588ebe5f29dc09b23a0f7615.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c75fd25b24f459e0b0e83a7b4e18cfe3f1ccfb31.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 26 files
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

[glue-viz/glue-openspace](https://github.com/glue-viz/glue-openspace)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
