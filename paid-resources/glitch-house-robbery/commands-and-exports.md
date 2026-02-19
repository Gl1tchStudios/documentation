# Commands & Exports

### Commands

#### Admin Commands

All admin commands require the `group.admin` permission.

**`/addhouse`**

Adds a new house robbery location at your current position.

**Usage:** `/addhouse`

**Permission Required:** `group.admin`

**Description:**

* Creates a new house robbery location at the admin's current coordinates
* Automatically saves the location to the `shared/config.lua` file
* Displays a notification with the total number of houses after adding
* Useful for expanding robbery locations on your server

**Example:**

```
/addhouse
> Success! House added successfully at your location! Total houses: 15
```

***

**`/deletehouse`**

Removes the closest house robbery location to your current position.

**Usage:** `/deletehouse`

**Permission Required:** `group.admin`

**Description:**

* Finds the nearest house robbery location to your current position
* Removes it from the configuration
* Automatically saves changes to the `shared/config.lua` file
* Shows the distance to the removed house and remaining count
* Useful for removing unwanted or misplaced house locations

**Example:**

```
/deletehouse
> Success! Removed closest house (45.2m away)! Remaining: 14
```

***

#### Debug Commands

Debug commands are only available when `Config.Debug = true` in the configuration file.

**`/housedebug`**

Main debug command that displays all available debug sub-commands.

**Usage:** `/housedebug [action] [parameters]`

**Permission Required:** None (only available in debug mode)

***

**`/housedebug shell [tier|model]`**

Spawns a test shell at your current location for testing purposes.

**Usage:**

* `/housedebug shell [1-4]` - Spawn by tier number
* `/housedebug shell [model_name]` - Spawn by custom model name

**Parameters:**

* `tier` (1-4): Tier number to spawn (uses the shell model from Config.Tiers)
* `model_name`: Custom shell model name (e.g., `k4mb1_apartment_shell`)

**Description:**

* Spawns a shell interior at your location for testing
* Can spawn by tier number or custom model name
* Automatically sets your position inside the shell
* Useful for testing interior layouts and loot zone placements

**Examples:**

```
/housedebug shell 2
> Success! Spawned Tier 2 shell

/housedebug shell k4mb1_apartment_shell
> Success! Spawned custom shell: k4mb1_apartment_shell
```

***

**`/housedebug getcoords`**

Retrieves your current coordinates and heading.

**Usage:** `/housedebug getcoords`

**Description:**

* Gets your current world coordinates (X, Y, Z)
* Gets your current heading/rotation
* Automatically copies coordinates to clipboard as `vector3(x, y, z)`
* Displays coordinates in both console (F8) and notification
* Useful for setting up spawn points, interaction zones, etc.

**Example Output:**

```
=== DEBUG COORDINATES ===
Position: vector3(123.456789, -987.654321, 45.678901)
Heading: 180.456789
Coordinates copied to clipboard!
```

***

**`/housedebug offset`**

Calculates the offset from a spawned shell to your current position.

**Usage:** `/housedebug offset`

**Requirements:** Must have a shell spawned first using `/housedebug shell`

**Description:**

* Calculates the offset between the shell origin and your current position
* Generates a complete loot zone configuration
* Automatically copies the formatted config to clipboard
* Essential for creating accurate loot zones in shell interiors
* Output format is ready to paste into `Config.Tiers[x].lootZones`

**Example Output:**

```
=== DEBUG LOOT ZONE OFFSET ===
Shell Coords: 100.00, 200.00, 30.00
Player Coords: 105.50, 203.25, 31.00
Offset: 5.500000, 3.250000, 1.000000
Rotation: 90.000000
Loot zone config copied to clipboard!
```

**Clipboard Content:**

```lua
{
    offset = vector3(5.500000, 3.250000, 1.000000),
    size = vec3(1.0, 1.0, 10.0),
    rotation = 90.000000,
},
```

***

**`/housedebug zones`**

Toggles zone visualization for spawned shells.

**Usage:** `/housedebug zones`

**Requirements:** Must have a shell spawned first

**Description:**

* Toggles the visual display of interaction zones
* Shows loot zones, entry/exit points, etc.
* Helps with precise zone placement and debugging
* Useful for verifying zone sizes and positions

**Example:**

```
/housedebug zones
> Info: Zone visualization enabled
```

***

**`/housedebug cleanup`**

Removes all debug shells, zones, and resets debug state.

**Usage:** `/housedebug cleanup`

**Description:**

* Despawns any active debug shells
* Removes all created interaction zones
* Resets the current tier state
* Cleans up the testing environment
* Use this before leaving the area or testing new configurations

**Example:**

```
/housedebug cleanup
> Info: Cleaned up debug shell and zones
```

***

### Exports

#### Server Exports

**`useLockpick`**

Export used by ox\_inventory to handle lockpick usage.

**Type:** Server Export

**Usage:**

```lua
exports['glitch-houserobbery']:useLockpick(event, item, inventory)
```

**Parameters:**

* `event` (string): The oxinventory event type ("usingItem")
* `item` (table): Item data
* `inventory` (table): Player inventory data

**Description:**

* Triggered when a player uses a lockpick item from ox\_inventory
* Validates the player and triggers the door picking minigame
* Integrates with ox\_inventory's item use system
