# Config

`plugins/HousingPlugin/config.yml`. Run `/housing reload` after editing. Database and Redis changes need a restart.

## Connections

| Key | Default | Meaning |
| --- | --- | --- |
| `redis.host` · `port` · `password` | `localhost` · `6379` · `""` | Redis server |
| `database.host` · `port` · `name` · `user` · `password` | `localhost` · `3306` · ... | MySQL |
| `database.pool-size` | `10` | MySQL connections |
| `database.io-threads` | `4` | Background threads for lookups; keep below `pool-size` (minimum 2) |

## World and islands

| Key | Default | Meaning |
| --- | --- | --- |
| `world.name` | `HousingWorld` | The world houses live in |
| `island.max-slots` | `100` | Houses that can be open at once |
| `island.spawn-y` | `65` | Island height |
| `island.slot-width` | `1024` | Distance between islands (must stay 1024) |
| `island.warm-pool-min` · `warm-pool-max` | `1` · `20` | Pre-built islands kept ready |
| `island.roam-margin` | `24` | Blocks past the build zone before a player is sent back |
| `island.preload-radius` | `4` | Chunks loaded around spawn before arrival |
| `themes.default-theme` | `""` | Theme new houses start with |
| `house.default-name` | `Default House` | Name of a new house |

## Saving and sessions

| Key | Default | Meaning |
| --- | --- | --- |
| `autosave-seconds` | `120` | How often open houses save (minimum 15) |
| `session.reconnect-grace-minutes` | `15` | How long a house stays open after its owner disconnects |

## Plots

| Key | Default | Meaning |
| --- | --- | --- |
| `plot.default-size` | `32` | Starting build area |
| `plot.hollow-depth` | `9` | How deep a hollow reset digs |
| `plot.border-material` | `RED_WOOL` | Block that marks the plot edge |
| `plot.costs.<size>` | see [Economy](economy.md) | Upgrade prices |

## Players and protection

| Key | Default | Meaning |
| --- | --- | --- |
| `chat.separate-houses` | `true` | Chat stays inside each house |
| `inventory.separate-housing` | `true` | Separate inventories for the lobby and each house |
| `commands.housing-world.allowed` | list | Commands allowed inside houses (plus all housing commands) |
| `join-messages.enabled` | `true` | Replace join/leave messages with the `messages.yml` ones, lobby only |
| `join-messages.show-in-housing` | `false` | Also show them inside houses |

## Travel menu

| Key | Default | Meaning |
| --- | --- | --- |
| `travel.vip-permission` | `housing.travel.vip` | Permission that puts a house in the VIP channel |
| `travel.refresh-ticks` | `40` | How often open Travel menus update (20 = 1 second) |

## Pro tools

| Key | Default | Meaning |
| --- | --- | --- |
| `pro-tools.max-blocks` | `250000` | Most blocks one edit may change |
| `pro-tools.blocks-per-tick` | `8192` | Edit speed (higher is faster but laggier) |
| `pro-tools.selection-particles` | `true` | Draw the selected region |
| `pro-tools.particle-style` | `shell` | `shell` or `outline` |
| `pro-tools.particle-max` | `2000` | Most particles at once |
| `pro-tools.particle-ticks` | `10` | Redraw speed |
| `pro-tools.particle-colour` | `255, 40, 40` | Particle colour (red, green, blue) |

## Display

| Key | Meaning |
| --- | --- |
| `sky-times.day` · `sunset` · `night` | World time used for each sky option |
| `action-bar.rotate` · `display-seconds` · `hide-seconds` | Build/Social reminder and rotating tips |
| `scoreboard.housing` · `scoreboard.lobby` | Scoreboard titles and lines (see [Customization](customization.md)) |
| `theme-presets` | Biomes, skies and weathers offered when creating themes |
| `house-tags.presets` | House tag names and icons |
