# Configs

Controls save themselves automatically (add `NoSave = true` to opt a control out). These methods manage named config files and share codes.

```lua
Window:SaveConfig("my farm")     -- returns name, or nil if no file access
Window:LoadConfig("my farm")
Window:DeleteConfig("my farm")
Window:ListConfigs()             -- table of names
Window:SetAutoLoad("my farm")    -- load this one on every start
Window:GetAutoLoad()

local code = Window:ExportConfig()  -- shareable "VALEN-..." string
local ok, err = Window:ImportConfig(code)
```
