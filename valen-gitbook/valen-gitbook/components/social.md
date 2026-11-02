# Discord & Social

**DiscordCard** shows a live server widget (online avatars + member count). **Social** is a row of link buttons; clicking copies the link, Discord also opens the invite.

```lua
sec:DiscordCard({ ServerId = "1537859951043805355", Invite = "MttbEFvnx6" })

sec:Social({
    Discord = "MttbEFvnx6",
    YouTube = "https://youtube.com/@valenhub",
    GitHub  = "https://github.com/valenhub",
})
```

{% hint style="warning" %}
The live widget needs **Server → Widget → Enable** turned on in Discord, or it shows the invite only.
{% endhint %}
