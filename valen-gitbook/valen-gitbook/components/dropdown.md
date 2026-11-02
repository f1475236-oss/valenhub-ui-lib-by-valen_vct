# Dropdown

Single-select by default; set `Multi = true` for checkboxes.

```lua
sec:Dropdown({
    Name = "Use slots",
    Multi = true,
    Options = { "Slot 1", "Slot 2", "Slot 3" },
    Default = { "Slot 1" },
    Callback = function(value) end,   -- string, or table when Multi
})
```

**Methods:** `:Set(v)`, `:Get()`, `:SetOptions(list)`, `:Add(x)`, `:Remove(x)`, `:Refresh()`, and for multi `:SelectAll()` / `:Clear()`.

## PlayerDropdown

A dropdown that auto-fills with players in the server.

```lua
sec:PlayerDropdown({ Name = "Teleport to", ExcludeSelf = true })
```
