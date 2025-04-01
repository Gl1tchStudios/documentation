# Examples

### Examples

#### Basic Notification

```lua
exports['glitch-notifications']:ShowNotification("Maze Bank", "Transaction completed", 5000, "#ff4500")
```

#### Persistent Notification with Multiple Boxes

```lua
local notifId = exports['glitch-notifications']:ShowNotification("Diamond Casino", "Welcome to the Casino!", 0, "#4a90e2")

-- Add more boxes
exports['glitch-notifications']:AddBoxToNotification(notifId, "Diamond Casino", "Enjoy your stay!", "#22bb33")
exports['glitch-notifications']:AddBoxToNotification(notifId, "Diamond Casino", "Check out the VIP lounge!", "#ff5500")
```

#### Remove a Specific Box

```lua
exports['glitch-notifications']:RemoveBoxFromNotification(notifId, boxId)
```

#### Update a Box

```lua
exports['glitch-notifications']:UpdateBoxContent(notifId, boxId, "Updated message!", nil, "#00ff00")
```

#### Toggle a Notification

```lua
exports['glitch-notifications']:ToggleNotification(12345, "Maze Bank", "Your balance is low!", "#ff0000")
```

###
