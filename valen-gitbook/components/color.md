# Palette & Color

```lua
local palette = sec:Palette({
    Name = "Theme",
    Colors = {
        { "Valen", Color3.fromRGB(180, 78, 255) },
        { "Ocean", Color3.fromRGB(90, 140, 255) },
    },
    Default = "Valen",
    Callback = function(c) Window:SetAccent(c) end,
})

sec:ColorPicker({ Name = "Custom accent", Default = Library.Theme.Accent,
    Callback = function(c) Window:SetAccent(c) end })
```

**Palette methods:** `:Set(name)`, `:Clear()`.
**ColorPicker methods:** `:Set(color, silent)`, `:Get()`.
