---
description: A fast, clean interface library for Roblox script hubs.
---

# Introduction

**Valen UI** gives you a complete hub out of one file: a draggable window with a tab menu, cards you can pin or pull out, and a full set of controls (toggles, sliders, dropdowns, graphs, lists and more). Every control saves itself to config automatically, and any control can be read from anywhere by name.

```lua
local Library = loadstring(game:HttpGet("https://ui.f1475236.workers.dev/"))()
local Window = Library:CreateWindow({ Title = "My Hub" })
```

## Why Valen UI

* **No dependencies.** One loadstring, nothing else.
* **Flags registry.** Give a control a `Flag` and read it anywhere: `Library.Flags.Speed` — no juggling references in a big hub. → [Flags & Options](advanced/flags.md)
* **Events.** Bind many listeners to one control with `:OnChanged`. → [Events](advanced/events.md)
* **Mobile-ready.** Every control, and card dragging, works with touch. → [Mobile](advanced/mobile.md)
* **Accessible.** Text size independent of UI scale, plus a high-contrast mode. → [Accessibility](advanced/accessibility.md)
* **Yours to brand.** Override the font, theme colors and accent per window. → [Theming](window/theming.md)
* **Executor-safe.** Pure ASCII, config saving where files are available, graceful where they aren't.

## Start here

{% hint style="info" %}
New? Jump to the [Quick start](start/quickstart.md) — a complete working hub you can paste and run right now.
{% endhint %}

* [Quick start](start/quickstart.md) — a full example in one block
* [Create a window](start/window.md) — every option
* [Tabs & sections](start/tabs.md) — layout
* [Components](components/buttons.md) — the full control set
