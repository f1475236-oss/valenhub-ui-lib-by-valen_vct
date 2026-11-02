# Installation

Load the library and keep the returned table. That table is your entry point.

```lua
local Library = loadstring(game:HttpGet("https://ui.f1475236.workers.dev/"))()
```

{% hint style="info" %}
You can also read it back later with `getgenv().ValenUI` — the library registers itself there on load.
{% endhint %}
