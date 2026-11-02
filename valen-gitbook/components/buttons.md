# Buttons

```lua
sec:Button({
    Name = "Save slots",
    Icon = "save",
    Style = "Primary",       -- "Primary" | "Danger" | nil
    Callback = function() end,
})
```

| Field | Description |
| --- | --- |
| `Name` | Button label. |
| `Icon` | Optional Lucide icon. |
| `Style` | `"Primary"` (accent) or `"Danger"` (red). Default is plain. |
| `Callback` | Runs on click. |
