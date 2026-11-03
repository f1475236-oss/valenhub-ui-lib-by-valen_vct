---
description: Read and write any control from anywhere, without passing references around.
---

# Flags & Options

When a hub gets big, passing each control object around the file becomes painful. The **Flags / Options registry** fixes that: give a control a `Flag`, and you can reach its value from anywhere.

## Giving a control a Flag

Add a `Flag` field to any value control (Toggle, Slider, Dropdown, Input, Keybind, ColorPicker, List, etc.):

```lua
farm:Toggle({ Flag = "AutoFarm", Name = "Auto Farm" })
farm:Slider({ Flag = "Speed", Name = "Walk speed", Min = 16, Max = 200, Default = 16 })
```

## Reading & writing — three ways

### `Library.Flags` — the value

Read or write the control's **value** directly. Writing also updates the control on screen and fires its callback.

```lua
print(Library.Flags.AutoFarm)   -- true / false
print(Library.Flags.Speed)      -- 16

Library.Flags.Speed = 120       -- moves the slider, runs its callback
Library.Flags.AutoFarm = true
```

### `Library.Options` — the control object

`Library.Options[flag]` is the control itself, so you get `.Value` plus every method.

```lua
print(Library.Options.Speed.Value)      -- 16
Library.Options.Speed:Set(80)           -- same as Library.Flags.Speed = 80
Library.Options.AutoFarm:OnChanged(function(on) print(on) end)
```

### `Window.Flags` / `Window.Options`

The same, scoped to one window — handy if you run more than one.

```lua
Window.Flags.Speed = 100
Window.Options.Speed:Set(100)
```

## In your farm loop

The classic use — read flags straight inside a loop, no references held:

```lua
task.spawn(function()
    while task.wait() do
        if Library.Flags.AutoFarm then
            -- do the farming, using Library.Flags.Speed etc.
        end
    end
end)
```

{% hint style="info" %}
No `Flag`? The control still saves to config, but it's keyed by `"Tab/Card/Name"` instead of a short name. Add a `Flag` whenever you want to read it by a clean key.
{% endhint %}

## Table of what each returns

| Access | Returns |
| --- | --- |
| `Library.Flags.X` | the value (read/write) |
| `Library.Options.X` | the control object |
| `Library.Options.X.Value` | the value (read-only snapshot) |
| `Window.Flags.X` / `Window.Options.X` | same, per-window |
