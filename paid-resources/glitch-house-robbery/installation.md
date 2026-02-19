# Installation

## **Prerequisites**

Before installing this resource, ensure you have the required dependencies:

* **ox\_lib** - Core library for UI components, notifications, and utility functions
* **ox\_target** - Targeting system for interactive zones and entity interactions
* **oxmysql** - Database resource for player progression tracking
* **Shell Resource** - The following:
  * lynx\_shells - [https://github.com/Lynxist/lynx\_shells](https://github.com/Lynxist/lynx_shells)
  * K4MB1-StarterShells - [https://k4mb1maps.com/product/5015840](https://k4mb1maps.com/product/5015840)
* **Inventory System** - Compatible inventory resource (ox\_inventory)

## Installation Steps <a href="#installation-steps" id="installation-steps"></a>

#### 1. Download

Clone the repository to your local machine.

#### 2. Dependencies

Verify that all required dependencies listed in the prerequisites section are properly installed and running on your server prior to starting the script.

#### 3. Server Configuration

Add the resource to your `server.cfg` file:

```
start glitch-houserobbery
```

#### **4. Configuration**

Feel free to go through all the files inside of the **shared** folder and the **open\_source** files - these files are **not encrypted** and provide extensive customisation options:

**Shared Folder:**

* **config.lua** - Main configuration file containing:
  * Locale settings and debug mode toggles
  * XP system scaling and level progression
  * Starting locations and NPC configurations
  * Lockpicking mechanics and break chances
  * Noise alarm thresholds and level requirements
  * Tier unlock chances based on player level
  * Comprehensive loot tables with 6 reward tiers
  * Search timer settings and level-based reductions
  * Job notification delays and phone settings
* **apiKeys.lua** - Integration settings for:
  * Discord webhook URLs for logging systems

**Open Source Files:**

* **open\_source.lua** - Client-side integration functions:
  * Skill check/minigame system (supports ox\_lib and glitch-minigames)
  * Weather control for interior environments
  * Framework-specific client functions
* **open\_source.lua** - Server-side integration functions:
  * Player identification system
  * XP and level management
  * Phone notification integration (adapt for your phone resource if not using lb-phone)
  * Police alert system integration
  * Framework-specific server functions

#### **5.** Inventory Item Setup (Lockpick)

This resource requires a **lockpick item** to be added into your inventory system so players can begin breaking into houses.

`ox_inventory/data/items.lua`

```lua
['lockpick'] = {
    label = 'Lockpick',
    weight = 150,
    consume = 0,
    description = 'A general-purpose tool for gaining entry to locked areas or items',
    server = {
        export = 'glitch-houserobbery.useLockpick'
    }
},
```

* This item is required for the lockpicking mechanic to function.
* The server.export links directly into the house robbery system, allowing the lockpick to trigger the entry minigame.
* You can rename the item, change weight, or adjust the description if desired - just make sure the item name matches what’s used in the script config.
