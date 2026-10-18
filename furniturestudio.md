# FurnitureStudio

An add-on for MineclusiveHousing: build furniture in-game from blocks, then let players place it in their houses. Chairs they can sit on, tables, lamps, anything.

Install `FurnitureStudio.jar` next to MineclusiveHousing. It creates its own workshop world.

## For builders (`furniturestudio.edit`)

1. `/fs create <id>` opens a workshop bench in the FurnitureStudio world.
2. Build the piece from blocks on the bench.
3. Select the blocks with `/fs wand` (or `/fs pos1` and `/fs pos2`), then `/fs convert` turns them into a furniture model.
4. Adjust parts with `/fs move`, `/fs rotate`, `/fs scale`, `/fs highlight` and `/fs undo`. `/fs easy` toggles easy mode for click-based editing.
5. `/fs seat` sets where players sit and which way they face (`left`, `right`, `up`, `down`, `clear`).
6. `/fs test [id]` places test pieces to try it; `/fs test clear` removes them.
7. `/fs save` saves the piece. `/fs leave` exits the workshop.

| Command | Does |
| --- | --- |
| `/fs catalogue` | Browse all furniture |
| `/fs list` · `info <id>` · `delete <id>` | Manage pieces |
| `/fs edit <id>` | Reopen a piece in the workshop |
| `/fs deconvert` · `discard` | Back to blocks, or throw away the edit |
| `/fs reload` | Reload FurnitureStudio's config and messages |

Aliases: `/furniturestudio`, `/fs`, `/furniture`.

## For players (`furniturestudio.place`)

Players place furniture inside their own house. While placing, the hotbar becomes a set of tools (turn, tilt, roll, size, follow, confirm, cancel). Right-click a seat to sit; left-click to pick a piece back up.

## Limits

```yaml
max-per-house: 200     # furniture pieces per house
editor:
  max-parts: 200       # parts in one piece
testing:
  max-pieces: 20       # test pieces per builder
```

Everything else (tool items, workshop size, outline colours, sitting height) is in `plugins/FurnitureStudio/config.yml`, and all messages are in `messages.yml`.
