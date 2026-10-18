# Placeholders

With [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) installed, MineclusiveHousing adds `%housing_...%` placeholders you can use in other plugins: scoreboards, tab lists, chat formats, holograms, menus.

No `/papi ecloud` download is needed; the expansion is built into the plugin and registers itself on start.

## The player's own house

These describe the house the player owns and has open right now.

| Placeholder | Shows | Example | When no house is open |
| --- | --- | --- | --- |
| `%housing_in_housing%` | Whether the player has a house open | `true` | `false` |
| `%housing_house_name%` | Name of their open house | `Default House` | empty |
| `%housing_guests%` | Players visiting their house (not counting the owner) | `3` | `0` |
| `%housing_cookies%` | Cookies their house got this week | `12` | `0` |
| `%housing_slot%` | Island slot of their house | `s4` | empty |
| `%housing_slot_raw%` | Island slot number, starting at 0 | `3` | empty |

## The house the player is standing in

These describe whichever house the player is in, their own or someone else's. Useful for "You are visiting ..." lines.

| Placeholder | Shows | Example | When not in a house |
| --- | --- | --- | --- |
| `%housing_current_house%` | Name of the house they're in | `Steve's Castle` | empty |
| `%housing_current_owner%` | Owner of the house they're in | `Steve` | empty |
| `%housing_current_guests%` | Visitors in that house (not counting its owner) | `5` | `0` |

## Other

| Placeholder | Shows | Example |
| --- | --- | --- |
| `%housing_date%` | Today's date (MM/dd/yy) | `10/18/26` |

## Example

A TAB plugin header that changes inside houses:

```
&eHousing &7| %housing_current_house% &7by &f%housing_current_owner%
```

{% hint style="info" %}
Placeholders only read data that is already in memory, and guest counts are shared and refreshed once a second, so using them on scoreboards and tab lists for 1000+ players does not load the database.
{% endhint %}

The built-in housing scoreboard doesn't need PlaceholderAPI; it has its own `<placeholders>`, see [Customization](customization.md#scoreboards).
