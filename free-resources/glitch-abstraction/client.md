---
description: >-
  This page documents all available client-side functions in Glitch Abstraction.
  Functions are grouped by system and include required dependencies where
  applicable.
---

# Client

### Framework Functions

**Required Resource:** One of: ESX Legacy, QBCore, or QBox

#### Player Data

* `GlitchLib.Framework.GetPlayerData()`
  * Returns player data (job, money, etc.)
* `GlitchLib.Framework.TriggerCallback(name, callback, ...)`
  * Trigger a server callback and receive the result in `callback`
* `GlitchLib.Framework.Notify(message, type, duration)`
  * Show a notification (type: 'success', 'info', 'error', 'warning')
* `GlitchLib.Framework.ShowHelpNotification(message, thisFrame)`
  * Show a help notification (ESX only)
* `GlitchLib.Framework.SpawnPlayer(coords, callback)`
  * Spawn player at coordinates
* `GlitchLib.Framework.DrawText(x, y, text)`
  * Draw 2D text on screen
* `GlitchLib.Framework.Draw3DText(coords, text)`
  * Draw 3D text in world
* `GlitchLib.Framework.GetClosestPlayer()`
  * Returns closest player and distance
* `GlitchLib.Framework.GetVehicleProperties(vehicle)`
  * Get vehicle properties
* `GlitchLib.Framework.SetVehicleProperties(vehicle, props)`
  * Set vehicle properties

***

### Inventory Functions

**Required Resource:** One of: ox\_inventory, qb-inventory, or ESX inventory

#### Item Management

* `GlitchLib.Inventory.GetItems(itemName)`
  * Get an item or all item definitions
* `GlitchLib.Inventory.UseItem(data, cb)`
  * Use an item with callback
* `GlitchLib.Inventory.UseSlot(slot)`
  * Use item in specific slot

#### Inventory Access

* `GlitchLib.Inventory.OpenInventory()`
  * Open player inventory
* `GlitchLib.Inventory.CloseInventory()`
  * Close player inventory
* `GlitchLib.Inventory.SetStashTarget(id, owner)`
  * Set stash target for interactions

#### Weapon Handling

* `GlitchLib.Inventory.GetCurrentWeapon()`
  * Get current weapon data
* `GlitchLib.Inventory.WeaponWheel(state)`
  * Enable/disable weapon wheel

#### Item Lookup

* `GlitchLib.Inventory.GetSlotWithItem(itemName, metadata, strict)`
  * Get first slot containing item
* `GlitchLib.Inventory.GetSlotsWithItem(itemName, metadata, strict)`
  * Get all slots containing item

#### Inventory States

* `GlitchLib.Inventory.IsInventoryBusy()`
  * Check if inventory is in use
* `GlitchLib.Inventory.SetInventoryBusy(state)`
  * Set inventory busy state
* `GlitchLib.Inventory.AreHotkeysEnabled()`
  * Check if inventory hotkeys are enabled
* `GlitchLib.Inventory.SetHotkeysEnabled(state)`
  * Enable/disable inventory hotkeys
* `GlitchLib.Inventory.IsInventoryOpen()`
  * Check if inventory is open
* `GlitchLib.Inventory.CanUseWeapons()`
  * Check if weapons can be used
* `GlitchLib.Inventory.SetCanUseWeapons(state)`
  * Enable/disable weapon usage

***

### UI Functions

**Required Resource:** ox\_lib for most advanced features

#### Input Dialog

* `GlitchLib.UI.Input(header, inputs, options)`
  * Show input dialog window
* `GlitchLib.UI.CloseInputDialog()`
  * Force close open input dialog
* `GlitchLib.UI.InputForm(title, fields, options)`
  * Advanced dialog with typed fields
* `GlitchLib.UI.BuildForm(title, fields, options)`
  * Convenience method for form building

**Input Field Constructors**

* `GlitchLib.UI.Inputs.Text(label, options)`
* `GlitchLib.UI.Inputs.Number(label, options)`
* `GlitchLib.UI.Inputs.Checkbox(label, options)`
* `GlitchLib.UI.Inputs.Select(label, optionsList, options)`
* `GlitchLib.UI.Inputs.MultiSelect(label, optionsList, options)`
* `GlitchLib.UI.Inputs.Slider(label, options)`
* `GlitchLib.UI.Inputs.Color(label, options)`
* `GlitchLib.UI.Inputs.Date(label, options)`
* `GlitchLib.UI.Inputs.DateRange(label, options)`
* `GlitchLib.UI.Inputs.Time(label, options)`
* `GlitchLib.UI.Inputs.TextArea(label, options)`

#### Context Menu

* `GlitchLib.UI.RegisterContext(context)`
* `GlitchLib.UI.ShowContext(id)`
* `GlitchLib.UI.HideContext(onExit)`
* `GlitchLib.UI.GetOpenContext()`
* `GlitchLib.UI.OpenContextMenu(id, title, options, menu, canClose)`
* `GlitchLib.UI.ContextMenu(id, title, options, position)`
* `GlitchLib.UI.CreateContextMenu(id, title, options)`
* `GlitchLib.UI.BuildMenuStructure(menuTree)`
* `GlitchLib.UI.ConfirmContextMenu(id, title, message, onConfirm, onCancel, confirmText, cancelText)`

#### Keyboard Navigation Menu

* `GlitchLib.UI.RegisterMenu(data, cb)`
* `GlitchLib.UI.ShowMenu(id)`
* `GlitchLib.UI.HideMenu(onExit)`
* `GlitchLib.UI.GetOpenMenu()`
* `GlitchLib.UI.SetMenuOptions(id, options, index)`
* `GlitchLib.UI.CreateMenuOption(label, options)`
* `GlitchLib.UI.OpenMenu(id, title, options, position, callbacks)`
* `GlitchLib.UI.ConfirmMenu(id, title, message, onConfirm, onCancel)`

#### Radial Menu

* `GlitchLib.UI.AddRadialItem(items)`
* `GlitchLib.UI.RemoveRadialItem(id)`
* `GlitchLib.UI.ClearRadialItems()`
* `GlitchLib.UI.RegisterRadial(radial)`
* `GlitchLib.UI.HideRadial()`
* `GlitchLib.UI.DisableRadial(state)`
* `GlitchLib.UI.GetCurrentRadialId()`
* `GlitchLib.UI.CreateRadialItem(id, label, icon, options)`
* `GlitchLib.UI.CreateRadialMenu(id, items)`
* `GlitchLib.UI.QuickRadial(id, label, icon, onSelect)`
* `GlitchLib.UI.RadialSubmenu(parentId, parentLabel, parentIcon, submenuId, submenuItems)`

#### Progress Indicators

* `GlitchLib.UI.ProgressBar(params)`
* `GlitchLib.UI.ProgressCircle(params)`
* `GlitchLib.UI.IsProgressActive()`
* `GlitchLib.UI.CancelProgress()`
* `GlitchLib.UI.CreateAnimation(dict, clip, options)`
* `GlitchLib.UI.CreateScenario(scenario, options)`
* `GlitchLib.UI.CreateProp(model, options)`
* `GlitchLib.UI.DrinkProgress(duration, label, item)`
* `GlitchLib.UI.EatProgress(duration, label, item)`

#### Text UI

* `GlitchLib.UI.ShowTextUI(text, options)`
* `GlitchLib.UI.HideTextUI()`
* `GlitchLib.UI.IsTextUIOpen()`
* `GlitchLib.UI.StyledTextUI(text, position, icon, iconColor, style)`
* `GlitchLib.UI.AnimatedTextUI(text, icon, animation, position, iconColor)`

**Text UI Style Presets**

* `GlitchLib.UI.TextUIStyles.Success`
* `GlitchLib.UI.TextUIStyles.Error`
* `GlitchLib.UI.TextUIStyles.Info`
* `GlitchLib.UI.TextUIStyles.Warning`
* `GlitchLib.UI.TextUIStyles.Custom(bgColor, textColor, borderRadius)`

**Text UI Templates**

* `GlitchLib.UI.ShowInteractionTextUI(text, key)`
* `GlitchLib.UI.ShowSuccessTextUI(text)`
* `GlitchLib.UI.ShowErrorTextUI(text)`
* `GlitchLib.UI.ShowWarningTextUI(text)`

#### Skill Check

* `GlitchLib.UI.SkillCheck(difficulty, inputs)`
* `GlitchLib.UI.IsSkillCheckActive()`
* `GlitchLib.UI.CancelSkillCheck()`
* `GlitchLib.UI.CustomDifficulty(areaSize, speedMultiplier)`
* `GlitchLib.UI.SkillCheckSequence(difficulties, inputs, onComplete, onFail)`
* `GlitchLib.UI.Lockpick(difficulty, callback)`
* `GlitchLib.UI.Hack(difficulty, inputs, callback)`

#### Alert Dialog

* `GlitchLib.UI.Alert(titleOrParams, message, typeParam, icon)`

***

### Notification Functions

**Required Resource:** One of: ox\_lib, ESX, QBCore, or internal Glitch Notifications

#### Basic Notifications

* `GlitchLib.Notifications.Show(params)`
* `GlitchLib.Notifications.Success(title, message, duration, options)`
* `GlitchLib.Notifications.Error(title, message, duration, options)`
* `GlitchLib.Notifications.Info(title, message, duration, options)`
* `GlitchLib.Notifications.Warning(title, message, duration, options)`

#### Direct Access to Specific Systems

* `GlitchLib.Notifications.Glitch.Show(params)`
* `GlitchLib.Notifications.Glitch.Success(title, message, duration)`
* `GlitchLib.Notifications.Glitch.Error(title, message, duration)`
* `GlitchLib.Notifications.Glitch.Toggle(id, title, message, color)`
* `GlitchLib.Notifications.Ox.Show(params)`
* `GlitchLib.Notifications.Ox.Success(title, message, duration, options)`
* `GlitchLib.Notifications.Ox.Error(title, message, duration, options)`
* `GlitchLib.Notifications.Ox.Info(title, message, duration, options)`
* `GlitchLib.Notifications.Ox.Warning(title, message, duration, options)`
* `GlitchLib.Notifications.Ox.Custom(params)`
* `GlitchLib.Notifications.Ox.WithSound(params, soundBank, soundSet, soundName)`
* `GlitchLib.Notifications.Ox.WithAnimation(params, animation, iconAlign)`

***

### Target System Functions

**Required Resource:** One of: ox\_target, qb-target, or bt-target

#### Entity Targeting

* `GlitchLib.Target.AddTargetEntity(entities, options)`
* `GlitchLib.Target.AddTargetModel(models, options)`

#### Zone Targeting

* `GlitchLib.Target.AddBoxZone(name, center, length, width, options, targetOptions)`
* `GlitchLib.Target.AddSphereZone(name, center, radius, options, targetOptions)`
* `GlitchLib.Target.RemoveZone(id)`

#### Global Targeting

* `GlitchLib.Target.AddGlobalPlayer(options)`
* `GlitchLib.Target.AddGlobalVehicle(options)`
* `GlitchLib.Target.AddGlobalObject(options)`

***

### Door Lock Functions

**Required Resource:** One of: ox\_doorlock, qb-doorlock, or esx\_doorlock

* `GlitchLib.DoorLock.IsDoorLocked(door)`
* `GlitchLib.DoorLock.SetDoorLocked(door, state)`
* `GlitchLib.DoorLock.GetNearbyDoors()`
* `GlitchLib.DoorLock.GetAllDoors()`
* `GlitchLib.DoorLock.HasAccess(door)`

***

### Cutscenes Functions

**Required Resource:** None (uses native GTA functions)

#### Appearance Management

* `GlitchLib.Cutscene.SavePlayerAppearance()`
* `GlitchLib.Cutscene.RestorePlayerAppearance()`

#### Cutscene Control

* `GlitchLib.Cutscene.Play(cutsceneName, options)`
* `GlitchLib.Cutscene.Stop(immediate)`
* `GlitchLib.Cutscene.IsActive()`
* `GlitchLib.Cutscene.IsPlaying()`
* `GlitchLib.Cutscene.GetTime()`
* `GlitchLib.Cutscene.SkipToTime(time)`

***

### Progression Functions

**Required Resource:** pickle\_xp

#### Experience & Levels

* `GlitchLib.Progression.GetXP()`
* `GlitchLib.Progression.GetLevel()`
* `GlitchLib.Progression.GetRankData()`
* `GlitchLib.Progression.GetUserData()`
* `GlitchLib.Progression.HasRank(rank)`

#### UI Functions

* `GlitchLib.Progression.DrawXPBar(show)`
* `GlitchLib.Progression.ShowRank(state)`

***

### Scaleform Functions

**Required Resource:** None (uses native GTA functions)

#### Basic Scaleform Management

* `GlitchLib.Scaleform.Load(name)`
* `GlitchLib.Scaleform.Unload(nameOrHandle)`
* `GlitchLib.Scaleform.CallFunction(handleOrName, returnValue, funcName, ...)`
* `GlitchLib.Scaleform.Render(handleOrName, x, y, width, height, r, g, b, a, scale)`
* `GlitchLib.Scaleform.Render3D(handleOrName, x, y, z, rx, ry, rz, scale)`

#### Common Scaleform UIs

* `GlitchLib.Scaleform.SetupInstructionalButtons(buttons)`
* `GlitchLib.Scaleform.ShowMessageBox(title, subtitle, footer)`
* `GlitchLib.Scaleform.ShowMissionPassed(title, subtitle, rp, money)`
* `GlitchLib.Scaleform.ShowCountdown(number, message)`
* `GlitchLib.Scaleform.ShowCredits(items)`
