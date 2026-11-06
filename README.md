# Repolex Knowledge Graph of tinylibs/tinyspy

RDF knowledge graph data for [tinylibs/tinyspy](https://github.com/tinylibs/tinyspy), parsed by [repolex](https://repolex.ai).

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
rlex download tinylibs/tinyspy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3d2c9c8550061066a07cfb5c6e97f73e544675a5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3d2c9c8550061066a07cfb5c6e97f73e544675a5
│           └── chunk-001.nq.gz
├── blob
│   ├── 0904d96c0e4de148fad3bb2658860b45288f1fd8.nq.gz
│   ├── 0d1d7861e20a362953474119a640016bbee05475.nq.gz
│   ├── 0e727b1aa8a570d822e970b9a980af037fca8cf8.nq.gz
│   ├── 31354ec1389994b5f6708c7d915fdcc6bb76ba6e.nq.gz
│   ├── 384091a27a4916491eed9a0a2d53185fb462626b.nq.gz
│   ├── 3c9948f998bea5087a60d7784ce1f2599625e491.nq.gz
│   ├── 48d532ba3f348d157bbcc33aad7d54c17201c597.nq.gz
│   ├── 4d6219bde34f5654e99703138c5f2e1bcc4c8ac2.nq.gz
│   ├── 4f4bdf1aa32d01d2491bb2cdd5f7cd8e7209986c.nq.gz
│   ├── 54290fca99f7f646d90e93361afe98f7f995118e.nq.gz
│   ├── 592dddf12cf81fdf1eb03fc00052fb1142d607ea.nq.gz
│   ├── 627c8fce22242156b04e081e5df3bb9913fcf214.nq.gz
│   ├── 64143b80f2f1d7ae553251bdb129e850ce78df6a.nq.gz
│   ├── 68d52e712e5c4e3fdc3ee13f2dad22f2bb859bd1.nq.gz
│   ├── 6facc43ecb0fa28fe6c707c3c58bc472096fa1ab.nq.gz
│   ├── 7bc138e9bb36354943a06be2e78558b73825d25e.nq.gz
│   ├── 879ff0ef8aa22a84dbb51e199d2012e46058a0f4.nq.gz
│   ├── 9a1e54e902221f4471d4653347d118c6be6fc36a.nq.gz
│   ├── 9baaad0a442705ef2c236814b86627b26752030e.nq.gz
│   ├── 9dd708469438530fe5239229d8c7777017e51e96.nq.gz
│   ├── afc61a3da6552d7677998c3d2b4a646480343042.nq.gz
│   ├── b138c0adccdd0f58377149827e092a99a9010ae5.nq.gz
│   ├── b95fe5cc44a3d6e503c383975c3f3ca882d143bf.nq.gz
│   ├── c623ee04970a91f1340e65b289b8fbe10e580175.nq.gz
│   ├── c886661aeb234126402688b96c30cfc92da63d6a.nq.gz
│   ├── cd40595050dd6616f001485f1a6b8f3943185c00.nq.gz
│   ├── d13faa154de92588a6cbacea153db26c88b2afae.nq.gz
│   ├── e3a206a38f37a0027a870478418cfdc578ea12b2.nq.gz
│   ├── e8ddd98e804c77165f7bd200fe3f2f516b55c632.nq.gz
│   └── ef4c3e73235b708bebcbab1a17498b897955aa19.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3d2c9c8550061066a07cfb5c6e97f73e544675a5.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 38 files
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

[tinylibs/tinyspy](https://github.com/tinylibs/tinyspy)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
