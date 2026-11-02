# Toggle & Switch

A **Toggle** is a labelled on/off row that can carry its own keybind. A **Switch** is the compact version with no keybind.

```lua
sec:Toggle({
    Name = "Auto Join",
    Default = false,
    Keybind = Enum.KeyCode.G,   -- or Keybind = true to let the user pick
    Tooltip = "Click the key to change it.",
    Callback = function(on) end,
})

sec:Switch({ Name = "Low graphics", Default = true })
```

Mark dangerous controls with `Risky = true` to give them a red accent:

```lua
sec:Toggle({ Name = "Instant kill", Risky = true, Keybind = Enum.KeyCode.K })
```

**Methods:** `:Set(bool)`, `:Get()`, `:SetKeybind(key)`, `:GetKeybind()`, `:SetLocked(true, "Premium")`.
