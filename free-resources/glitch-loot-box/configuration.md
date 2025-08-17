# Configuration

Edit `shared/config.lua` to customise your loot box experience:

***

#### Basic Settings

```lua
config = {}

-- Debug mode for troubleshooting
config.debug = true

-- UI Mode (true = animated UI, false = classic notifications)
config.useUI = true
```

***

#### UI Configuration

```lua
config.ui = {
    -- Inventory system configuration - change this to match your inventory
    inventory = {
        system = 'ox', -- 'ox', 'qb', 'esx'
        iconPath = 'nui://ox_inventory/web/images/',
        iconExtension = '.png',
        fallbackIcon = 'nui://ox_inventory/web/images/placeholder.png'
    },
    
    -- Rarity colours for UI
    rarityColors = {
        common = '#b0c3d9',
        uncommon = '#5e98d9', 
        rare = '#4b69ff',
        ['very-rare'] = '#8847ff',
        epic = '#d32ce6',
        legendary = '#eb4b4b'
    }
}
```

***

#### Loot Table Configuration

Located in `shared/config.lua`:

```lua
config.lootBoxes = {
    ammocratet1 = {
        name = 'Ammo Crate T1',
        rewards = {
            { item = 'ammo-9', label = '9mm Ammo', min = 50, max = 150, rarity = 'common', chance = 40 },
            { item = 'ammo-50', label = '.50 Cal Ammo', min = 50, max = 150, rarity = 'uncommon', chance = 40 },
            { item = 'ammo-shotgun', label = 'Shotgun Shells', min = 15, max = 35, rarity = 'rare', chance = 20 }
        },
        bonusItems = { -- any items here have 100% chance to drop
            { item = 'money', amount = {min = 25, max = 100}, label = 'Cash Find' }
        }
    },
    
    -- Add your own loot boxes here...
}
```

***

#### Rarity Colours

Customise rarity colours in `shared/config.lua`:

```lua
config.ui.rarityColors = {
    common = '#b0c3d9',      -- Light Blue
    uncommon = '#5e98d9',    -- Blue  
    rare = '#4b69ff',        -- Royal Blue
    ['very-rare'] = '#8847ff', -- Purple
    epic = '#d32ce6',        -- Pink/Purple
    legendary = '#eb4b4b'    -- Red
}
```

***

#### Inventory System Settings

Configure your inventory system in `shared/config.lua`:

```lua
config.ui.inventory = {
    system = 'ox',  -- 'ox', 'qb', 'esx'
    iconPath = 'nui://ox_inventory/web/images/',
    iconExtension = '.png',
    fallbackIcon = 'nui://ox_inventory/web/images/placeholder.png'
}
```
