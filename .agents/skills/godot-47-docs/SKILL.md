---
name: godot-47-docs
description: >
  Look up Godot 4.7 in this local Markdown corpus before answering. Use for
  GDScript, Godot C#, nodes, signals, classes, methods, properties, builtins,
  TileMap, CharacterBody2D, move_and_slide, and @GlobalScope. Do not invent
  4.x signatures from memory.
---

# Godot 4.7 docs lookup

The corpus root is the directory that contains `CATALOG.md` and `godot-4.7-docs.zip`. `gdd` means GoDot Docs. Stay inside it. Open one file, or one member block.

If `gdd_*.md` is not already here, unzip the pages in this directory first. Do not read the zip itself.

```bash
unzip -n godot-4.7-docs.zip
```

## Class, builtin, method, property, signal

1. Find the page by symbol, not by guessing the number:

```bash
rg --files -g 'gdd_*_CharacterBody2D.md'
rg --files -g 'gdd_*_@GlobalScope.md'
```

2. For a member, jump to its prose. The `## Methods` table only lists signatures. The text block repeats the signature with no ` | ` and stops at the next `---`.

```bash
rg -n -A 20 '^bool move_and_slide\(\)' gdd_0548_CharacterBody2D.md
```

Do not anchor the pattern with `$`. Lines end with a carriage return, so `$` misses them. Stop at the next `---`. Do not read `Node.md` or `@GlobalScope.md` from the top.

## Workflow or concept

Search the catalog, then open the single named file. Manual pages are `gdd_0001`–`gdd_0510`.

```bash
rg -n '^gdd_[0-9]+_TileMap\.md:' CATALOG.md
```

That exact slug is the page. A wider pattern also hits `TileMapLayer` and `Using_TileMaps`; ignore those unless the question names them.

## Authority

- Filename equal to the symbol wins over a tutorial that mentions it.
- These are not the API: `gdd_0511_All_classes.md`, `gdd_1588_Genindex.md`, `gdd_1589_404.md`, `gdd_1592_Index.md`.
- Class pages: `gdd_0512`–`gdd_1587`. Builtins: `gdd_1550`–`gdd_1587`. Globals: `gdd_1590_@GDScript.md`, `gdd_1591_@GlobalScope.md`.
- Quote the signature from the file you opened.
