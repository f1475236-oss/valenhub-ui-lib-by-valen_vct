# Labels & display

```lua
sec:Label("Pick a stage below.")
sec:Divider("Extras")                 -- optional label
sec:Paragraph({ Title = "Welcome", Content = "Runs from the tabs on the left." })
sec:Image({ Image = "rbxthumb://type=Asset&id=1&w=768&h=432", Height = 130, Caption = "Banner" })
sec:Code({ Title = "loader.lua", Code = 'loadstring(game:HttpGet("..."))()' })
```

**Paragraph methods:** `:SetTitle(s)`, `:SetContent(s)`.
**Code methods:** `:Set(s)`, `:Copy()`.
