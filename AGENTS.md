# Godot 4.7 docs

This folder is the Godot 4.7 English manual and class reference, one page per file. `gdd` means GoDot Docs. Signatures in these files override model memory, including Godot 3.x habits.

The pages ship in `godot-4.7-docs.zip`. If `gdd_*.md` is not in this directory, run `unzip -n godot-4.7-docs.zip` here before searching. Search steps live in `.agents/skills/godot-47-docs/SKILL.md`. Do not load this whole folder, the zip, or all of `CATALOG.md`.

## Which file wins

- A type, builtin, method, property, or signal: open the one file whose name is `gdd_*_<Symbol>.md`. Class pages are `gdd_0512` through `gdd_1587`. Builtins are `gdd_1550` through `gdd_1587`. Script globals are `gdd_1590_@GDScript.md` and `gdd_1591_@GlobalScope.md`.
- A workflow or concept with no single type name: search titles in `CATALOG.md`, then open that one manual file. Manual pages are `gdd_0001` through `gdd_0510`.
- If several files match, the filename that equals the symbol beats a tutorial that only mentions it. Manual titles repeat (`Introduction`); match the slug, not the heading.

Do not use `gdd_0511_All_classes.md`, `gdd_1588_Genindex.md`, `gdd_1589_404.md`, or `gdd_1592_Index.md` as the API. Numbers have gaps; trust the filename, not a guessed number.

For one member, read that member's block only. `## Methods` and `## Properties` tables are signature lists. The prose is the later block that starts with the signature and ends at `---`.
