# Repolex Knowledge Graph of UKPLab/emnlp2026-zoom-in

RDF knowledge graph data for [UKPLab/emnlp2026-zoom-in](https://github.com/UKPLab/emnlp2026-zoom-in), parsed by [repolex](https://repolex.ai).

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
rlex download UKPLab/emnlp2026-zoom-in
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0e68db59bcbdfb1a1e72b4a394971144159222e3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0e68db59bcbdfb1a1e72b4a394971144159222e3
│           └── chunk-001.nq.gz
├── blob
│   ├── 01dbc3167502d110014b5c1123a8dfe920693e8c.nq.gz
│   ├── 0f229786cdaf76fdf0928d6b4b1f49b740802d32.nq.gz
│   ├── 141c68ee7f0dee4b6fed2ff85a85185a5e2d8883.nq.gz
│   ├── 148903d3bb376a76dadfcaa5be65b18dba49ed8a.nq.gz
│   ├── 1c45d27afefc4791b52b41f40aa3ab512e11cca3.nq.gz
│   ├── 251f86c78a483e5ab4bf2d28e71b2066ff38a28a.nq.gz
│   ├── 27c45ce55bcce77a6c318477b20973e96aa60a6e.nq.gz
│   ├── 2e9e43001055842cf765bc5d7731595fdc795a81.nq.gz
│   ├── 34f13dc90e64019f97b0971adb0c1338ff94be31.nq.gz
│   ├── 44a81fd9750e06becb5a23e21a6c3577fd81e9c2.nq.gz
│   ├── 4b82ad6feedb010186b571f382d7ff3f6ef20a24.nq.gz
│   ├── 536a3668e5e7af2d8f30a506c75ed4396c70704b.nq.gz
│   ├── 53f9f93b30e5ce22d117442675923e4abc1d98a5.nq.gz
│   ├── 5e42d409f350b7c3f769b43cfb4bfe5769f20586.nq.gz
│   ├── 7b1eb505609cbfd39b4e981233deeb8711901dcb.nq.gz
│   ├── 8441e8b7b82ef705a9096467242359778961f30b.nq.gz
│   ├── 85ba6250d9f527da6dd74bc24bfac92b4444ece7.nq.gz
│   ├── 8c639da7406e397ac915180a87531c7c7ec40e72.nq.gz
│   ├── a62331aa8b1995eee7d2ebda02f55b9b70109d83.nq.gz
│   ├── c0dbe7bdc097e1f8c4e9269cbd12ca7e95db28f3.nq.gz
│   ├── c565ae116478d28724241e8db063491af74c927c.nq.gz
│   ├── c5cbaa111d0f52c936567b40b1c81b6e28bc4851.nq.gz
│   ├── c667b02c97a006f01c308961d3aae6a7100e9527.nq.gz
│   ├── c991c95291c3d43dc5a0195e2db30751be117729.nq.gz
│   ├── cbb5c268a618e8ff8e3058f3ec7f6ee1113b79d0.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e91619a5e3f4992b47db87a4621ce3b31bd7313d.nq.gz
│   ├── f49a4e16e68b128803cc2dcea614603632b04eac.nq.gz
│   ├── f77fcbe6d8b31dafb5217b2be6c0cebfac0d7445.nq.gz
│   └── f7e5675af70517e7201203634db8361a55681ae3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0e68db59bcbdfb1a1e72b4a394971144159222e3.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 37 files
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

[UKPLab/emnlp2026-zoom-in](https://github.com/UKPLab/emnlp2026-zoom-in)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
