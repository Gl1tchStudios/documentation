# Installation

## Installation Guide

### Prerequisites

Before installing this resource, ensure you have the required dependencies:

* **Glitch Abstraction** - Essential framework handler that enables compatibility across different FiveM frameworks
  * [Download Glitch Abstraction](../glitch-abstraction/)
* **Glitch Minigames** - Required for loot box functionality
  * [Download Glitch Loot Box](https://github.com/Gl1tchStudios/glitch-lootBox)

> **Important:** Glitch Abstraction is a critical dependency that manages framework compatibility, allowing our resources to seamlessly integrate with your existing server setup.

### Installation Steps

#### 1. Repository Setup

Clone the repository to your local machine and locate the `glitch-lootBox` folder.

#### 2. File Placement

Move the `glitch-lootBox` folder into your FiveM server's resources directory:

```
/resources/glitch-lootBox/
```

#### 3. Server Configuration

Add the resource to your `server.cfg` file:

```cfg
start glitch-lootBox
```

#### 4. Adding Items

You do not have to do this as you can create any item into a loot box by just adding it to the config but for some pre created ones&#x20;



Example SQL for adding ammo crate items to your database

```sql
-- For ESX (items table)
INSERT INTO `items` (`name`, `label`, `weight`, `rare`, `can_remove`) VALUES
('ammocratet1', 'Tier 1 Ammo Crate', 5, 0, 1),
('ammocratet2', 'Tier 2 Ammo Crate', 8, 0, 1),
('ammocratet3', 'Tier 3 Ammo Crate', 12, 0, 1),
('civilianbox', 'Civilian Ammo Box', 3, 0, 1),
('holidaycrate', 'Holiday Special Crate', 20, 0, 1);
```

For QBCore (qb-core/shared/items.lua) or for OX inventory add these into (ox\_inventory/data/items.lua)

```lua
-- Add these to your items.lua file:

['ammocratet1'] = {
    ['name'] = 'ammocratet1',
    ['label'] = 'Tier 1 Ammo Crate',
    ['weight'] = 5000,
    ['type'] = 'item',
    ['image'] = 'ammocratet1.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'A basic ammo supply crate containing various ammunition types.'
},
['ammocratet2'] = {
    ['name'] = 'ammocratet2',
    ['label'] = 'Tier 2 Ammo Crate',
    ['weight'] = 8000,
    ['type'] = 'item',
    ['image'] = 'ammocratet2.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'An advanced ammo supply crate with guaranteed shotgun shells and chance for pistol or rifle ammo.'
},
['ammocratet3'] = {
    ['name'] = 'ammocratet3',
    ['label'] = 'Tier 3 Ammo Crate',
    ['weight'] = 12000,
    ['type'] = 'item',
    ['image'] = 'ammocratet3.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'A premium ammo supply crate guaranteed to contain rifle ammunition with bonus pistol ammo chance.'
},
['civilianbox'] = {
    ['name'] = 'civilianbox',
    ['label'] = 'Civilian Ammo Box',
    ['weight'] = 3000,
    ['type'] = 'item',
    ['image'] = 'civilianbox.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'Basic civilian ammunition box with limited supplies.'
},
['holidaycrate'] = {
    ['name'] = 'holidaycrate',
    ['label'] = 'Holiday Special Crate',
    ['weight'] = 20000,
    ['type'] = 'item',
    ['image'] = 'holidaycrate.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'Limited time holiday ammunition crate containing massive amounts of all ammo types.'
}
```

#### 4. Permissions Verification

Ensure your server has the necessary permissions to execute the script and all its components.

### Final Notes

Once installation is complete, restart your server to activate the loot box system. The resource will automatically integrate with your existing framework through Glitch Abstraction.
