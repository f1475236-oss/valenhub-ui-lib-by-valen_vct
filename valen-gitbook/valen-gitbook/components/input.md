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

## Multi-line input

Set `Multiline = true` (or `Lines = n`) for a tall text area — good for webhook messages, notes, or pasted lists. The label sits on top and the box fills the width.

```lua
local notes = sec:Input({
    Name = "Message",
    Multiline = true,
    Lines = 5,                       -- height in rows (2–12)
    Placeholder = "Type several lines...",
    Callback = function(text) print(text) end,
})

notes:Set("line one\nline two")
print(notes:Get())                   -- the full text, with newlines
```

`:Lines()` returns the text split into a table of lines.
