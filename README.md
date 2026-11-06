# Repolex Knowledge Graph of sphinx-contrib/sphinx-contrib-rapidoc

RDF knowledge graph data for [sphinx-contrib/sphinx-contrib-rapidoc](https://github.com/sphinx-contrib/sphinx-contrib-rapidoc), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/sphinx-contrib-rapidoc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b1ece327c26854e6867e2d0670a8ade753354948
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b1ece327c26854e6867e2d0670a8ade753354948
│           └── chunk-001.nq.gz
├── blob
│   ├── 124dfd17d44d67b8f064ce1e358b8a8f682b9e7f.nq.gz
│   ├── 16b8147ae83f7e6f4e33cff7821ae41aa797f69a.nq.gz
│   ├── 1d45dc6ea30fb622e1c50396757105770b0b9685.nq.gz
│   ├── 29166b93e2848d891b3000ea0599659d1671c819.nq.gz
│   ├── 35ad6d891aebb45d38db2963998864c7b3ae47ae.nq.gz
│   ├── 479ab3158bdf8f2d94c36c07c759c08706e290ce.nq.gz
│   ├── 4c1e5f536019779d3e59d53f9735612af8fe92e6.nq.gz
│   ├── 50cde3f1f12cdd21737881b1cd4a5507d3595539.nq.gz
│   ├── 5acb1a6f03c8ac270d377335465dc8c0e17d4110.nq.gz
│   ├── 99fba323a10954b0455cbe9ef41a691262305249.nq.gz
│   ├── 9aac9ebcc5567bbbb81b97d25c099825aeff2b61.nq.gz
│   ├── ae0f862b865ef2f17cee6a962d8fb480d7229488.nq.gz
│   ├── b3b024f30c915acd0461793492058b1f083a57dd.nq.gz
│   ├── beda28e821662c8d9fdefee034d83a5d75f9c023.nq.gz
│   ├── c656086a02db4b9f845659eeec893376f86a7fd7.nq.gz
│   ├── cac5ede7d714c3b686683f9a637f12bcdd8baca8.nq.gz
│   ├── e079f8a6038dd2dc8512967540f96ee0de172067.nq.gz
│   ├── e1095ce6e088a91932b1fab6e53a0f1801a767e1.nq.gz
│   ├── e5202edc75b482e4294cd7bd5b5e7d3b83b26102.nq.gz
│   └── f05540e5117f9c3941cffc85fe4cffcd9075ddf0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b1ece327c26854e6867e2d0670a8ade753354948.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 27 files
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

[sphinx-contrib/sphinx-contrib-rapidoc](https://github.com/sphinx-contrib/sphinx-contrib-rapidoc)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
