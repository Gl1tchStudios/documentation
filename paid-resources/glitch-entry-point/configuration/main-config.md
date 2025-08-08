# Main Config

This guide will help you understand and modify the configuration for the Entry Point training system, a tactical police training resource for FiveM servers.

### Table of Contents

1. [Basic Settings](main-config.md#basic-settings)
2. [Police & Permission Settings](main-config.md#police-and-permission-settings)
3. [Game Mechanics](main-config.md#game-mechanics)
4. [Player & NPC Configuration](main-config.md#player-and-npc-configuration)
5. [UI & Notifications](main-config.md#ui-and-notifications)
6. [Weapons Configuration](main-config.md#weapons-configuration)
7. [Map Selection System](main-config.md#map-selection-system)
8. [Spawn Points & Maps](main-config.md#spawn-points-and-maps)
9. [Interior Maps](main-config.md#interior-maps)
10. [Small Interiors](main-config.md#small-interiors)

***

### Basic Settings

#### Debug Mode

```lua
Config.Debug = false
```

* **Purpose**: Enables debug logging and additional console output
* **Values**: `true` or `false`
* **Recommendation**: Keep `false` in production

#### Routing Bucket

```lua
Config.orgBucket = 0
```

* **Purpose**: The routing bucket players are placed in after completing training
* **Values**: Any integer
* **Note**: Most servers should keep this as `0` (default world)

***

### Police & Permission Settings

#### Police Jobs

```lua
Config.PoliceRole = { 'police', 'offpolice' }
```

* **Purpose**: Defines which job names can access the training system
* **Format**: Table of strings
* Example: Add more jobs like `{ 'police', 'sheriff', 'state'` - set to false to disable.&#x20;

#### Minimum Grade Requirement

```lua
Config.PoliceGrade = 3
```

* **Purpose**: Minimum job grade required to access training for all jobs defined in Config.PoliceRole

#### Discord Role Verification (Optional)

```lua
Config.DiscordRoleCheck = false
Config.DiscordRolesToCheck = {
    "Senior Admin Team",
    "Admin Team", 
    "Tactical Operations Unit",
    "Police Leaders"
}
```

* **Purpose**: Additional permission layer using Discord roles for those starting the match
* **Setup**: Set `DiscordRoleCheck = true` and add your Discord role names, you'll need to set this up with your own role check script in config-client.lua under the function roleCheck()

***

### Game Mechanics

#### Hostage Behaviour

```lua
Config.hostileHostageChance = 40
```

* **Purpose**: Percentage chance (0-100) that a hostage will become hostile when players attempt to cuff them
* **Balance**: Higher values = more challenging scenarios

#### Hostage Death Consequences

```lua
Config.deadHostageResponse = 'mask'
```

* **Purpose:** Adds a consequence to killing a hostage who is not hostile
* **Options**:
  * `'mask'` - Replaces player's mask as punishment
  * `'death'` - Kills the player
  * `false` - No consequence

#### Mask Punishment Settings (if using 'mask' option)

```lua
Config.hostageKilledMask_Male = 97
Config.hostageKilledMaskTexture_Male = 0
Config.hostageKilledMask_Female = 97
Config.hostageKilledMaskTexture_Female = 0
```

***

### Player & NPC Configuration

#### Default Guard/Hostage Stats

```lua
Config.defaultHealth = 100
Config.defaultArmor = 0
Config.defaultAccuracy = 80
```

* **Health**: 1-200 (100 = full health)
* **Armor**: 0-100 (0 = no armor)
* **Accuracy**: 0-100 (affects AI accuracy)

#### NPC Guard Models

```lua
Config.SoldierModels = { 
    's_m_y_marine_02', 
    'csb_mweather', 
    's_m_y_swat_01', 
    's_m_y_marine_03' 
}
```

* **Purpose**: Random selection of guard/enemy models
* **Format**: Valid GTA V ped model names

#### Default Weapons

```lua
Config.defaultWeapon = 'weapon_carbinerifle'
Config.hostileHostageWeapon = 'WEAPON_pistol'
```

***

### UI & Notifications

#### Radio Settings

```lua
Config.useRadio = false
Config.defaultRadio = 997
```

* **useRadio**: Enable/disable automatic radio channel assignment
* **defaultRadio**: Channel number to assign players
* **Radio Script:** Will need to implement your own radio script functionality in config-client.lua.

#### Notification Settings

<pre class="language-lua"><code class="lang-lua"><strong>Config.notifyTitle = 'Entry Point'
</strong>Config.notifyAnimation = 'beatFade'
Config.notifyIcon = 'fa-solid fa-person-rifle'
</code></pre>

***

### Weapons Configuration

The weapons table defines available weapons in the training system:

```lua
Config.Weapons = {
    { value = 'weapon_g36', label = 'G36' },
    { value = 'WEAPON_PISTOL', label = 'Pistol' },
    -- Add more weapons here
}
```

#### Adding New Weapons

```lua
{ value = 'WEAPON_HASH', label = 'Display Name' },
```

***

### Map Selection System

#### Menu Structure

```lua
Config.mapSelection = {
    menuId = 'map_selection',
    title = 'Select Map Category!',
    options = {
        {
            title = 'External Maps',
            description = 'Maps outside in the fresh air!',
            icon = 'fa-solid fa-tree',
            menu = 'map_selection_external',
        },
        {
            title = 'Interiors', 
            description = 'Maps inside buildings!',
            icon = 'fa-solid fa-door-closed',
            menu = 'map_selection_interior',
        },
    }
}
```

***

### Best Practices

#### Performance Optimization

* Keep enemy counts reasonable (15-30 for most maps)
* Use polyZones to limit map boundaries
* Test maps with multiple players

#### Balance Considerations

* Outdoor maps can handle more enemies
* Indoor maps should have fewer enemies but more tactical complexity
* Consider sightlines and cover when placing enemies

#### Testing New Maps

1. Load the map with debug enabled
2. Test with minimum and maximum enemy counts
3. Verify all spawn points are accessible
4. Check that polyZone boundaries work correctly
5. Test with multiple players

#### Troubleshooting Common Issues

**Players spawning in walls/ground:**

* Check Z coordinate accuracy
* Ensure `findZ = true` for external maps if needed

**Enemies not spawning:**

* Verify coordinate format (vector4 with heading)
* Check that coordinates are within the map boundaries

**Menu not displaying maps:**

* Confirm `menuId` matches between map and menu configuration
* Verify all required fields are present

**Performance issues:**

* Reduce enemy counts
* Optimize polyZone point count
* Check for overlapping spawn points

***

### Support & Resources

* **Coordinates**: Use in-game coordinate tools or scripts
* **Icons**: Font Awesome icons (fa-solid, fa-regular, etc.)
* **Models**: GTA V ped and vehicle spawn names
* **IPL**: bob74\_ipl documentation for interior configuration

Remember to restart your resource after making configuration changes!
