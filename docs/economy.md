# Economy

MineclusiveHousing uses **Vault** for paid upgrades. Vault is optional: without it everything works, and paid upgrades say purchases are unavailable.

## Plot size upgrades

Every house starts with a `plot.default-size` buildable area (32×32). Owners buy bigger plots from **House Settings → Plot Size Upgrade**.

```yaml
plot:
  default-size: 32
  costs:
    48: 5000
    64: 15000
    96: 40000
    128: 100000
```

* A size is only offered to players with `housing.plot.<size>`.
* A cost of `0` means the permission alone unlocks it (good for rank perks).
* The money is taken through Vault from your economy plugin (EssentialsX, CMI and so on).
* Plot size belongs to the **house**, not the theme, so it stays when the owner changes theme.
* Sizes only go up: shrinking would cut off what was built outside the new edge.

## Cookies

Cookies are not money. They are a free weekly rating: a visitor gets one pack per week per house, and the counts drive the Travel menu's **Weekly cookies** channel.

## Keeping your economy safe

Houses give creative mode and free blocks. MineclusiveHousing stops these leaking into your real economy:

* Ender chests are closed in the housing world.
* Each house has its own inventory, separate from the lobby (`inventory.separate-housing`).
* Only commands in `commands.housing-world.allowed` work inside houses, so `/sell`, `/ah`, `/pv`, `/ec`, `/trade` and similar are blocked unless you add them.
* Creative mode is removed when a player leaves a house or the housing world.
