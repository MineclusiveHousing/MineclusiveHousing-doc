# MineclusiveHousing

Hypixel-style housing for your server. Every player gets their own island, built from a template you design, with their building saved between visits. Players decorate, invite friends, rate each other's houses with cookies and browse what everyone else has built.

**Current version: 5.1.2**

## Compatibility

| Requirement | Version |
| --- | --- |
| Server | Spigot **1.21.11** (tested). Paper builds of 1.21.11 should work but are not the tested platform. |
| Java | **21** or newer |
| Database | **MySQL** (8.x recommended): houses, settings and building are stored here. The database and tables are created for you. |
| Cache | **Redis**: required; coordinates island slots and sessions |
| Optional | **PlaceholderAPI** (`%housing_*%` placeholders), **Vault** + an economy plugin (paid plot upgrades) |
| Add-on | **FurnitureStudio**: in-game furniture builder, needs MineclusiveHousing |

{% hint style="warning" %}
The plugin uses server internals (NMS) for fast island pasting, so it only runs on the Minecraft version it was built for: 1.21.11.
{% endhint %}

## Features

* **My Houses**: `/house` opens a house selector. One house for everyone, three with `housing.vip`.
* **Instant islands**: islands are pasted section by section in milliseconds, and a warm pool keeps islands pre-built so most players arrive in under a second.
* **Saved building**: every block a player changes is saved to MySQL and rebuilt on top of the template each time the house opens. Autosave protects against crashes.
* **Themes**: players swap their whole island for another theme, with its biome, sky and weather.
* **House settings**: time of day, max players (fixed or dynamic), house name, plot size upgrades, house tag, cookie jar and reset.
* **Build and Social mode**: owners switch between creative building and playing as a visitor.
* **Visiting rules**: public, party, friend, guild or private, plus trust, ban and kick.
* **Travel menu**: browse open houses by most guests, weekly cookies, VIP, recommended or social, and filter by house tag.
* **House tags**: Parkour, PvP, Hangout and more, so players find what they feel like doing.
* **Cookies**: a weekly rating visitors give to houses they like.
* **Jukebox**: houses play Note Block Studio songs to everyone on the plot (VIP).
* **Pro tools**: `//set`, `//walls`, `//copy`, `//cut`, `//paste`, `//undo` inside your own plot.
* **Lobby NPCs**: skinned NPCs that open Browse Houses, My Houses or a random house.
* **Exploit protection**: creative mode and free blocks never leave the housing world. Ender chests are closed, other plugins' commands are limited to a list you control, and teleports respect bans.
* **Reconnect grace**: rejoin within 15 minutes and you are put back exactly where you stood.
* **Fully configurable**: every menu, message and scoreboard line can be changed.
* **Built for big servers**: no database work on the main thread, bounded thread pools, and features designed for 1000+ players online.
