# Installation

Load the library and keep the returned table. That table is your entry point.

```lua
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/f1475236-oss/UI-by-valen_vct/refs/heads/main/UI%20by%20valen_vct"))()
```

{% hint style="info" %}
You can also read it back later with `getgenv().ValenUI` — the library registers itself there on load.
{% endhint %}
