# Segmented

A row of options where exactly one is active — good for modes and sizes.

```lua
sec:Segmented({
    Name = "Lobby",
    Options = { "Public", "Friends", "Solo" },
    Default = "Public",
    Callback = function(v) end,
})
```

**Methods:** `:Set(v)`, `:Get()`.
