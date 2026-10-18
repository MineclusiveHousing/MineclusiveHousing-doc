# Themes

A **theme** is what a house looks like: a template world you build, plus the plot players may build on, a spawn point, and the biome, sky and weather that go with it. Every house is pasted from a theme, and players can switch their house to another theme from the Housing Menu.

You need at least one theme before players can open houses.

## How it fits together

| Word | Meaning |
| --- | --- |
| **Template world** | A normal Minecraft world folder in `plugins/HousingPlugin/themes/<name>`. This is what gets copied for every house. |
| **Theme** | A template world plus its plot, spawn, biome, sky and weather. Players pick themes. |
| **Plot** | The square area inside the theme where the owner may build. Everything outside it is protected. |

## 1. Add the template world

1. Build the island in any world (single player is fine). Keep it compact: the island is pasted for every house.
2. Copy that world's folder into `plugins/HousingPlugin/themes/`, for example `plugins/HousingPlugin/themes/forest/`.
3. Check it shows up:

```
/housing world list
```

## 2. Open it and make changes

```
/housing world tp forest edit
```

You're teleported into the template. In `edit` mode your changes are saved back into the template. Use `readonly` instead of `edit` to look without changing anything.

While you're in a template world, the sidebar shows the **Theme Editor** scoreboard: the template's name, edit or read-only mode, whether it's set up as a theme yet, its Carpenter spot, and whether the dummies are showing. Change its lines under `scoreboard.template` in `config.yml`.

When you're done:

| Command | Does |
| --- | --- |
| `/housing world save` | Save your edits and go back to the lobby |
| `/housing world unsave` | Throw away edits since the last save and go back |

## 3. Create the theme

Stand in the template world and start the theme editor:

```
/housing create theme forest
```

You get a set of tools in your hotbar:

| Tool | Slot | Use |
| --- | --- | --- |
| **Plot Tool** (stick) | 1 | Right-click where the plot should be. Its edge is shown in red wool. |
| **Resize Tool** (blaze rod) | 2 | Right-click to make the plot bigger, left-click to make it smaller (2 to 255 blocks). |
| **Undo / Redo** (arrows) | 4, 5 | Step back or forward through size changes. |
| **Save** (lime dye) | 9 | Right-click when the plot is right. |

The players' spawn point is the spot where you placed the plot.

After **Save**, the chat asks you four questions:

1. **Biome**, for example jungle, snowy taiga, desert, plains (type the number)
2. **Sky**: day, night or sunset (type the number)
3. **Weather**: clear, rain, storm or thunder (type the number)
4. **Carpenter**: walk to where the [Carpenter](carpenter.md) should stand, face the way it should face, and type `here`. Type `skip` to put it next to the spawn instead.

Type `cancel` at any question to stop. When the last question is answered the theme is saved, and the red wool preview is removed.

To abort the whole editor at any time:

```
/housing create theme cancel
```

{% hint style="info" %}
The choices offered are set in `config.yml` under `theme-presets` (biomes, skies, weathers). Add any Minecraft biome name there to offer it.
{% endhint %}

## 4. Set the default theme

New houses start with the default theme. Set it in `config.yml` to the **template folder name**:

```yaml
themes:
  default-theme: forest
```

Then run `/housing reload`.

If no default is set yet, you can also run `/housing create template <name>` for a theme that already exists: the plugin offers to make it the default and asks you to run the command again to confirm.

## Quick template without the editor

```
/housing create template forest
```

Run it while standing in the template world. It registers the world straight away, finds a safe spawn automatically and gives it a 32×32 plot, with plains, day and clear weather. Use it to test quickly, then refine with the theme editor.

## Moving the spawn or Carpenter spot

Stand on the new spot in the template world (facing the right way for the Carpenter) and run:

| Command | Sets |
| --- | --- |
| `/housing theme set spawn` | Where players arrive in houses of this theme |
| `/housing theme set carpenter` | Where the Carpenter starts, and the way it faces |

Only works for a template that's already a theme. The dummies and the editor scoreboard update straight away. Houses whose owner already moved their Carpenter keep their own spot.

## Checking the spawn and Carpenter spots

While you are in a template world, show stand-ins where players arrive and where the Carpenter stands:

```
/housing theme dummy
```

| Dummy | Shows |
| --- | --- |
| **[DUMMY] Spawnpoint** | Where players arrive in houses of this theme |
| **[DUMMY] Carpenter point** | Where the Carpenter starts (only if the theme has a Carpenter spot) |

They show automatically when you teleport into a template that's already a theme. Run the command to hide them, and again to show them. The dummies glow so they are easy to find, can't be hit, are never saved into the template, and disappear when the template closes.

A template that isn't a theme yet (before its first setup) shows nothing.

If you change the spots while the dummies are showing, run `/housing theme dummy` twice to refresh them.

## Managing themes

| Command | Does |
| --- | --- |
| `/housing theme list` | List registered themes |
| `/housing theme scan` | Look for template folders again |
| `/housing remove theme <name>` | Remove a theme |
| `/housing remove template <name>` | Remove a template |

Themes are stored in `plugins/HousingPlugin/themes.yml`.

## Tips

* **Plot size** in the theme is where building starts. Players can buy bigger plots later (see [Economy](economy.md)), and their upgrade follows them to every theme.
* Weather is shown only to players on that island, and rain falls as snow in cold biomes such as snowy taiga.
* Players switching theme keep their house; the island is repasted in place with the new theme's biome, sky and weather.
* Close a template with `/housing world save` before you create or import it again, so the server and the editor don't both work on the same files.
