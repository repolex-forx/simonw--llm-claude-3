# Repolex Knowledge Graph of simonw/llm-claude-3

RDF knowledge graph data for [simonw/llm-claude-3](https://github.com/simonw/llm-claude-3), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/llm-claude-3
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5b42bfc3e5140e0849895fc4802190ae67c8f1bf
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5b42bfc3e5140e0849895fc4802190ae67c8f1bf
│           └── chunk-001.nq.gz
├── blob
│   ├── 1b4670be97db7e57d67c42b112c7805bce887471.nq.gz
│   ├── 258a0061eb1a869d35dafd6b5ef1db2aec4f4095.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 46512d87a0840472e302ac76f29709e47491c72d.nq.gz
│   ├── 5840e702f99184e6bdc710c260f2f161224fd44e.nq.gz
│   ├── 73a4fa04b4fbe180d2641b23e23a4935b1c598ff.nq.gz
│   ├── 7cad1b32a020a1acbd9b1302bf286df9462db97d.nq.gz
│   ├── 8c9d07d3f65367b3a9107855578361fc33cd9d9b.nq.gz
│   ├── ae1edc2b2a54be06557f2a75c7ab90cdffef2ab1.nq.gz
│   ├── ba3fb3b930e3e9d1ca175e73876fa7ad7f39b752.nq.gz
│   ├── cff0255e8f4222c098e8ddc8206ccb4c02cea3da.nq.gz
│   ├── e61ce1d68a38f43ce1ad952ccdb94f9ab7d69670.nq.gz
│   ├── e64c5fb1b4a400207db9aa48939e100131b6dfef.nq.gz
│   └── eb1b09110e942f55943936da0b32c64e79b298d2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5b42bfc3e5140e0849895fc4802190ae67c8f1bf.nq.gz
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

[simonw/llm-claude-3](https://github.com/simonw/llm-claude-3)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
