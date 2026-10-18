# Carpenter

Every house has a **Carpenter**: a friendly NPC labelled `[NPC] Carpenter` that helps the owner manage their house. It turns to look at players nearby.

## For players

**Right-click the Carpenter** in your own house to open the **Carpenter Menu**:

| Button | Does |
| --- | --- |
| Housing Menu | Open the Housing Menu |
| Themes | Change your island's theme |
| House Settings | Time, max players, name, plot size and more |
| Visiting Rules | Choose who may visit |
| Jukebox | Music for your house (VIP) |
| Building Tips | A book with tips for building and getting visitors |
| Move Carpenter Here | Move it to where you stand (stand on the ground, inside your house) |
| Remove Carpenter | Take it out of your house; click twice to confirm |

Other players who click your Carpenter are told it only works for you.

**Bringing it back:** after removing it, open **House Settings → Carpenter** while standing where it should go. The button shows whether your Carpenter is in your house or removed.

**Welcome:** the first time a new house opens, the Carpenter greets its owner in chat with a few tips. This happens once per house.

## Where it stands

1. Wherever the owner last moved it with **Move Carpenter Here**.
2. Otherwise, the theme's Carpenter spot, set by an admin during theme setup (see [Themes](themes.md)).
3. Otherwise, next to the island spawn.

The spot is remembered for each house, and the Carpenter only exists while the house is open.

## For server owners

`config.yml`:

```yaml
carpenter:
  enabled: true
  name: "&8[NPC] &aCarpenter"
  skin: ""
```

| Key | Default | Meaning |
| --- | --- | --- |
| `enabled` | `true` | Turn the Carpenter on or off for every house |
| `name` | `&8[NPC] &aCarpenter` | Label above its head |
| `skin` | `""` | A Minecraft player name whose skin it wears. Empty uses the default skin. |

`messages.yml`, under `carpenter`:

* `welcome`: the lines sent on a new house's first visit (`<player>` is the owner)
* `tips`: the pages of the Building Tips book, one entry per page (write `\n` for a new line)
* the messages shown when moving, removing or bringing it back

Set where the Carpenter starts for each theme in the theme setup, and check it with `/housing theme dummy` (see [Themes](themes.md)).

{% hint style="info" %}
Each open house has one Carpenter entity and one label, so the cost stays small with many houses open.
{% endhint %}
