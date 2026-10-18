# Installation

## 1. Requirements

* A Spigot **1.21.11** server running **Java 21**
* A **MySQL** database and user
* A **Redis** server (local is fine)
* Optional: PlaceholderAPI, Vault with an economy plugin

## 2. Create the database

```sql
CREATE DATABASE mineclusivehousing;
CREATE USER 'mineclusivehousing'@'%' IDENTIFIED BY 'change-me';
GRANT ALL PRIVILEGES ON mineclusivehousing.* TO 'mineclusivehousing'@'%';
FLUSH PRIVILEGES;
```

Tables are created automatically on first start.

## 3. Install the jars

1. Put `MineclusiveHousing-<version>.jar` in `plugins/`.
2. Optional: put `FurnitureStudio.jar` in `plugins/` too.
3. Start the server once so `plugins/HousingPlugin/` is created, then stop it.

{% hint style="warning" %}
When you update, **delete the old MineclusiveHousing jar** before starting the server. Two versions in `plugins/` will both try to load.
{% endhint %}

## 4. Connect MySQL and Redis

Open `plugins/HousingPlugin/config.yml`:

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
  password: change-me
```

## 5. Templates and themes

Houses are pasted from **template worlds** in `plugins/HousingPlugin/templates/<name>`. Build or copy a world there, then as an admin:

```
/housing world tp <name> edit        load and edit it
/housing create template <name>      register it as a template
/housing create theme <name>         make it a theme players can pick
/housing world save                  save and return to the lobby
```

Set `themes.default-theme` in `config.yml` to the theme new houses start with.

## 6. Start and test

Start the server, join, and run `/house`. You should get the My Houses menu and, after clicking a house, arrive on your island.

{% hint style="info" %}
Restart the server after replacing a jar. `/reload` and `/housing reload` do not load new plugin code, and SkinsRestorer and similar plugins do not support `/reload` at all.
{% endhint %}
