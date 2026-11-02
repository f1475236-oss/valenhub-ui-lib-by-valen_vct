# Input & Keybind

```lua
sec:Input({
    Name = "Webhook URL",
    Placeholder = "https://discord.com/api/...",
    Callback = function(text) end,
})

sec:Keybind({
    Name = "Panic key",
    Default = Enum.KeyCode.P,
    Callback = function() Window:SetVisible(false) end,
})
```

**Input methods:** `:Set(text)`, `:Get()`.
**Keybind methods:** `:Set(key)`, `:Get()`.
