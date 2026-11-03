# Configs

Controls save themselves automatically (add `NoSave = true` to opt a control out). Every hub keeps its own files in `ValenUI/<Id>/`, so two hubs that both use Valen UI never see each other's configs.

```lua
local Window = Library:CreateWindow({
    Title = "My Hub",
    Id = "MyHub",            -- folder + window name. Defaults to Title. Keep it stable.
    ConfigVersion = 2,       -- bump when you rename/remove controls
    MigrateConfig = function(data, fromVersion, toVersion)
        if fromVersion < 2 then
            data.AutoFarm = data["Main/Farming/Auto Farm"]  -- old key -> new Flag
        end
        return data
    end,
})

Window:SaveConfig("my farm")                     -- returns name, or nil if no file access
Window:LoadConfig("my farm")                     -- fires callbacks
Window:LoadConfig("my farm", { Silent = true })  -- restores values only, no callbacks
Window:DeleteConfig("my farm")
Window:ListConfigs()
Window:SetAutoLoad("my farm")
Window:GetAutoLoad()

local code = Window:ExportConfig()
local ok, err = Window:ImportConfig(code)                     -- fires callbacks
local ok, err = Window:ImportConfig(code, { Silent = true })
```

{% hint style="warning" %}
**Always give saved controls a `Flag`.** Without one the key is `"Tab/Card/Name"`. If you rename a tab or card, Valen UI still finds the control by its name when that name is unique in the hub, but a `Flag` never breaks.
{% endhint %}
