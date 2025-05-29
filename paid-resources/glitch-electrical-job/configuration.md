# Configuration

## 🔧 Configuration Guide

The electrical job script offers extensive customization options through two main configuration files. This guide will walk you through each configuration option to help you set up the perfect electrical job experience for your server.

### 📁 Configuration Files

The configuration is split across two main files:

* **`config-main.lua`** - Core gameplay settings, payouts, and mechanics
* **`config-locations.lua`** - Location data for all mission types

### ⚙️ Main Configuration (`config-main.lua`)

#### Basic Settings

```lua
config.Car = "speedo"           -- Vehicle model for electrical work
config.Plate = "ELE "          -- License plate prefix for work vehicles
config.Debug = true            -- Enable/disable debug mode for testing
```

#### User Interface Options

```lua
config.UI = "GTAUI"                    -- UI type: "Notification" or "GTAUI"
config.HesitCompleteUI = false         -- Show heist completion UI
config.DrawTextAtLocations = true      -- Show interaction text at mission locations
```

#### Experience System Integration

```lua
config.usingPickleXP = true     -- Enable PickleXP system integration
config.hardsetLevelXP = 10      -- Manual level override (if not using PickleXP)
```

### 🎮 Minigame Configuration

The script supports multiple minigame types for different mission categories:

```lua
config.hacks = {
    bank = {
        { type = 'circuitBreaker'}  -- Requires glitch-minigames
    },
    store = {
        { type = 'buttonMash'}      -- Requires glitch-minigames
    },
    house = {
        { type = 'skillBar'}        -- Requires SN-Hacking
    },
    mlo = {
        { type = 'circuitBreaker'},
        { type = 'buttonMash'},
        { type = 'skillBar'}
    }
}
```

#### Supported Minigame Types

| Type             | Required Resource | Description              |
| ---------------- | ----------------- | ------------------------ |
| `circuitBreaker` | glitch-minigames  | Circuit breaker puzzle   |
| `buttonMash`     | glitch-minigames  | Button mashing challenge |
| `skillBar`       | SN-Hacking        | Skill bar timing game    |

#### Failure Penalties

```lua
config.failureReductAmount = math.random(500, 800)  -- Money deducted on minigame failure
config.hackFailureThreshold = 0                     -- Failure threshold percentage
```

### 💰 Payment & Bonus System

#### Time-Based Bonuses

```lua
config.bonusEnabled = true      -- Enable time completion bonuses
config.bonusRatio = 1.5        -- Bonus multiplier (1.5x base pay)

config.missionBaseTime = {     -- Time limits for bonus eligibility (seconds)
    bank = 60 * 4,            -- 4 minutes
    store = 60 * 4,
    house = 60 * 4,
    atm = 60 * 4,
    lightpoles = 60 * 4,
    mlo = 60 * 4
}
```

#### Level-Based Pay Scaling

The payment system scales with player level, offering higher rewards and faster completion times as players progress:

```lua
config.payLevels = {
    {
        minLevel = 0, maxLevel = 10,
        lightpoleRepairPay = {1000, 1250},
        atmMissionPay = {1000, 1250},
        bankMissionPay = {4200, 4900},
        houseMissionPay = {4200, 4900},
        storeMissionPay = {4200, 4900},
        mloMissionPay = {4300, 5000},
        TimeToFix = {8000, 11000}
    },
    -- Additional level ranges up to 50+
}
```

#### Payment Breakdown by Level

| Level Range | Light Pole    | ATM           | Bank/House/Store | MLO           | Repair Time (ms) |
| ----------- | ------------- | ------------- | ---------------- | ------------- | ---------------- |
| 0-10        | $1,000-$1,250 | $1,000-$1,250 | $4,200-$4,900    | $4,300-$5,000 | 8-11 seconds     |
| 10-20       | $1,250-$1,400 | $1,250-$1,400 | $4,900-$5,600    | $5,000-$5,700 | 7-9 seconds      |
| 20-30       | $1,400-$1,600 | $1,400-$1,600 | $5,600-$6,000    | $5,700-$6,100 | 6-8 seconds      |
| 30-40       | $1,600-$1,900 | $1,600-$1,900 | $6,000-$6,700    | $6,100-$6,800 | 5-7 seconds      |
| 40-50       | $1,900-$2,100 | $1,900-$2,100 | $6,700-$8,700    | $6,800-$8,800 | 4-6 seconds      |
| 50+         | $2,600        | $2,600        | $9,700           | $9,800        | 3-5 seconds      |

### 🎁 Special Events & Items

#### Special Events

```lua
config.specialEvents = true           -- Enable special event missions
config.specialEventPercentage = 15    -- 15% chance for special events
config.specialEventBonus = 50000     -- Extra $50,000 for special events
```

#### Risk & Reward

```lua
config.chanceToBeRobbed = true            -- Enable robbery encounters
config.chanceToBeRobbedPercentage = 5     -- 5% chance of being robbed
```

#### Bonus Items

```lua
config.bonusItems = true          -- Enable bonus item rewards
config.bonusItemChance = 35       -- 35% chance to receive bonus items

config.items = {
    {item = "copper", minLevel = 0},
    {item = "e_scrap", minLevel = 0},
    {item = "rubber", minLevel = 0},
    {item = "atmmotherboard", minLevel = 40}  -- High-level exclusive item
}
```

#### Item Reward Scaling

```lua
config.levelRewards = {
    {minLevel = 0, maxLevel = 10, minAmount = 1, maxAmount = 2},
    {minLevel = 10, maxLevel = 20, minAmount = 1, maxAmount = 3},
    {minLevel = 20, maxLevel = 30, minAmount = 2, maxAmount = 4},
    {minLevel = 30, maxLevel = 40, minAmount = 3, maxLevel = 4},
    {minLevel = 40, maxLevel = 50, minAmount = 4, maxAmount = 5},
    {minLevel = 50, maxLevel = math.huge, minAmount = 5, maxAmount = 5}
}
```

### 🏢 Location Configuration (`config-locations.lua`)

#### MLO Compatibility

```lua
config.usingGabzBanks = false    -- Enable Gabz Bank MLO support
config.usingGabzStores = false   -- Enable Gabz Store MLO support
```

#### Mission Location Types

The script supports various location types for different mission categories:

**Street Light Repair Posts**

```lua
config.Posts = {
    {
        prop = 'prop_streetlight_01',
        scenario = 'PROP_HUMAN_SEAT_BENCH',
        verticalOffset = -0.5,
        forwardOffset = 0.0,
        leftOffset = 0.0,
        angularOffset = 180.0
    }
    -- Additional light pole configurations
}
```

**ATM Locations**

Pre-configured ATM coordinates across the map:

```lua
config.atmProps = {
    vector3(-1205.9755, -324.9689, 37.8596),
    vector3(-1205.1788, -326.5736, 37.8574),
    -- 25+ additional ATM locations
}
```

**Bank Missions**

Bank locations with different coordinates for default GTA and Gabz MLO interiors:

```lua
config.bankData = {
    {
        title = "Legion",
        location = vector3(151.4436, -1035.0088, 29.3396),
        locationOne = vector3(145.7424, -1044.1407, 29.3778),
        locationTwo = vector3(146.8694, -1046.0580, 29.3681)
    }
    -- 6 total bank locations
}
```

**Store Missions**

Store locations with Gabz MLO support:

```lua
config.storeData = {
    {
        title = "Mirror Park",
        location = vector3(1159.6, -328.1, 69.0),
        locationOne = vector3(1159.8577, -315.1490, 69.2050),
        locationTwo = vector3(1161.9144, -314.3739, 71.3255)
    }
    -- 8 total store locations
}
```

**House Missions**

Residential electrical work locations:

```lua
config.houseData = {
    {
        title = "House 1",
        location = vector3(-351.3857, 475.7126, 112.8314),
        locationOne = vector3(-381.8230, 462.9610, 113.5191),
        locationTwo = vector3(-370.2748, 464.2496, 113.1691)
    }
    -- 21 total house locations
}
```

**MLO Interior Missions**

Complex interior locations including:

* **FIB HQ** - High-security government building
* **Luxury Apartments** - High-end residential properties
* **Business Centers** - Corporate office buildings
* **Nightclubs** - Entertainment venues
* **Vehicle Warehouses** - Commercial properties
* **Casino Penthouses** - Premium locations
* And More!

```lua
config.mloData = {
    {
        title = "FIB HQ",
        location = vector3(141.1393, -765.5107, 45.7520),
        locationTwo = vector3(138.1929, -764.6608, 242.1456),
        mloOne = vector3(119.5360, -724.8893, 242.9142),
        mloTwo = vector3(125.0617, -726.8911, 242.1496)
    }
    -- 30+ total MLO locations
}
```

#### Special Event Locations

```lua
config.mloSpecialEvent = {vector3(149.9800, -759.8262, 242.1518)}
config.mloSpecialEventTwo = {vector3(-64.3865, -2522.1533, 6.0100)}
config.mloSpecialEventThree = {vector3(-57.1349, -2520.8381, 7.4012)}
```

### 🔧 Level Lock for MLO Jobs

#### Level Restrictions

```lua
config.levelLock = 10  -- Minimum level required to access electrical jobs
```
