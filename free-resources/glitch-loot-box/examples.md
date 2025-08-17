# Examples

### 📚 Examples

#### Example 1: Adding Custom Loot Boxes

```lua
-- In shared/config.lua, add to config.lootBoxes:
config.lootBoxes.weaponbox = {
    name = 'Weapon Box',
    rewards = {
        { item = 'weapon_pistol', label = 'Pistol', min = 1, max = 1, rarity = 'rare', chance = 30 },
        { item = 'weapon_knife', label = 'Knife', min = 1, max = 1, rarity = 'uncommon', chance = 50 },
        { item = 'weapon_bat', label = 'Baseball Bat', min = 1, max = 1, rarity = 'common', chance = 20 }
    },
    bonusItems = {
        { item = 'money', amount = {min = 100, max = 500}, label = 'Bonus Cash' }
    }
}
```

***

#### Example 2: Adding Custom Items to Existing Boxes

```lua
-- In shared/config.lua, modify existing loot box:
config.lootBoxes.ammocratet1.rewards = {
    { item = 'ammo-9', label = '9mm Ammo', min = 50, max = 150, rarity = 'common', chance = 30 },
    { item = 'ammo-50', label = '.50 Cal Ammo', min = 50, max = 150, rarity = 'uncommon', chance = 30 },
    { item = 'ammo-shotgun', label = 'Shotgun Shells', min = 15, max = 35, rarity = 'rare', chance = 20 },
    -- Add your new item here
    { item = 'explosive_ammo', label = 'Explosive Rounds', min = 5, max = 15, rarity = 'legendary', chance = 20 }
}
```

***

#### Example 3: Custom Inventory System Integration

```lua
-- In shared/config.lua, configure for different inventory systems:

-- For QB-Core
config.ui.inventory = {
    system = 'qb',
    iconPath = 'nui://qb-inventory/html/images/',
    iconExtension = '.png',
    fallbackIcon = 'nui://qb-inventory/html/images/placeholder.png'
}

-- For ESX
config.ui.inventory = {
    system = 'esx',
    iconPath = 'nui://esx_inventory/html/img/items/',
    iconExtension = '.png',
    fallbackIcon = 'nui://esx_inventory/html/img/items/placeholder.png'
}

-- For ox_inventory
config.ui.inventory = {
    system = 'ox',
    iconPath = 'nui://ox_inventory/web/images/',
    iconExtension = '.png',
    fallbackIcon = 'nui://ox_inventory/web/images/placeholder.png'
}
```

***

#### Example 4: Custom Rarity Tiers

```lua
-- In shared/config.lua, add custom rarity colours:
config.ui.rarityColors = {
    common = '#b0c3d9',      -- Light Blue
    uncommon = '#5e98d9',    -- Blue  
    rare = '#4b69ff',        -- Royal Blue
    ['very-rare'] = '#8847ff', -- Purple
    epic = '#d32ce6',        -- Pink
    legendary = '#eb4b4b',   -- Red
    mythic = '#ff0000',      -- Bright Red (custom tier)
    ['god-tier'] = '#ffd700' -- Gold (custom tier)
}
```
