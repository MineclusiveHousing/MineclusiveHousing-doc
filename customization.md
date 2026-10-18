# Customization

Everything players see can be changed. After editing, run `/housing reload`.

| File | Holds |
| --- | --- |
| `menu.yml` | Every menu: title, size, slots, items, names, lore, sounds |
| `messages.yml` | Every chat message |
| `config.yml` | Scoreboards, action bar, house tags, behaviour (see [Config](config.md)) |
| `themes.yml` | Registered themes with their biome, sky and weather |
| `npcs.yml` | Lobby NPCs (see [NPCs](npcs.md)) |
| `songs/` | Jukebox songs |

## Menus

Each button keeps its slot, item and text together:

```yaml
housing-menu:
  title: "Housing Menu"
  buttons:
    themes:
      slot: 14
      item: PAINTING
      name: "&aThemes"
      lore:
        - "&7Apply visual themes"
        - "&7to your house."
```

Every value is optional. Remove a key and that button uses the built-in default, so a typo can't break a menu. Bad values are logged with the key and the default used. Sounds accept `block.note_block.pling` or `BLOCK_NOTE_BLOCK_PLING`, with optional `volume` and `pitch`, or `none` to silence them.

## Messages

`messages.yml` uses `&` colour codes and `<placeholders>` such as `<player>`. Missing keys are added back automatically on start, and the log lists them.

## Scoreboards

The housing and lobby scoreboards are in `config.yml` under `scoreboard`: animated title frames, frame speed and lines. Placeholders: `<date>`, `<slot>`, `<house_name>`, `<guests>`, `<cookies>`.

## House tags

```yaml
house-tags:
  presets:
    Parkour: FEATHER
    PvP: IRON_SWORD
    Hangout: CAMPFIRE
```

Name: icon item. Owners can also type their own tag.

## Jukebox songs

Put `.nbs` files (Note Block Studio) in `plugins/HousingPlugin/songs/` and run `/housing reload`. VIP owners pick songs for their house from the Housing Menu.

## Themes

Build template worlds and register them as themes (see [Installation](installation.md#5-templates-and-themes)). Players switch themes from the Housing Menu; the island is repasted in place with the theme's biome, sky and weather.

## PlaceholderAPI

With PlaceholderAPI installed, `%housing_*%` placeholders are available to other plugins.
