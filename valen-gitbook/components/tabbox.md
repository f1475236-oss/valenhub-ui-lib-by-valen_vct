# Tabbox & Group

**Tabbox** puts tabs inside a single card. Each tab is a mini-section you add controls to.

```lua
local box = sec:Tabbox({ "Lobby", "Stages", "Raids" })
box.Lobby:Button({ Name = "Summon area" })
box.Stages:Dropdown({ Name = "Stage", Options = { "Namak", "Sand" } })
box.Raids:Toggle({ Name = "Auto raid" })
```

**Group** is a sub-heading inside a section that returns a sub-container:

```lua
local g = sec:Group("Movement")
g:Number({ Name = "Walk speed", Min = 16, Max = 200 })
g:Switch({ Name = "Infinite jump" })
```
