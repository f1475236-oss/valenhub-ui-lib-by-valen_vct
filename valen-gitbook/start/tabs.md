# Tabs & sections

Add tabs to the window, then sections (cards) inside each tab. Controls go into sections.

```lua
local Main = Window:Tab("Main", "layout-dashboard")   -- name, icon
Window:Group("Utility")                               -- heading in the tab menu
local Misc = Window:Tab("Misc", "package")

-- Section(title, side, icon)  — side is "Left" or "Right"
local tools = Misc:Section("Tools", "Left", "wrench")
tools:Button({ Name = "Do thing", Callback = function() end })
```

Sections lay out in two columns. Pass `"Left"` or `"Right"` to choose the column; icons are optional.

{% hint style="info" %}
**Cards are live.** Users can drag a card out of the window, pin it, or reorder it — it returns to its original slot when dropped back. You don't need to do anything for this.
{% endhint %}

## Every control

| Control | Purpose |
| --- | --- |
| [Button](../components/buttons.md) | Run an action |
| [Toggle / Switch](../components/toggle.md) | On / off, with optional keybind |
| [Dropdown / PlayerDropdown](../components/dropdown.md) | Single or multi select |
| [Slider / Number](../components/sliders.md) | Pick a value in a range |
| [Input / Keybind](../components/input.md) | Text box, key picker |
| [Segmented](../components/segmented.md) | Pick exactly one |
| [List view](../components/list.md) | Scrollable, selectable list |
| [Label / Paragraph / Divider / Image / Code](../components/display.md) | Static display |
| [Stat / Progress / Sparkline / Console](../components/data.md) | Live readouts |
| [Tabbox / Group](../components/tabbox.md) | Group controls |
| [Palette / ColorPicker](../components/color.md) | Theme colors |
| [Social / DiscordCard](../components/social.md) | Links & live server |
