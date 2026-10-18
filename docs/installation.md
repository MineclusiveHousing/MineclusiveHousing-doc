# Installation

## 1. Requirements

* A Spigot **1.21.11** server running **Java 21**
* A **MySQL** server and a user that can create databases (or a database your host made for you)
* A **Redis** server (local is fine)
* Optional: PlaceholderAPI, Vault with an economy plugin

## 2. Install the jars

1. Put `MineclusiveHousing-<version>.jar` in `plugins/`.
2. Optional: put `FurnitureStudio.jar` in `plugins/` too.
3. Start the server once so `plugins/HousingPlugin/` is created, then stop it.

{% hint style="warning" %}
When you update, **delete the old MineclusiveHousing jar** before starting the server. Two versions in `plugins/` will both try to load.
{% endhint %}

## 3. Connect MySQL and Redis

Open `plugins/HousingPlugin/config.yml` and fill in your MySQL and Redis details:

```yaml
redis:
  host: localhost
  port: 6379
  password: ""

database:
  host: localhost
  port: 3306
  name: mineclusivehousing
  user: mineclusivehousing
  password: your-password
```

You don't need to create anything in MySQL yourself: on the next start the plugin creates the database named in `database.name` (if it doesn't exist yet) and all its tables.

{% hint style="info" %}
On a hosting panel that gives you a ready-made database, put that database's name, user and password here. The plugin uses it as it is.
{% endhint %}

## 4. Templates and themes

Houses are pasted from **template worlds** in `plugins/HousingPlugin/templates/<name>`. Build or copy a world there, then as an admin:

```
/housing world tp <name> edit        load and edit it
/housing create template <name>      register it as a template
/housing create theme <name>         make it a theme players can pick
/housing world save                  save and return to the lobby
```

Set `themes.default-theme` in `config.yml` to the theme new houses start with.

## 5. Start and test

Start the server, join, and run `/house`. You should get the My Houses menu and, after clicking a house, arrive on your island.

{% hint style="info" %}
Restart the server after replacing a jar. `/reload` and `/housing reload` do not load new plugin code, and SkinsRestorer and similar plugins do not support `/reload` at all.
{% endhint %}
