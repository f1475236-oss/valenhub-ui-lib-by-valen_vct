# Stat, Progress & Graph

Readouts you update at runtime by holding the returned object.

```lua
local gems = sec:Stat({ Name = "Gems earned", Value = 0 })
local wave = sec:Progress({ Name = "Wave", Min = 0, Max = 25, Default = 0 })
gems:Set(120); wave:Set(12)

local fps = sec:Sparkline({ Name = "FPS", Points = 40, Suffix = " fps" })
fps:Push(60)                       -- feed one value

local log = sec:Console({ Height = 150 })
log:Append("Script loaded")
log:Append("Joined Planet Namak", "success")  -- "success" | "warn" | "error"
log:Clear()
```

| Control | Methods |
| --- | --- |
| Stat | `:Set(v)`, `:Get()` |
| Progress | `:Set(v)`, `:SetMax(n)`, `:SetRange(a,b)`, `:GetPercentage()` |
| Sparkline | `:Push(v)`, `:Set(list)`, `:Clear()`, `:GetAll()` |
| Console | `:Append(text, kind)`, `:Clear()`, `:SetHeight(px)` |
