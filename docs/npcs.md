# NPCs

Lobby NPCs, like the ones in the Hypixel housing lobby: a skinned NPC with lines above its head that does something when right-clicked.

## Quick start

Stand where the NPC should be, facing the way it should face:

```
/housing npc create browse
/housing npc lines browse &aBrowse Houses | &e&lRIGHT CLICK
/housing npc skin browse Notch
/housing npc action browse add menu travel
```

Repeat with `menu my-houses` and `menu random-house` for the other two classic NPCs.

## Selecting an NPC

Look at an NPC and run `/housing npc select`. Every other command can then leave out the id:

```
/housing npc select
/housing npc lines &aMy Houses | &e&lRIGHT CLICK
/housing npc look stable
```

Run `/housing npc select` while looking at nothing to see what is selected. The selection ends when you log out or change world.

## Commands

All need `housing.admin`.

| Command | Does |
| --- | --- |
| `create <id>` · `delete <id>` · `list` | Add, remove, list |
| `select` | Select the NPC you look at |
| `tp <id>` · `move <id>` | Go to it, or move it to where you stand |
| `skin <id> <player>` | Use a player's skin |
| `lines <id> <line> \| <line>` · `lines <id> clear` | Lines above its head, `&` colour codes allowed |
| `look <id> on\|off\|stable` | Turn to the nearest player, stop, or look straight ahead |
| `pose <id> standing\|sneaking\|sitting\|sleeping\|swimming` | Pose |
| `equip <id> head\|chest\|legs\|feet\|hand\|offhand\|clear` | Equip the item in your hand |
| `action <id> add <type> <value>` · `list` · `remove <n>` · `clear` | Click actions |

## Actions

| Action | Example |
| --- | --- |
| `menu travel` | Open Browse Houses |
| `menu my-houses` | Open My Houses |
| `menu random-house` | Send the player to a random open house they may visit |
| `message <text>` | `message &aWelcome, {player}!` |
| `command <command>` | Run as the player: `command spawn` |
| `console <command>` | Run by the console: `console give {player} cookie 1` |
| `sound <sound> [volume] [pitch]` | `sound entity.experience_orb.pickup 1 1.2` |
| `teleport` | Teleport to where you stood when adding it |

An NPC runs all of its actions in order. `{player}` becomes the clicker's name.

## Good to know

* NPCs are saved in `plugins/HousingPlugin/npcs.yml`. You can edit it by hand and run `/housing reload`.
* NPCs can't be placed in the housing world, hurt or pushed.
* Head turning is off by default.
* Each NPC is one real entity, so they cost the same with 10 or 1000 players online.
* Skins are looked up from Mojang by player name, so they work on offline-mode servers too.

Looking for the NPC inside houses? See [Carpenter](carpenter.md).
