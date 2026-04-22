# Repolex Knowledge Graph of baoyachi/shadow-rs

RDF knowledge graph data for [baoyachi/shadow-rs](https://github.com/baoyachi/shadow-rs), parsed by [repolex](https://repolex.ai).

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
lexq download baoyachi/shadow-rs
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 544adb4738e9ae8c9917f211ca96edc57a0e04b9
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 544adb4738e9ae8c9917f211ca96edc57a0e04b9.nq.gz
│   └── repolex
│       └── 544adb4738e9ae8c9917f211ca96edc57a0e04b9
│           └── chunk-001.nq.gz
├── blob
│   ├── 13257e6dd69621af00db12f5aabedd05c69a22e9.nq.gz
│   ├── 14700c19eade8409ba85d1f18a9315ca388b580e.nq.gz
│   ├── 1717342d470fead8bf1ae697c3bca22c387cd365.nq.gz
│   ├── 18039b85b480077ddf1cda74d31292b7fd0bbaf2.nq.gz
│   ├── 194b5a15753a355ea8a129fd98da21b7f90d5792.nq.gz
│   ├── 1b74ba6ba5afe82becf592f3f4b06b8080fe3567.nq.gz
│   ├── 2517e7f0e4b410387ebb26cd3d7f336d6af4a057.nq.gz
│   ├── 26e071972ae0bce6500327810d17068972671874.nq.gz
│   ├── 2e049011e7eceb5d8b29a0f70f116e8b1a588c29.nq.gz
│   ├── 2e734fa41f92df92db083ac86d6614226275a3c6.nq.gz
│   ├── 2f53c9ef7559ff7462a7db44c9ee3483298d953a.nq.gz
│   ├── 3885f32a804c7fa56cc20c5179e10474e330125e.nq.gz
│   ├── 3ed56e9f4f34e455c3ae08d66a1df1ede0a9ce24.nq.gz
│   ├── 3f678c433ec003e6f49929097cd00b151f94c9b8.nq.gz
│   ├── 5802b2bd9028b6a418799eea3b543e846be13bb2.nq.gz
│   ├── 5a13ad7fc29d41428995d17dd5da897a5e56933d.nq.gz
│   ├── 6cc0984a0fab6b37a57ffae5e7424f2856f3bb64.nq.gz
│   ├── 6d7ffde99e05faae70b9f6b88453072681bca3e4.nq.gz
│   ├── 7714c0fe318905da7438ab072de7cda0d4d376e2.nq.gz
│   ├── 78788f5f8255b863a24a985cc556704ffb29f5ce.nq.gz
│   ├── 808686b771ac3d59a468bd005df718448f03b3a3.nq.gz
│   ├── 827ed40c0d22c1c0acbe03488120e8f7539a0972.nq.gz
│   ├── 8ea4b20b0d2c37b72ad1ea0fd119df3b7b21214c.nq.gz
│   ├── b10cd7c5a9114f3f632b4097d2392694f4956b19.nq.gz
│   ├── b43a4b15e7ed0e0dc59e7c9bc296b3d580a9ef03.nq.gz
│   ├── c2242925dbc4dfacb8460020cc62d4cfb97575fb.nq.gz
│   ├── caddbb2bfd91b0b62c974e52ef68b5a286f9465f.nq.gz
│   ├── d17a8c1cb7bd05fc82628bd39ec533e4e6aa0317.nq.gz
│   ├── d33f4da2103ba4a8c6e39920e07f5c3660d64fab.nq.gz
│   ├── e62784c27d130b9efe5d54ded54deff3304dc109.nq.gz
│   ├── e6f47037374c5c64cb104fab37ba28e00723770f.nq.gz
│   ├── f930b420ae18adb084d3baf326e35f2553f1040e.nq.gz
│   ├── f9d103e22833aca43c026d5e31e8faf21687bc31.nq.gz
│   ├── fe6c274ff6b6f2125e22383cde4449266848cce6.nq.gz
│   └── ff9f65571a27ced528d44979157a14084caa0514.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 544adb4738e9ae8c9917f211ca96edc57a0e04b9.nq.gz
├── filetree
│   └── 544adb4738e9ae8c9917f211ca96edc57a0e04b9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 45 files
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

[baoyachi/shadow-rs](https://github.com/baoyachi/shadow-rs)

---
*Parsed on 2026-04-22 by [repolex](https://repolex.ai)*
