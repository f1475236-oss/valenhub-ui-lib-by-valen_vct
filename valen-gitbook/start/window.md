# Create a window

`Library:CreateWindow(config)` builds the window and returns it. Every field is optional except a title.

```lua
local Window = Library:CreateWindow({
    Title = "VALEN HUB",
    Game = "Anime Adventures",
    Logo = 106125024550388,          -- Roblox image asset id
    Icon = "flame",                  -- fallback when no Logo
    Tier = "Premium",                -- omit to show @username
    ToggleKey = Enum.KeyCode.RightControl,
})
```

| Field | Type | Description |
| --- | --- | --- |
| `Title` | string | Window title (your hub name). |
| `Game` | string | Subtitle under the title. |
| `Logo` | number | Roblox image asset id shown in the header. |
| `Icon` | string | Lucide icon name used when no Logo is set. |
| `Tier` | string | Badge text (e.g. `"Premium"`). Omit to show the username. |
| `ToggleKey` | KeyCode | Key that shows/hides the window. |
| `DragSmooth` | number | Window drag easing, 5–12. Lower trails the mouse more. |
| `Translations` | table | Your own strings per language — see [SetLanguage](../window/methods.md). |
