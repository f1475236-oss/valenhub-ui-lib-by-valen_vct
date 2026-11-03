---
description: Bind many listeners to a control's changes, separately from its Callback.
---

# Events

Every value control has a `Callback`, but that's a single function. When you need **several** things to react to one control — or you want to attach a reaction later, from another part of your code — use `:OnChanged`.

## `:OnChanged(fn [, callNow])`

Registers a listener that runs **every time the value changes**, whether the change came from the user, a keybind, a slider drag, or a `:Set` / `Library.Flags` write. Returns a **disconnect** function.

```lua
local speed = farm:Slider({ Flag = "Speed", Name = "Walk speed", Min = 16, Max = 200, Default = 16 })

local disconnect = speed:OnChanged(function(v)
    print("speed is now", v)
end)

-- stop listening later
disconnect()
```

Pass `true` as the second argument to fire the listener once immediately with the current value:

```lua
speed:OnChanged(function(v) label:Set("Speed: " .. v) end, true)
```

## Many listeners on one control

```lua
local toggle = Window.Options.AutoFarm

toggle:OnChanged(function(on) print("logger:", on) end)
toggle:OnChanged(function(on) statusStat:Set(on and "ON" or "OFF") end)
toggle:OnChanged(function(on) if on then startFarm() else stopFarm() end end)
```

All three run on every change. `Callback` still runs too — `OnChanged` is additive, not a replacement.

## `.Value`

Every registered control also keeps its latest value on `.Value`, so you can read it without calling `:Get()`:

```lua
if Window.Options.AutoFarm.Value then ... end
```

{% hint style="info" %}
`OnChanged` is available on every control that has a value (`:Get`). Display-only controls (Label, Paragraph, Image) don't have it.
{% endhint %}
