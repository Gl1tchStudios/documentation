---
description: '!  DOCUMENTATION IS NOT UP TO DATE WITH LATEST LIB UPDATE !'
---

# Client

## Client-Side Functions

### Framework Functions

_Required Resources: One of: ESX Legacy, QBCore, or QBox_

#### Player Data

```javascript
GlitchLib.Framework.GetPlayerData() // Returns player data
GlitchLib.Framework.TriggerCallback(name, callback, ...) // Trigger a server callback
GlitchLib.Framework.Notify(message, type, duration) // Show notification
GlitchLib.Framework.ShowHelpNotification(message, thisFrame) // Show help notification (ESX)
GlitchLib.Framework.SpawnPlayer(coords, callback) // Spawn player at coordinates
GlitchLib.Framework.DrawText(x, y, text) // Draw 2D text on screen
GlitchLib.Framework.Draw3DText(coords, text) // Draw 3D text in world
GlitchLib.Framework.GetClosestPlayer() // Returns closest player and distance
GlitchLib.Framework.GetVehicleProperties(vehicle) // Get vehicle properties
GlitchLib.Framework.SetVehicleProperties(vehicle, props) // Set vehicle properties
```

### Inventory Functions

_Required Resources: One of: ox\_inventory, qb-inventory, or ESX inventory_

#### Item Management

```javascript
GlitchLib.Inventory.GetItems(itemName) // Get an item or all items definition
GlitchLib.Inventory.UseItem(data, cb) // Use an item with callback
GlitchLib.Inventory.UseSlot(slot) // Use item in specific slot
```

#### Inventory Access

```javascript
GlitchLib.Inventory.OpenInventory() // Open player inventory
GlitchLib.Inventory.CloseInventory() // Close player inventory
GlitchLib.Inventory.SetStashTarget(id, owner) // Set stash target for interactions
```

#### Weapon Handling

```javascript
GlitchLib.Inventory.GetCurrentWeapon() // Get current weapon data
GlitchLib.Inventory.WeaponWheel(state) // Enable/disable weapon wheel
```

#### Item Lookup

```javascript
GlitchLib.Inventory.GetSlotWithItem(itemName, metadata, strict) // Get first slot containing item
GlitchLib.Inventory.GetSlotsWithItem(itemName, metadata, strict) // Get all slots containing item
```

#### Inventory States

```javascript
GlitchLib.Inventory.IsInventoryBusy() // Check if inventory is in use
GlitchLib.Inventory.SetInventoryBusy(state) // Set inventory busy state
GlitchLib.Inventory.AreHotkeysEnabled() // Check if inventory hotkeys are enabled
GlitchLib.Inventory.SetHotkeysEnabled(state) // Enable/disable inventory hotkeys
GlitchLib.Inventory.IsInventoryOpen() // Check if inventory is open
GlitchLib.Inventory.CanUseWeapons() // Check if weapons can be used
GlitchLib.Inventory.SetCanUseWeapons(state) // Enable/disable weapon usage
```

### UI Functions

_Required Resources: ox\_lib for most advanced features_

#### Input Dialog

_Required Resource: ox\_lib_

**Basic Input Dialog**

```javascript
GlitchLib.UI.Input(header, inputs, options) // Show input dialog window
GlitchLib.UI.CloseInputDialog() // Force close open input dialog
GlitchLib.UI.InputForm(title, fields, options) // Advanced dialog with typed fields
GlitchLib.UI.BuildForm(title, fields, options) // Convenience method for form building
```

**Input Field Constructors**

```javascript
GlitchLib.UI.Inputs.Text(label, options) // Create text input field
GlitchLib.UI.Inputs.Number(label, options) // Create number input field
GlitchLib.UI.Inputs.Checkbox(label, options) // Create checkbox input
GlitchLib.UI.Inputs.Select(label, optionsList, options) // Create dropdown select
GlitchLib.UI.Inputs.MultiSelect(label, optionsList, options) // Create multi-select dropdown
GlitchLib.UI.Inputs.Slider(label, options) // Create slider input
GlitchLib.UI.Inputs.Color(label, options) // Create color picker input
GlitchLib.UI.Inputs.Date(label, options) // Create date picker input
GlitchLib.UI.Inputs.DateRange(label, options) // Create date range picker input
GlitchLib.UI.Inputs.Time(label, options) // Create time picker input
GlitchLib.UI.Inputs.TextArea(label, options) // Create textarea input
```

#### Context Menu

_Required Resource: ox\_lib_

**Context Menu Management**

```javascript
GlitchLib.UI.RegisterContext(context) // Register a context menu
GlitchLib.UI.ShowContext(id) // Show a registered context menu
GlitchLib.UI.HideContext(onExit) // Hide visible context menu
GlitchLib.UI.GetOpenContext() // Get ID of open context menu
GlitchLib.UI.OpenContextMenu(id, title, options, menu, canClose) // Create and show in one step
GlitchLib.UI.ContextMenu(id, title, options, position) // Legacy context menu display
GlitchLib.UI.CreateContextMenu(id, title, options) // Legacy context menu registration
GlitchLib.UI.BuildMenuStructure(menuTree) // Helper for building nested menus
GlitchLib.UI.ConfirmContextMenu(id, title, message, onConfirm, onCancel, confirmText, cancelText) // Show confirmation dialog
```

#### Keyboard Navigation Menu

_Required Resource: ox\_lib_

**Menu Management**

```javascript
GlitchLib.UI.RegisterMenu(data, cb) // Register a keyboard navigation menu
GlitchLib.UI.ShowMenu(id) // Show a registered menu
GlitchLib.UI.HideMenu(onExit) // Hide current menu
GlitchLib.UI.GetOpenMenu() // Get ID of open menu
GlitchLib.UI.SetMenuOptions(id, options, index) // Update menu options
GlitchLib.UI.CreateMenuOption(label, options) // Helper for creating menu options
GlitchLib.UI.OpenMenu(id, title, options, position, callbacks) // Create and show in one step
GlitchLib.UI.ConfirmMenu(id, title, message, onConfirm, onCancel) // Show confirmation menu
```

#### Radial Menu

_Required Resource: ox\_lib_

**Radial Menu Management**

```javascript
GlitchLib.UI.AddRadialItem(items) // Add items to global radial menu
GlitchLib.UI.RemoveRadialItem(id) // Remove item from radial menu
GlitchLib.UI.ClearRadialItems() // Remove all items from radial menu
GlitchLib.UI.RegisterRadial(radial) // Register a sub-menu
GlitchLib.UI.HideRadial() // Hide current radial menu
GlitchLib.UI.DisableRadial(state) // Enable/disable radial menu
GlitchLib.UI.GetCurrentRadialId() // Get ID of current radial menu
GlitchLib.UI.CreateRadialItem(id, label, icon, options) // Helper for creating radial items
GlitchLib.UI.CreateRadialMenu(id, items) // Create and register a radial menu
GlitchLib.UI.QuickRadial(id, label, icon, onSelect) // Add a single radial item
GlitchLib.UI.RadialSubmenu(parentId, parentLabel, parentIcon, submenuId, submenuItems) // Create linked submenus
```

#### Progress Indicators

_Required Resource: ox\_lib_

**Progress Bar**

```javascript
GlitchLib.UI.ProgressBar(params) // Show progress bar with full parameter support
GlitchLib.UI.ProgressCircle(params) // Show circular progress indicator
GlitchLib.UI.IsProgressActive() // Check if progress bar is active
GlitchLib.UI.CancelProgress() // Cancel active progress
GlitchLib.UI.CreateAnimation(dict, clip, options) // Helper for creating animation parameters
GlitchLib.UI.CreateScenario(scenario, options) // Helper for creating scenario parameters
GlitchLib.UI.CreateProp(model, options) // Helper for creating prop parameters
GlitchLib.UI.DrinkProgress(duration, label, item) // Show drinking animation progress
GlitchLib.UI.EatProgress(duration, label, item) // Show eating animation progress
```

#### Text UI

_Required Resource: ox\_lib_

**Text UI Management**

```javascript
GlitchLib.UI.ShowTextUI(text, options) // Show text UI with full options
GlitchLib.UI.HideTextUI() // Hide visible text UI
GlitchLib.UI.IsTextUIOpen() // Check if text UI is visible and get text
GlitchLib.UI.StyledTextUI(text, position, icon, iconColor, style) // Show styled text UI
GlitchLib.UI.AnimatedTextUI(text, icon, animation, position, iconColor) // Show text UI with animated icon
```

**Text UI Style Presets**

```javascript
GlitchLib.UI.TextUIStyles.Success // Green success style
GlitchLib.UI.TextUIStyles.Error // Red error style
GlitchLib.UI.TextUIStyles.Info // Blue info style
GlitchLib.UI.TextUIStyles.Warning // Orange warning style
GlitchLib.UI.TextUIStyles.Custom(bgColor, textColor, borderRadius) // Custom style creator
```

**Text UI Templates**

```javascript
GlitchLib.UI.ShowInteractionTextUI(text, key) // Show interaction prompt
GlitchLib.UI.ShowSuccessTextUI(text) // Show success message
GlitchLib.UI.ShowErrorTextUI(text) // Show error message
GlitchLib.UI.ShowWarningTextUI(text) // Show warning message
```

#### Skill Check

_Required Resource: ox\_lib_

**Skill Check System**

```javascript
GlitchLib.UI.SkillCheck(difficulty, inputs) // Run a skill check with defined difficulty
GlitchLib.UI.IsSkillCheckActive() // Check if a skill check is active
GlitchLib.UI.CancelSkillCheck() // Cancel ongoing skill check
GlitchLib.UI.CustomDifficulty(areaSize, speedMultiplier) // Create custom difficulty
GlitchLib.UI.SkillCheckSequence(difficulties, inputs, onComplete, onFail) // Run sequence of checks
GlitchLib.UI.Lockpick(difficulty, callback) // Convenience function for lockpicking
GlitchLib.UI.Hack(difficulty, inputs, callback) // Convenience function for hacking
```

#### Alert Dialog

_Required Resource: ox\_lib_

**Alert Dialog**

```javascript
GlitchLib.UI.Alert(titleOrParams, message, typeParam, icon) // Show alert dialog
```

### Notification Functions

_Required Resources: One of: ox\_lib, ESX, QBCore, or internal Glitch Notifications_

#### Basic Notifications

```javascript
GlitchLib.Notifications.Show(params) // Show notification with parameters
GlitchLib.Notifications.Success(title, message, duration, options) // Show success notification
GlitchLib.Notifications.Error(title, message, duration, options) // Show error notification
GlitchLib.Notifications.Info(title, message, duration, options) // Show info notification
GlitchLib.Notifications.Warning(title, message, duration, options) // Show warning notification
```

#### Direct Access to Specific Systems

```javascript
GlitchLib.Notifications.Glitch.Show(params) // Show Glitch notification (no external dependency)
GlitchLib.Notifications.Glitch.Success(title, message, duration) // Show Glitch success notification
GlitchLib.Notifications.Glitch.Error(title, message, duration) // Show Glitch error notification
GlitchLib.Notifications.Glitch.Toggle(id, title, message, color) // Toggle persistent notification

GlitchLib.Notifications.Ox.Show(params) // Show ox_lib notification (requires ox_lib)
GlitchLib.Notifications.Ox.Success(title, message, duration, options) // Show ox_lib success notification
GlitchLib.Notifications.Ox.Error(title, message, duration, options) // Show ox_lib error notification
GlitchLib.Notifications.Ox.Info(title, message, duration, options) // Show ox_lib info notification
GlitchLib.Notifications.Ox.Warning(title, message, duration, options) // Show ox_lib warning notification
GlitchLib.Notifications.Ox.Custom(params) // Show custom styled ox_lib notification
GlitchLib.Notifications.Ox.WithSound(params, soundBank, soundSet, soundName) // Show notification with sound
GlitchLib.Notifications.Ox.WithAnimation(params, animation, iconAlign) // Show notification with animated icon
```

### Target System Functions

_Required Resources: One of: ox\_target, qb-target, or bt-target_

#### Entity Targeting

```javascript
GlitchLib.Target.AddTargetEntity(entities, options) // Add options to specific entities
GlitchLib.Target.AddTargetModel(models, options) // Add options to all entities of specified models
```

#### Zone Targeting

```javascript
GlitchLib.Target.AddBoxZone(name, center, length, width, options, targetOptions) // Create box interaction zone | Alternative for ox: AddBoxZone({parameters})
GlitchLib.Target.AddSphereZone(name, center, radius, options, targetOptions) // Create spherical interaction zone
GlitchLib.Target.RemoveZone(id) // Remove interaction zone
```

#### Global Targeting

```javascript
GlitchLib.Target.AddGlobalPlayer(options) // Add options to all players
GlitchLib.Target.AddGlobalVehicle(options) // Add options to all vehicles
GlitchLib.Target.AddGlobalObject(options) // Add options to all objects
```

### Door Lock Functions

_Required Resources: One of: ox\_doorlock, qb-doorlock, or esx\_doorlock_

```javascript
GlitchLib.DoorLock.IsDoorLocked(door) // Check if door is locked (id or name)
GlitchLib.DoorLock.SetDoorLocked(door, state) // Lock/unlock a door
GlitchLib.DoorLock.GetNearbyDoors() // Get doors near the player
GlitchLib.DoorLock.GetAllDoors() // Get all doors
GlitchLib.DoorLock.HasAccess(door) // Check if player has access to door
```

### Cutscenes Functions

_Required Resources: None (uses native GTA functions)_

#### Appearance Management

```javascript
GlitchLib.Cutscene.SavePlayerAppearance() // Save current player appearance
GlitchLib.Cutscene.RestorePlayerAppearance() // Restore saved player appearance
```

#### Cutscene Control

```javascript
GlitchLib.Cutscene.Play(cutsceneName, options) // Play cutscene with options
GlitchLib.Cutscene.Stop(immediate) // Stop current cutscene
GlitchLib.Cutscene.IsActive() // Check if a cutscene is active
GlitchLib.Cutscene.IsPlaying() // Check if a cutscene is currently playing
GlitchLib.Cutscene.GetTime() // Get current cutscene time (ms)
GlitchLib.Cutscene.SkipToTime(time) // Skip to specific time in cutscene (ms)
```

### Progression Functions

_Required Resources: pickle\_xp_

#### Experience & Levels

```javascript
GlitchLib.Progression.GetXP() // Get player's current XP
GlitchLib.Progression.GetLevel() // Get player's current level
GlitchLib.Progression.GetRankData() // Get detailed rank data
GlitchLib.Progression.GetUserData() // Get user's progression data
GlitchLib.Progression.HasRank(rank) // Check if player has specific rank
```

#### UI Functions

```javascript
GlitchLib.Progression.DrawXPBar(show) // Show/hide XP bar
GlitchLib.Progression.ShowRank(state) // Show/hide rank display
```

### Scaleform Functions

_Required Resources: None (uses native GTA functions)_

#### Basic Scaleform Management

```javascript
GlitchLib.Scaleform.Load(name) // Load a scaleform by name, returns handle
GlitchLib.Scaleform.Unload(nameOrHandle) // Unload a scaleform by name or handle
GlitchLib.Scaleform.CallFunction(handleOrName, returnValue, funcName, ...) // Call function on scaleform
GlitchLib.Scaleform.Render(handleOrName, x, y, width, height, r, g, b, a, scale) // Render scaleform 2D
GlitchLib.Scaleform.Render3D(handleOrName, x, y, z, rx, ry, rz, scale) // Render scaleform in 3D world
```

#### Common Scaleform UIs

```javascript
GlitchLib.Scaleform.SetupInstructionalButtons(buttons) // Create instructional buttons UI
GlitchLib.Scaleform.ShowMessageBox(title, subtitle, footer) // Show a large message box
GlitchLib.Scaleform.ShowMissionPassed(title, subtitle, rp, money) // Show mission passed UI
GlitchLib.Scaleform.ShowCountdown(number, message) // Show a countdown UI
GlitchLib.Scaleform.ShowCredits(items) // Show scrolling credits UI
```
