# Configuration

## ⚙️ Configuration

The Casino Heist resource offers extensive customization options through the `config.lua` file. This guide covers all available configuration options to help you set up the perfect heist experience.

### 🎮 Minigame Dependencies

Before configuring the heist, ensure you have the required minigame dependencies installed based on your chosen hack types:

#### SN-Hacking Series

* `SN-MemoryGame`
* `SN-NumberUp`
* `SN-SkillCheck`
* `SN-Thermite`
* `SN-SkillBar`
* `SN-KeyPad`
* `SN-ColorPicker`
* `SN-MemoryCards`

#### Glow Minigames

* `glow-Path`
* `glow-Spot`
* `glow-Math`

#### Pure Minigames

* `pure-NumberCounter`

#### BD Minigames

* `bd-PinCracker`
* `bd-Chopping`
* `bd-RoofRunning`
* `bd-Thermite`
* `bd-Terminal`

#### BOII Minigames

* `boii-ButtonMash`
* `boii-Anagram`
* `boii-ChipHack`
* `boii-Hangman`
* `boii-KeyDrop`
* `boii-Pincode`
* `boii-SafeCrack`
* `boii-SkillBar`
* `boii-SkillCircle`
* `boii-Wirecut`

#### OX Lib

* `ox-SkillCircle`
* `glitch-keypad` (Requires ox\_lib)



Glitch Minigames

* Every Minigame that Glitch Minigames has

### 🔧 Basic Configuration

#### Testing & Debug

```lua
config.TestingMode = false
```

Set to `true` to enable debug messages and testing features. Set to `false` for production use.

#### Notification System

```lua
config.Notifications = "ox"
```

Supported options: `"ox"` or `"glitch"`

#### Hints System

```lua
config.Hints = true
```

Set to `false` to disable heist hints (feature not complete).

### ⏰ Timing Configuration

#### Power Station Settings

```lua
config.BlackoutTime = 10 -- Time in minutes for power station to be offline
config.TimeToRepairCasino = 4 -- Time in minutes to repair casino power
```

#### Vault Looting Timer

```lua
config.timeLimitOnLootingVault = true -- Enable/disable vault time limit
config.timeToLootVault = 60 * 4 -- Time in seconds (240 seconds = 4 minutes)
```

### 🚪 Entry & Exit Locations

#### Casino Entry Points

The heist supports multiple entry methods with specific spawn locations:

```lua
config.CasinoEnterLocations = {
    main = {1000.9869, 52.8287, 75.0596, 237.4639},
    partyroof = {960.1717, 43.1645, 71.6945, 103.9184},
    roof = {971.9659, 52.1280, 120.2407, 149.8707},
    sewer = {993.2103, -140.8808, 34.7420, 321.7434},
    penthouse = {2514.3110, -231.3394, -39.1229, 0.2265},
}
```

#### Teleport Destinations

Corresponding interior locations for each entry method:

```lua
config.CasinoTeleportLocations = {
    main = {2501.8677, -237.3059, -55.1232, 272.6512},
    partyroof = {965.0214, 58.5690, 112.5531, 61.5764},
    roof = {2521.8577, -264.7307, -24.1149, 4.7998},
    sewer = {2516.6213, -327.1884, -70.6539, 93.5412},
    penthouse = {969.4594, 63.1847, 112.5549, 237.0931},
}
```

### 🔓 Hack Configuration

Configure different minigames for each heist phase:

```lua
config.Hacks = {
    mainEntrance = {"glow-Spot", "glow-Spot", "glow-Spot"},
    roofEntrance = {"boii-SkillBar", "boii-SkillBar"},
    sewerEntrance = {"ox-SkillCircle", "ox-SkillCircle"},
    vault = {"boii-ButtonMash", "boii-ButtonMash"},
    security = {"SN-SkillBar", "SN-SkillBar"}
}
```

Each array represents the sequence of minigames players must complete for that entry method or objective.

### 💰 Loot Configuration

#### Loot Items

Define the rewards players can obtain:

```lua
config.LootItems = {
    money = {itemName = "money", count = math.random(1, 5)},
    gold = {itemName = "gold", count = math.random(1, 5)},
    diamonds = {itemName = "diamonds", count = math.random(1, 5)},
    artwork = {itemName = "bread", count = 1}, -- Example placeholder
}
```

#### Required Items

Items needed for different hack phases:

```lua
config.HackItems = {
    electricalTamper = "pliers",
    explosive = "thermal_charge",
    hackItemOne = "xtrojan",
    hackItemTwo = "xphone",
    hackItemThree = "xlaptop",
    hackItemFour = "flapperhero",
    hackItemFive = "decrypto",
    hackItemSix = "laptop_h",
    drillItem = "pliers",
    rappelEquipment = "rappel_equipment",
    penthouse = "casino_penthouse_key",
    vaultOne = "casino_vault_key_one",
    vaultTwo = "casino_vault_key_two",
    usbDevice = "casino_usbdevice",
    teargas = "weapon_teargas",
    bonusItemOne = "water", -- Bonus vault item
    bonusItemTwo = "water" -- Bonus vault item
}
```

### 💨 Tear Gas System

#### Affected Zone

Define the polygon area where tear gas affects players:

```lua
config.TearGasZonePoints = {
    vector3(2504.59, -233.50, -69.58),
    vector3(2504.76, -199.32, -69.58),
    vector3(2561.41, -247.36, -69.58),
    vector3(2516.50, -268.54, -69.58),
    vector3(2501.22, -262.36, -69.58),
    vector3(2500.62, -248.32, -69.58),
    vector3(2504.73, -243.58, -69.58)
}
```

#### Gas Spawn Locations

Specific coordinates where tear gas effects are created:

```lua
config.TearGasLocations = {
    {coords = vector3(2511.6406, -238.5636, -70.7372), radius = 5.0},
    {coords = vector3(2528.7166, -238.5137, -70.7372), radius = 8.0},
    -- Additional locations...
}
```

Each location includes coordinates and an effect radius.

### 👮 Security Guards

#### Penthouse Guard Positions

Configure guard spawn locations and headings:

```lua
config.PenthouseGuardLocations = {
    {coords = vector3(971.3420, 49.3578, 116.1642), heading = 309.9797},
    {coords = vector3(969.3802, 41.2354, 116.1642), heading = 46.9673},
    -- Additional guard positions...
}
```

Guards are divided into left side and right side formations for tactical placement.

### 🎯 Interactive Props

The heist features an extensive prop system for interactive elements like keycards, cash stacks, and hackable devices. Each prop includes:

* **Model**: 3D model hash or name
* **Location Type**: `"fixed"` or `"random"`
* **Interaction**: Custom functions, events, or server callbacks
* **Conditions**: Requirements for interaction availability
* **Zones**: Interaction areas and sizes

#### Key Prop Categories

1. **Keycards**: Various access cards found throughout the heist
2. **Loot Items**: Cash stacks, gold bars, and bonus items
3. **Security Devices**: Keycard scanners and access terminals
4. **Bonus Items**: Special rewards for thorough exploration

### 🔧 Prop Actions

The system supports multiple action types:

* `customFunction`: Execute Lua functions
* `triggerEvent`: Fire client events
* `triggerServerEvent`: Fire server events

Each action can include custom parameters and conditions for maximum flexibility.



This configuration system provides extensive customization options for creating the perfect casino heist experience tailored to your server's needs.
