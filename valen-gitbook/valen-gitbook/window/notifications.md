# Notifications

```lua
Window:Notify({
    Title = "Match finished",
    Content = "Wave 25 cleared in 6m 12s.",
    Type = "success",        -- "success" | "error" | nil
    Icon = "circle-check",
    Duration = 5,
    Actions = {              -- optional buttons
        { Name = "Later" },
        { Name = "Join", Callback = function() end },
    },
})

Window:Toast("Joining...")        -- small, quick

Window:Popup({                    -- blocking confirm
    Title = "Reset everything?",
    Content = "This can't be undone.",
    Options = {
        { Name = "Cancel" },
        { Name = "Reset", Style = "Danger", Callback = function() end },
    },
})
```
