# Quick start

This is a complete, working hub. Paste it into your executor, run it, and you have a window with tabs, controls, notifications and config saving — all from one file.

```lua
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/f1475236-oss/UI-by-valen_vct/refs/heads/main/UI%20by%20valen_vct"))()

local Window = Library:CreateWindow({
    Title = "My Hub",
    Game = "Any Game",
    Icon = "flame",
    ToggleKey = Enum.KeyCode.RightControl,
})

-- a tab, a card, some controls
local Main = Window:Tab("Main", "layout-dashboard")
local farm = Main:Section("Farming", "Left", "wheat")

farm:Toggle({
    Flag = "AutoFarm",                 -- give it a Flag so you can read it anywhere
    Name = "Auto Farm",
    Callback = function(on)
        print("Auto Farm:", on)
    end,
})

farm:Slider({
    Flag = "Speed",
    Name = "Walk speed",
    Min = 16, Max = 200, Default = 16,
    Callback = function(v)
        local char = game.Players.LocalPlayer.Character
        local h = char and char:FindFirstChildOfClass("Humanoid")
        if h then h.WalkSpeed = v end
    end,
})

farm:Button({ Name = "Say hi", Style = "Primary", Callback = function()
    Window:Notify({ Title = "Hi!", Content = "Your hub is working.", Icon = "zap" })
end })

Window:Notify({ Title = "My Hub", Content = "Loaded. Press RightCtrl to toggle.", Icon = "check" })
```

## Reading values later

Because the two controls above have a `Flag`, you can read or set them from anywhere — no need to keep a reference:

```lua
if Library.Flags.AutoFarm then
    print("current speed is", Library.Flags.Speed)
end

Library.Flags.Speed = 120   -- this also moves the slider and fires its callback
```

More on this in [Flags & Options](../advanced/flags.md).

## Where to go next

* [Create a window](window.md) — every window option
* [Tabs & sections](tabs.md) — layout
* [Flags & Options](../advanced/flags.md) — the registry (most useful for big hubs)
* [Events](../advanced/events.md) — `:OnChanged` listeners
