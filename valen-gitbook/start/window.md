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
    Id = "ValenAA",                  -- unique id for your hub (files + window name)
})
```

| Field | Type | Description |
| --- | --- | --- |
| `Title` | string | Window title (your hub name). |
| `Game` | string | Subtitle under the title. |
| `Logo` | number | Roblox image asset id shown in the header. |
| `Icon` | string | Lucide icon name used when no Logo is set. |
| `Tier` | string | Badge text (e.g. `"Premium"`). Omit to show the username. |
| `ToggleKey` | KeyCode / string | Key that shows/hides the window, e.g. `Enum.KeyCode.RightControl` or `"K"`. |
| `DragSmooth` | number | Window drag easing, 5–12. Lower trails the mouse more. |
| `Translations` | table | Your own strings per language — see [SetLanguage](../window/methods.md). |
| `Id` | string | Unique hub id. Names the window and the folder `ValenUI/<Id>/` that holds configs, layout and pins. Defaults to `Title`. Keep it the same between updates. |
| `ConfigVersion` | number | Version of your saved settings. Bump it when you rename or remove controls — see [Configs](../window/configs.md). |
| `MigrateConfig` | function | `function(data, from, to) return data end` — converts old configs. |
| `LiteAnimations` | boolean | `true` = light open/close animation (faster for big hubs). `false` = always full. Omit for auto (light above 80 controls). |

{% hint style="info" %}
**Running more than one hub is safe.** Each window has its own GUI, files and connections, so two hubs using Valen UI never close or overwrite each other. Re-running the same hub (same `Id`) cleanly replaces the old window.
{% endhint %}
