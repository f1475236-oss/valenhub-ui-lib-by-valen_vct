---
description: Switch the whole UI font at runtime, or ship your own.
---

# Fonts

Valen UI ships with a set of named fonts and lets you change the whole interface's font on the fly — a ready-made "Font" picker for your Settings tab.

## Built-in fonts

`Library.Fonts` is a table of name → font:

| Name | Font |
| --- | --- |
| `Builder` | BuilderSans (default) |
| `Gotham` | GothamSSm |
| `Montserrat` | Montserrat |
| `Poppins` | Poppins |
| `Nunito` | Nunito |
| `Source` | Source Sans |
| `Ubuntu` | Ubuntu |
| `Arimo` | Arimo |

## Switch at runtime

`Window:SetFont(name)` reskins every label instantly. Monospace views (Code, Console) keep their mono font.

```lua
Window:SetFont("Gotham")
Window:SetFont("Poppins")
```

You can also pass any Roblox `FontFace` json directly:

```lua
Window:SetFont("rbxasset://fonts/families/Jura.json")
```

The chosen font is saved, so it comes back the next time the hub loads.

## A font picker for Settings

```lua
local names = {}
for name in pairs(Library.Fonts) do table.insert(names, name) end
table.sort(names)

settings:Dropdown({
    Name = "Font",
    Options = names,
    Default = "Builder",
    NoSave = true,
    Callback = function(v) Window:SetFont(v) end,
})
```

## Set it permanently (distributors)

If you're shipping a rebranded hub, set the font once in `CreateWindow` — see [Theming](../window/theming.md):

```lua
Library:CreateWindow({ Title = "My Hub", Font = Library.Fonts.Poppins })
```

`Window:GetFont()` returns the current font family.
