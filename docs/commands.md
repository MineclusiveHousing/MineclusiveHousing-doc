# Commands

## Players

| Command | Aliases | Does |
| --- | --- | --- |
| `/house` | `/h`, `/houses` | Open My Houses |
| `/house visit <player>` | | Visit someone's house (their visiting rule applies) |
| `/house trust <player>` | | Let a player build in your house |
| `/house ban <player>` | | Ban a player from your house |
| `/house kick <player>` | | Send a player in your house back to the lobby |
| `/house leave` | `/leave` | Return to the lobby |
| `/house settings` | | Open the Housing Menu |
| `/house name <name>` | | Rename your house |
| `/time <dawn\|day\|noon\|sunset\|night\|midnight\|ticks>` | | Time of day on your island |
| `/housetag <tag\|none>` | | Set or clear your house tag |
| `/visitingrule <public\|party\|friend\|guild\|private>` | `/visitrule` | Who may visit |
| `/toggleborder` | `/border` | Show or hide the plot edge |
| `/safemode` | | Toggle safe mode in a house |

## Pro tools (inside your own plot)

| Command | Does |
| --- | --- |
| `//set [block]` | Fill the selected region |
| `//walls [block]` | Wall the selected region |
| `//copy` · `//cut` · `//paste` | Clipboard |
| `//undo` | Undo the last fill or paste |

Lava, fire, portals, TNT, command blocks and other dangerous blocks can't be used.

## Admins (`housing.admin`)

| Command | Does |
| --- | --- |
| `/housing world tp <name> [edit\|readonly]` | Load a template world and go there |
| `/housing world list` · `save` · `unsave` | List templates, save edits, discard edits |
| `/housing create template <name>` | Register the world you stand in as a template |
| `/housing create theme <name>` | Register a template as a theme |
| `/housing theme list` · `scan` | List or rescan themes |
| `/housing remove template\|theme <name>` | Remove one |
| `/housing debug data\|light` | Debug information |
| `/housing reload` | Reload config, messages, menus, themes and NPCs |
| `/housing npc ...` | Lobby NPCs, see [NPCs](npcs.md) |

FurnitureStudio commands are on the [FurnitureStudio](furniturestudio.md) page. Permissions are on the [Permissions](permissions.md) page.
