# List view

A scrollable list of rows — for logs, selectable items, or any list that's longer than a few entries. Rows can be single-select, multi-select, or read-only.

```lua
local maps = sec:List({
    Name = "Maps",
    Height = 160,
    Multi = false,                       -- true for checkboxes
    Items = { "Planet Namak", "Shiganshina", "Snowy Town", "Hidden Sand" },
    Default = "Planet Namak",
    Callback = function(selected) print("picked", selected) end,
})
```

## Items with icons and values

Each item can be a string, or a table with `Text`, an optional `Icon`, and a `Value` returned instead of the label:

```lua
sec:List({
    Items = {
        { Text = "Easy",      Icon = "circle",   Value = 1 },
        { Text = "Hard",      Icon = "flame",    Value = 2 },
        { Text = "Nightmare", Icon = "skull",    Value = 3 },
    },
    Callback = function(v) print("difficulty", v) end,   -- 1 / 2 / 3
})
```

## Multi-select

```lua
local picked = sec:List({
    Name = "Slots", Multi = true,
    Items = { "Slot 1", "Slot 2", "Slot 3", "Slot 4" },
    Default = { "Slot 1" },
    Callback = function(list) print(#list, "slots") end,  -- list is a table
})
```

## As a live log

Set `Selectable = false` and append rows as things happen:

```lua
local log = sec:List({ Height = 150, Selectable = false })
log:Add("Script loaded")
log:Add({ Text = "Joined Planet Namak", Icon = "map-pin" })
```

## Methods

| Method | Does |
| --- | --- |
| `:SetItems(list)` | Replace all items. |
| `:Add(item)` | Append one item. |
| `:Clear()` | Remove all items. |
| `:Get()` | Selected value (or table of values when `Multi`). |
| `:GetItems()` | All item values. |
| `:Select(value)` | Select an item by value. |
| `:ClearSelection()` | Deselect everything. |
| `:Set(value)` | Clear, then select one value. |
| `:OnChanged(fn)` | Listen for selection changes. |

Give it a `Flag` to read the selection through [Flags & Options](../advanced/flags.md).
