# Action bar

While a house owner is in their own house, the action bar (the line of text above the hotbar) reminds them which mode they're in, and can rotate through your own tips or announcements.

## What it shows

1. The **mode reminder**: "You are currently in **Build Mode**!" or "...**Social Mode**!", depending on the owner's toggle in the Housing Menu.
2. Then, if rotation is on, each of your **extra messages** in turn.
3. Then back to the mode reminder, and so on.

Each message stays on screen for a while, then the bar is empty for a moment before the next one appears.

{% hint style="info" %}
The action bar is shown to the **house owner** while they are in the housing world, not to visitors.
{% endhint %}

## Text: messages.yml

```yaml
housing:
  action-bar:
    build: "&eYou are currently in &bBuild Mode&e!"
    social: "&eYou are currently in &bSocial Mode&e!"
    messages:
      - "&7Tip: &fright-click the &aNether Star &ffor the Housing Menu"
      - "&7Rate houses you like with &6cookies&7, &f<player>&7!"
```

| Key | Shown |
| --- | --- |
| `build` | While the owner is in Build Mode |
| `social` | While the owner is in Social Mode |
| `messages` | Extra lines, shown one after another after the mode reminder |

Use `&` colour codes. `<player>` is replaced with the owner's name. Leave `messages` empty (`messages: []`) for no extra lines.

{% hint style="warning" %}
A fresh install ships with two placeholder lines, `test 1` and `test 2`. Replace them with your own text or empty the list.
{% endhint %}

## Theme editor

Admins inside a template world (`/housing world tp <name>`) see their own action bar instead:

```yaml
housing:
  action-bar:
    editor-edit: "&eYou are editing &b<template> &e- changes are saved"
    editor-readonly: "&eYou are viewing &b<template> &e- read-only"
```

`<template>` is the template's name. It shows for as long as they're in the template world.

## Timing: config.yml

```yaml
action-bar:
  rotate: true
  display-seconds: 5
  hide-seconds: 3
```

| Key | Default | Meaning |
| --- | --- | --- |
| `rotate` | `true` | Show the extra `messages`. When `false`, only the mode reminder is shown. |
| `display-seconds` | `5` | How long each message stays on screen. The last few seconds are Minecraft's own fade-out, so values under about 3 fade almost at once. |
| `hide-seconds` | `3` | How long the bar stays empty before the next message. `0` runs messages back to back. |

Run `/housing reload` after changing either file.
