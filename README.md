# Repolex Knowledge Graph of kivy/kivy-remote-shell

RDF knowledge graph data for [kivy/kivy-remote-shell](https://github.com/kivy/kivy-remote-shell), parsed by [repolex](https://repolex.ai).

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
rlex download kivy/kivy-remote-shell
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e5d27ed151160faabfdb9a14ce758e886e5490da
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e5d27ed151160faabfdb9a14ce758e886e5490da
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ff33d150279bcf946e6b6f5cee712377b9f55e7.nq.gz
│   ├── 1ba01f15ad71f6c38d1000debf4fe2a72754a583.nq.gz
│   ├── 3094688dafeee35c803ef401d98f040cfba13dd0.nq.gz
│   ├── 3b979aec2b27d59f30e9105da9a0ab625f1de5d9.nq.gz
│   ├── 3c76fc0aefaf184f6d3295ce3662c4acbe463c99.nq.gz
│   ├── 46b7da64bd3763b6048f6c301b1b331b794aee7b.nq.gz
│   ├── 64a204a093d342e13c864811f71d5dbe1e3bf273.nq.gz
│   ├── 664e5fab824034988c3c1c41e8ad8b35bb02e56b.nq.gz
│   ├── 6736043d24fa8a913e96a438c04aec00019d5c78.nq.gz
│   ├── 6a4b832c4f36f50e23f9b28abdaf4d92f0f90225.nq.gz
│   ├── 7021e6784fc0a2a7ba5642f0b3e3c879db5f6961.nq.gz
│   ├── 77f42ccdd92e45ab39abe13ebb20f313baded1ac.nq.gz
│   ├── 78656072773a1b5dd00d5cbfb401a30427a80b64.nq.gz
│   ├── a1baae66d91e49b3145fc135528dec6244db7184.nq.gz
│   ├── af72371cdecacd60078f4463bc2a13c05e2b19d1.nq.gz
│   ├── b0a682b629cdf4f4a420b390eb588a40013364a7.nq.gz
│   ├── c63678d751eb5ed792105a71c5f112f774ca1f4d.nq.gz
│   ├── c6aeb2d6ace031f40b1f7d853cb8da9abd4479cf.nq.gz
│   ├── d5d6b13c8523290257544a9fc3b75abf911b367d.nq.gz
│   ├── d9f4d83d68219cf3560bc50099f90392b0c1872a.nq.gz
│   ├── e301b6640bd48f0367445ddd27a9ef23e3756fff.nq.gz
│   └── f9a9eada33c935e359c71d7d1a929922f2b766f1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e5d27ed151160faabfdb9a14ce758e886e5490da.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 30 files
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

[kivy/kivy-remote-shell](https://github.com/kivy/kivy-remote-shell)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
