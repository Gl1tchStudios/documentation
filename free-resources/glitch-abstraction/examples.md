---
description: >-
  Below are practical examples of how to use Glitch Abstraction's most common
  functions. These examples demonstrate framework-agnostic code that works
  across ESX, QBCore, and QBox, as well as with suppo
---

# Examples

### Getting the Abstraction Library

```lua
local GlitchLib = exports['glitch-abstraction']:getAbstraction()
```

***

### Wait for Library to be Ready

```lua
CreateThread(function()
    while not GlitchLib.IsReady do Wait(100) end
    -- Now safe to use GlitchLib functions
end)
```

***

### Sending a Notification (Client)

```lua
GlitchLib.Notifications.Success("Hello!", "This is a cross-framework notification.")
```

***

### Showing an Input Dialog (Requires ox\_lib)

```lua
local result = GlitchLib.UI.Input("Enter Info", {
    GlitchLib.UI.Inputs.Text("Name", {required = true}),
    GlitchLib.UI.Inputs.Number("Age", {min = 18, max = 100})
})
if result then
    print("Name:", result[1], "Age:", result[2])
end
```

***

### Using a Context Menu (Requires ox\_lib)

```lua
GlitchLib.UI.RegisterContext({
    id = 'example_menu',
    title = 'Example Menu',
    options = {
        { title = 'Option 1', icon = 'star' },
        { title = 'Option 2', icon = 'user' }
    }
})
GlitchLib.UI.ShowContext('example_menu')
```

***

### Adding/Removing Items (Server)

```lua
-- Add an item to a player
GlitchLib.Inventory.AddItem(source, 'bread', 2)

-- Remove an item from a player
GlitchLib.Inventory.RemoveItem(source, 'water', 1)
```

***

### Checking Player Inventory (Client)

```lua
if GlitchLib.Inventory.HasItem('phone') then
    GlitchLib.Notifications.Info('Inventory', 'You have a phone!')
end
```

***

### Registering a Usable Item (Server)

```lua
GlitchLib.Inventory.UseItem('lockpick', function(source)
    -- Custom logic when player uses a lockpick
    TriggerClientEvent('myresource:lockpickUsed', source)
end)
```

***

### Target System Example (Client)

```lua
GlitchLib.Target.AddTargetEntity(PlayerPedId(), {
    {
        label = 'Greet',
        icon = 'handshake',
        action = function(entity)
            GlitchLib.Notifications.Success('Hello!', 'You greeted the player!')
        end
    }
})
```

***

### Progress Bar (Client, Requires ox\_lib)

```lua
GlitchLib.UI.ProgressBar({
    label = 'Processing...',
    duration = 3000
})
```

***

### Door Lock State (Server)

```lua
local isLocked = GlitchLib.DoorLock.GetDoorState(doorId)
if not isLocked then
    GlitchLib.DoorLock.SetDoorState(doorId, true)
end
```

***

### Awarding XP (Server, Requires pickle\_xp)

```lua
GlitchLib.Progression.AddXP(source, 100, 'Completed Task')
```

***

### Playing a Cutscene (Client)

```lua
GlitchLib.Cutscene.Play('michael_intro', { skip = false })
```

***

### Using Scaleform UI (Client)

```lua
GlitchLib.Scaleform.ShowMessageBox('Title', 'Subtitle', 'Footer')
```

***

### Framework-Agnostic Callback (Client)

```lua
GlitchLib.Framework.TriggerCallback('myresource:getData', function(data)
    print('Received from server:', data)
end)
```

***

### Registering a Server Callback (Server)

```lua
GlitchLib.Framework.RegisterCallback('myresource:getData', function(source, cb)
    cb({ foo = 'bar' })
end)
```
