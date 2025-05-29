---
description: '!  DOCUMENTATION IS NOT UP TO DATE WITH LATEST LIB UPDATE !'
---

# Server

## Server-Side Functions

### Framework Functions

_Required Resources: One of: ESX Legacy, QBCore, or QBox_

#### Player Management

```javascript
GlitchLib.Framework.GetPlayer(source) // Get player object
GlitchLib.Framework.GetPlayerFromIdentifier(identifier) // Get player from identifier/citizenid
GlitchLib.Framework.GetPlayers() // Get all online players
```

#### Money Management

```javascript
GlitchLib.Framework.GetMoney(source) // Get player's cash
GlitchLib.Framework.AddMoney(source, amount) // Add cash to player
GlitchLib.Framework.RemoveMoney(source, amount) // Remove cash from player
GlitchLib.Framework.GetBankMoney(source) // Get player's bank balance
GlitchLib.Framework.AddBankMoney(source, amount) // Add to player's bank balance
GlitchLib.Framework.RemoveBankMoney(source, amount) // Remove from player's bank balance
```

#### Job Management

```javascript
GlitchLib.Framework.GetJob(source) // Get player's job
GlitchLib.Framework.SetJob(source, job, grade) // Set player's job and grade
```

#### Notification & Callbacks

```javascript
GlitchLib.Framework.RegisterCallback(name, callback) // Register a server callback
GlitchLib.Framework.Notify(source, message, type, length) // Send notification to player
```

### Inventory Functions

_Required Resources: One of: ox\_inventory, qb-inventory, or ESX inventory_

#### Item Management

```javascript
GlitchLib.Inventory.AddItem(source, item, amount, metadata, slot, info, reason) // Add item to player | QB does NOT use metadata and OX does NOT use info, or reason
GlitchLib.Inventory.RemoveItem(source, item, count, metadata, slot) // Remove item from player
GlitchLib.Inventory.GetItem(source, item, metadata) // Get item data for player
GlitchLib.Inventory.GetItemCount(source, item, metadata) // Get count of item player has
GlitchLib.Inventory.CanAddItem(source, item, amount) // Check if player can carry item
GlitchLib.Inventory.CanCarryItem(source, item, count) // Check if player can carry item
GlitchLib.Inventory.CanSwapItem(source, item, count, toSlot) // Check if player can swap item slots
GlitchLib.Inventory.SetInventory(source, items) // Set player's entire inventory
GlitchLib.Inventory.ClearInventory(source) // Clear player's inventory
GlitchLib.Inventory.SetItemData(source, itemName, key, val) // Set specific data for an item
GlitchLib.Inventory.UseItem(itemName, callback) // Register item usage handler
```

#### Inventory Management

```javascript
GlitchLib.Inventory.OpenInventory(source, invType, data) // Open inventory for player
GlitchLib.Inventory.CloseInventory(source, identifier) // Close inventory for player
GlitchLib.Inventory.OpenInventoryById(source, playerId) // Open another player's inventory
GlitchLib.Inventory.ConfiscateInventory(source) // Confiscate player inventory (ox)
GlitchLib.Inventory.ReturnInventory(source) // Return confiscated inventory (ox)
GlitchLib.Inventory.ClearInventory(inv, keep) // Clear specific inventory with optional keeps
```

#### Stash Management

```javascript
GlitchLib.Inventory.RegisterStash(id, label, slots, maxWeight, owner, groups, coords) // Register stash
GlitchLib.Inventory.CreateTemporaryStash(properties) // Create temporary stash (ox)
GlitchLib.Inventory.OpenShop(source, name) // Open shop menu
GlitchLib.Inventory.CreateShop(shopData) // Create custom shop
```

#### Drop Management

```javascript
GlitchLib.Inventory.CustomDrop(prefix, items, coords, slots, maxWeight, instance, model) // Create drop
GlitchLib.Inventory.CreateDropFromPlayer(playerId) // Create drop from player inventory
```

#### Item Lookup

```javascript
GlitchLib.Inventory.GetFreeWeight(source) // Get remaining weight capacity
GlitchLib.Inventory.GetSlots(identifier) // Get slot data for inventory
GlitchLib.Inventory.GetSlotsByItem(items, itemName) // Get all slots containing specific item
GlitchLib.Inventory.GetFirstSlotByItem(items, itemName) // Get first slot with specific item
GlitchLib.Inventory.GetItemBySlot(source, slot) // Get item in specific slot
GlitchLib.Inventory.GetItemByName(source, item) // Get first instance of item
GlitchLib.Inventory.GetItemsByName(source, item) // Get all instances of item
GlitchLib.Inventory.Search(source, search, item, metadata) // Search inventory (ox)
GlitchLib.Inventory.GetSlot(source, slot) // Get item in specific slot (ox)
GlitchLib.Inventory.SwapSlots(source, fromSlot, toSlot) // Swap inventory slots (ox)
```

#### Inventory State Control

```javascript
GlitchLib.Inventory.SetBusy(source, state) // Set inventory busy state
GlitchLib.Inventory.LockInventory(source) // Lock player inventory
GlitchLib.Inventory.UnlockInventory(source) // Unlock player inventory
```

### Notification Functions

_Required Resources: ox\_lib for server-side notifications_

#### Basic Notifications

```javascript
GlitchLib.ServerNotifications.Show(playerId, params) // Send notification to specific player
GlitchLib.ServerNotifications.Broadcast(params) // Send notification to all players
GlitchLib.ServerNotifications.Success(playerId, title, message, duration, options) // Send success notification
GlitchLib.ServerNotifications.Error(playerId, title, message, duration, options) // Send error notification
GlitchLib.ServerNotifications.Info(playerId, title, message, duration, options) // Send info notification
GlitchLib.ServerNotifications.Warning(playerId, title, message, duration, options) // Send warning notification
```

#### Broadcast Helpers

```javascript
GlitchLib.ServerNotifications.BroadcastSuccess(title, message, duration, options) // Broadcast success
GlitchLib.ServerNotifications.BroadcastError(title, message, duration, options) // Broadcast error
GlitchLib.ServerNotifications.BroadcastInfo(title, message, duration, options) // Broadcast info
GlitchLib.ServerNotifications.BroadcastWarning(title, message, duration, options) // Broadcast warning
```

#### Direct Access to ox\_lib Notifications

```javascript
GlitchLib.ServerNotifications.Ox.Show(playerId, params) // Send ox_lib notification to player
GlitchLib.ServerNotifications.Ox.Broadcast(params) // Broadcast ox_lib notification to all
GlitchLib.ServerNotifications.Ox.Success(playerId, title, message, duration, options) // Send ox success
GlitchLib.ServerNotifications.Ox.Error(playerId, title, message, duration, options) // Send ox error
GlitchLib.ServerNotifications.Ox.Info(playerId, title, message, duration, options) // Send ox info
GlitchLib.ServerNotifications.Ox.Warning(playerId, title, message, duration, options) // Send ox warning
GlitchLib.ServerNotifications.Ox.Custom(playerId, params) // Send custom ox notification
GlitchLib.ServerNotifications.Ox.WithSound(playerId, params, soundBank, soundSet, soundName) // Send with sound
GlitchLib.ServerNotifications.Ox.BroadcastSuccess(title, message, duration, options) // Broadcast ox success
GlitchLib.ServerNotifications.Ox.BroadcastError(title, message, duration, options) // Broadcast ox error
GlitchLib.ServerNotifications.Ox.BroadcastInfo(title, message, duration, options) // Broadcast ox info
GlitchLib.ServerNotifications.Ox.BroadcastWarning(title, message, duration, options) // Broadcast ox warning
```

### Door Lock Functions

_Required Resources: One of: ox\_doorlock, qb-doorlock, or esx\_doorlock_

```javascript
GlitchLib.DoorLock.GetDoorState(door) // Get door state (locked/unlocked)
GlitchLib.DoorLock.SetDoorState(door, state, playerId) // Set door state
GlitchLib.DoorLock.PlayerHasAccess(source, door) // Check if player has access to door
GlitchLib.DoorLock.GetAllDoors() // Get all doors
GlitchLib.DoorLock.AddDoor(door) // Add a new door (if supported)
GlitchLib.DoorLock.RemoveDoor(door) // Remove a door (if supported)
```

### Progression Functions

_Required Resources: pickle\_xp_

#### Experience Management

```javascript
GlitchLib.Progression.GetXP(source) // Get player's XP
GlitchLib.Progression.AddXP(source, amount, reason) // Add XP to player
GlitchLib.Progression.SetXP(source, amount) // Set player's XP
GlitchLib.Progression.GetLevel(source) // Get player's level
GlitchLib.Progression.SetLevel(source, level) // Set player's level
GlitchLib.Progression.AddLevels(source, amount) // Add levels to player
```

#### XP Sources

```javascript
GlitchLib.Progression.RegisterXPSource(name, min, max, notify) // Register XP source
GlitchLib.Progression.AwardXPFromSource(source, sourceName) // Award XP from source
```

#### Rank Management

```javascript
GlitchLib.Progression.GetRankData(source) // Get player's rank data
GlitchLib.Progression.GetUserData(source) // Get player's user data
GlitchLib.Progression.HasRank(source, rank) // Check if player has specific rank
```
