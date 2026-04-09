# Repolex Knowledge Graph of rbarrois/uconf

RDF knowledge graph data for [rbarrois/uconf](https://github.com/rbarrois/uconf), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download rbarrois/uconf
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a90813d767615291a4085558b46fe471ce81f409
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── a90813d767615291a4085558b46fe471ce81f409.nq.gz
│   └── repolex
│       └── a90813d767615291a4085558b46fe471ce81f409
│           └── chunk-001.nq.gz
├── blob
│   ├── 01e96a8ab620c1f58160064e1fd0949894d4d214.nq.gz
│   ├── 0416172259dad2fa1d5d0040e7db2f01b3aff341.nq.gz
│   ├── 14c43b1fa488e90f9a57d1f4a8d54e1c26f5fc40.nq.gz
│   ├── 1d07143aecc185afc669c20db32291043024307a.nq.gz
│   ├── 20e182a5f98b6e7b1222e7998d09b2e1a2d5a527.nq.gz
│   ├── 28f44bcf6c18544e49c8ac0362b149b64d47aa9e.nq.gz
│   ├── 3c1b30ae685d9f60c6b2c1df0b6c04b34eb40858.nq.gz
│   ├── 3f9a5c9da4c946470ac7bd151025a27e9e3412d5.nq.gz
│   ├── 4e44a888c50ad0c2423d27234f21a2ed79e3eb39.nq.gz
│   ├── 573344cb41bd40086a89d49f5cca8a5271bfaf18.nq.gz
│   ├── 582386ee28ecec4a07f8eb84509c0829932733b8.nq.gz
│   ├── 63c4df3ce807b7e2df2236fa40d756738b1cb23f.nq.gz
│   ├── 661b234edf978cbcd75ff858e3462177c3e3b10b.nq.gz
│   ├── 66c8630d4e5fb30ae623c28af1d5f9d5fa3761ab.nq.gz
│   ├── 6acfdc3bab8d17444c65aa91ffdf75a7eb582820.nq.gz
│   ├── 6ec01ac3e83ef577f3b218b14f87ecd94f50973d.nq.gz
│   ├── 70a305f199fc709fdbcb56f24eb1a576f6adcb86.nq.gz
│   ├── 73b1748673ff2544c092f550e7878f9c73b76fd0.nq.gz
│   ├── 85897a757c6b4a86c334f2b0f048bcc72c3198f3.nq.gz
│   ├── 8b137891791fe96927ad78e64b0aad7bded08bdc.nq.gz
│   ├── a1ed58410404ad0a62e69e42fb64f88f28c324e9.nq.gz
│   ├── a62169600b1e9cc09537838b2501c79712b610fb.nq.gz
│   ├── b00503e2c0c385b2d62d59985a1cb67301bfc460.nq.gz
│   ├── be79c12c2f44e853f9810bb706064234186daaa0.nq.gz
│   ├── c2e57fad4cbe4d6b0573ac7541925a6619d303b0.nq.gz
│   ├── c6db9eede575a25383416df168f6c0941e48c7fc.nq.gz
│   ├── cf8491931025402da39180287b6701f109ca9662.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f05438f8ffabc67ced1e344776245c15f6d6cf91.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── a90813d767615291a4085558b46fe471ce81f409.nq.gz
├── filetree
│   └── a90813d767615291a4085558b46fe471ce81f409.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 37 files
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

## Source repository

[rbarrois/uconf](https://github.com/rbarrois/uconf)

---
*Parsed on 2026-04-09 by [repolex](https://repolex.ai)*
