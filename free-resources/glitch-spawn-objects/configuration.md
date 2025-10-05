---
description: >-
  Glitch Spawn Objects is a lightweight and efficient FiveM resource designed to
  spawn, synchronise, and persist world objects seamlessly across all players on
  the server.
---

# Configuration

Edit `shared/config.lua` to customise your spawn oi experience:

***

#### Basic Settings

```lua
Config = {}

Config.Debug = false -- Set to true to enable debug mode, which will draw markers for spawned objects.
```

***

#### Permission Configuration

```lua
Config.permissionSystem = "ace" -- Options: "ace", "discord", "steam", "license", "everyone"
Config.acePermission = "command.spawnobject" -- ACE permission required (only used when permissionSystem = "ace")
Config.allowedDiscordAccess = {"Owner", "Admin Team"} -- List of roles that are allowed access to commands (only used when permissionSystem = "discord") (Note: You need to implement your own Discord role checking logic)
Config.allowedSteamIDs = {"steam:123456789", "steam:987654321"} -- List of allowed Steam IDs (only used when permissionSystem = "steam")
Config.allowedLicenses = {"license:abc123", "license:def456"} -- List of allowed licenses (only used when permissionSystem = "license")
```

***

#### Command Configuration

```lua
Config.commands = {
    spawnObject = "spawnobject", -- Command to spawn a new synced object
    syncedObjects = "syncedobjects" -- Command to view all synced objects
}
```

***

#### Misc Configuration

```lua
Config.ignoreSceneType = {"christmas"} -- List of scene types to exclude from being loaded by this script.
Config.itemsPerPage = 20 -- Amount of objects shown per page via /syncedobjects
Config.renderDistance = 150.0 -- The distance threshold (in units) at which objects will be rendered. Modify this value to adjust the render distance.
```

***

#### Discord Logging

Configure your discord system in `shared/apiKeys.lua`:\
\- Discord logging is available, set up API key within `shared/apiKeys.lua` if you wish to use it.

```lua
local apiKeys = {
    discordWebhook = "https://discord.com/api/webhooks/" 
}
```
