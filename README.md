# Repolex Knowledge Graph of huggingface/picotron

RDF knowledge graph data for [huggingface/picotron](https://github.com/huggingface/picotron), parsed by [repolex](https://repolex.ai).

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
rlex download huggingface/picotron
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 59714b1bf25541dbeb6f5a721ed15f6d0768e786
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 59714b1bf25541dbeb6f5a721ed15f6d0768e786
│           └── chunk-001.nq.gz
├── blob
│   ├── 1368f30e19790cae71672792e9c3dff0c97da46d.nq.gz
│   ├── 17014e3f3a1b8c2521649a17ffe1596d38c0037b.nq.gz
│   ├── 1c39a1eeff7ec5d04a860b65ad316af099efc3d9.nq.gz
│   ├── 3e40db1767f7f2f174d6ee7b097a32a08a56dabf.nq.gz
│   ├── 4da678330864bb6e4af71829aea503878e574e01.nq.gz
│   ├── 5b3c0ff2341e525fcf735a5a2b4badaead03dfa4.nq.gz
│   ├── 65d26c0dfa3dd49468dda1b1a712e4499a258cbc.nq.gz
│   ├── 6b13aee04a5c45716e6c02e37cccab3a42454883.nq.gz
│   ├── 7451d709001078bae8a36232c08310be07f8f64c.nq.gz
│   ├── 79a4bdb8bf0d29137e477910da73c1fd1e478b6c.nq.gz
│   ├── 81fc585358b1b70f53116dfe0d245bf1ae9d127d.nq.gz
│   ├── 84da4cfb63372e68e2f93ef8b20c8d53d137e8e6.nq.gz
│   ├── 853dfeb4d0dcbcfac9c97e7b7ab852bae2165ed9.nq.gz
│   ├── 8cd920970146c847fd7011a08f813452e93bd9c2.nq.gz
│   ├── 95aae0e723a6a0e37f72fecb3590d1c4b6e917f1.nq.gz
│   ├── b42c2c031290245f7ab309ccd7a231ef7c5151e6.nq.gz
│   ├── b52fa10f3aa44ff882f2389bf26b94a294eebd64.nq.gz
│   ├── cbe0fc73a3e61d5cbfdf74fede1edee56f7165da.nq.gz
│   ├── cfe93a7388783906a2fd437b6c761a44c7577d74.nq.gz
│   ├── d5345d6b63e0a073ba964eea0ec9eada74791390.nq.gz
│   ├── dc7ae4806ca532da8b39e505a6fed968c56f32e9.nq.gz
│   ├── e28ebfa523a4c16363891f0c6e19d7a96878f4f1.nq.gz
│   ├── e92bb36d72af0de30b170e17ab42a1bfc58d0282.nq.gz
│   ├── e9ecf2369d7be8b435d21c70e10a106ca22a79f2.nq.gz
│   ├── eb72887c8cdaf8242123bbc09580dd9731c24bac.nq.gz
│   ├── f3f8203876e6432d29353283f9a8364706865d6d.nq.gz
│   ├── f3ff321220a8aea55af53a500c1038b950a10969.nq.gz
│   └── fcbd31b8442963c51b57f2892c255cf6add4e447.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 59714b1bf25541dbeb6f5a721ed15f6d0768e786.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 36 files
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

[huggingface/picotron](https://github.com/huggingface/picotron)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
