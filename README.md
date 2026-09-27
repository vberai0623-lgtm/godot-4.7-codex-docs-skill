# Godot 4.7 documentation for Codex Skill

Markdown export of the official Godot Engine 4.7 documentation, for people and for coding agents that need the real 4.7 signatures instead of memory from older versions.

`gdd` means **GoDot Docs**. Each page is one file:

```text
gdd_0001_Godot_Docs_master_branch.md
gdd_0548_CharacterBody2D.md
gdd_1591_@GlobalScope.md
```

There are 1592 pages, converted from `GodotEngine.epub`. GitHub's file list stops at 1,000 entries, so those pages are packed in `godot-4.7-docs.zip`. The files kept beside the archive are this introduction, `CATALOG.md`, `AGENTS.md`, and `.agents/skills/godot-47-docs/SKILL.md`.

Unzip the pages into this directory before a search. Existing files are left as they are.

```bash
unzip -n godot-4.7-docs.zip
```

## Look something up

**A class, builtin, method, property, or signal.** Find the file whose name ends with that symbol. Do not guess the number.

```bash
rg --files -g 'gdd_*_CharacterBody2D.md'
```

Methods are not separate files. Open the class page, then read the block that repeats the signature and ends at the next `---`. The `## Methods` table is only a list.

```bash
rg -n -A 20 '^bool move_and_slide\(\)' gdd_0548_CharacterBody2D.md
```

Do not end that pattern with `$`. The files use carriage returns, so a line-end anchor misses the prose.

**A workflow or concept**, such as TileMaps or input. Search the catalog, then open the one file it names. Manual pages are `gdd_0001` through `gdd_0510`.

```bash
rg -n '^gdd_[0-9]+_TileMap\.md:' CATALOG.md
```

Match the slug. `TileMap`, `TileMapLayer`, and `Using_TileMaps` are different pages. Several manual pages are titled Introduction.

These files are not the API: `gdd_0511_All_classes.md` (class list only), `gdd_1588_Genindex.md`, `gdd_1589_404.md`, `gdd_1592_Index.md`.

## For an agent

`AGENTS.md` is the short rule for which page wins. `.agents/skills/godot-47-docs/SKILL.md` is the search procedure. Read one page, or one member block. Do not load the whole repository or all of `CATALOG.md`.

## License

The Godot documentation is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), © Juan Linietsky, Ariel Manzur, and the Godot community. This repository redistributes a Markdown conversion of that text and does not change that license.

Conversion from `GodotEngine.epub` by 孤辰辰, 2026-06-27. The export was published with the Bilibili video [BV1UhTu6tEoF](https://www.bilibili.com/video/BV1UhTu6tEoF/).
