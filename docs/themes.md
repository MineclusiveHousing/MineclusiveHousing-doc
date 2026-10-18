# Themes

A **theme** is what a house looks like: a template world you build, plus the plot players may build on, a spawn point, and the biome, sky and weather that go with it. Every house is pasted from a theme, and players can switch their house to another theme from the Housing Menu.

You need at least one theme before players can open houses.

## How it fits together

| Word | Meaning |
| --- | --- |
| **Template world** | A normal Minecraft world folder in `plugins/HousingPlugin/templates/<name>`. This is what gets copied for every house. |
| **Theme** | A template world plus its plot, spawn, biome, sky and weather. Players pick themes. |
| **Plot** | The square area inside the theme where the owner may build. Everything outside it is protected. |

## 1. Add the template world

1. Build the island in any world (single player is fine). Keep it compact: the island is pasted for every house.
2. Copy that world's folder into `plugins/HousingPlugin/templates/`, for example `plugins/HousingPlugin/templates/forest/`.
3. Check it shows up:

```
/housing world list
```

## 2. Open it and make changes

```
/housing world tp forest edit
```

You're teleported into the template. In `edit` mode your changes are saved back into the template. Use `readonly` instead of `edit` to look without changing anything.

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

After **Save**, the chat asks you three questions. Type the number of your choice:

1. **Biome**, for example jungle, snowy taiga, desert, plains
2. **Sky**: day, night or sunset
3. **Weather**: clear, rain, storm or thunder

Type `cancel` to stop. The theme is saved, and the red wool preview is removed.

To abort the whole editor at any time:

```
/housing create theme cancel
```

{% hint style="info" %}
The choices offered are set in `config.yml` under `theme-presets` (biomes, skies, weathers). Add any Minecraft biome name there to offer it.
{% endhint %}

## 4. Set the default theme

New houses start with the default theme. Set it in `config.yml`:

```yaml
themes:
  default-theme: forest
```

Then run `/housing reload`.

## Quick template without the editor

```
/housing create template forest
```

Run it while standing in the template world. It registers the world straight away, finds a safe spawn automatically and gives it a 32×32 plot, with plains, day and clear weather. Use it to test quickly, then refine with the theme editor.

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
