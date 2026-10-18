# Permissions

## MineclusiveHousing

| Permission | Default | Grants |
| --- | --- | --- |
| `housing.use` | everyone | `/house` |
| `housing.vip` | none | 3 house slots instead of 1, and the jukebox |
| `housing.plot.<size>` | none | Plot size upgrade: `48`, `64`, `96`, `128` (see [Economy](economy.md)) |
| `housing.travel.vip` | none | Listed in the Travel menu's VIP channel (change it with `travel.vip-permission`) |
| `housing.visit.bypass` | op | Enter any house whatever its visiting rule |
| `housing.commands.bypass` | op | Use any command inside the housing world |
| `housing.gamemode.bypass` | op | Keep creative or spectator in other houses and after leaving |
| `housing.admin` | op | `/housing` and admin access to every house |

{% hint style="info" %}
Test as a **non-op player**. Ops bypass the command list and the game mode protection, so they don't see what normal players see.
{% endhint %}

## FurnitureStudio

| Permission | Default | Grants |
| --- | --- | --- |
| `furniturestudio.place` | everyone | Place furniture inside your own house |
| `furniturestudio.edit` | op | Build and manage furniture models (`/fs`) |

## Example (LuckPerms)

```
/lp group vip permission set housing.vip true
/lp group vip permission set housing.travel.vip true
/lp group vip permission set housing.plot.48 true
/lp group vip permission set housing.plot.64 true
```
