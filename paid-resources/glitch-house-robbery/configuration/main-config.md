# Main Config

```lua
Config = {}

Config.Locale = 'en' -- Set the locale for the resource
Config.Debug = false -- Enable debug mode

Config.RobberyXP = { -- Independent Robbery XP system configuration
    xpStart = 75, -- Base XP required for first level
    xpFactor = 0.15, -- XP scaling factor per level
    maxLevel = 75, -- Maximum achievable level
}

Config.StartPoints = { -- Starting points for the robbery
    {pedCoords = vector3(-523.8732, -1635.5927, 17.0352), pedHeading = 59.4313, pedModel = 'hc_gunman', pedScenario = 'WORLD_HUMAN_LEANING'},
}

Config.PhoneMessageContact = "⭐ Robert" -- Contact name for phone messages

Config.JobNotificationDelay = { -- Job notification delay configuration
    min = 60000,  -- Minimum delay in milliseconds (1 minute)
    max = 240000  -- Maximum delay in milliseconds (4 minutes)
}

Config.SearchTimer = { -- Search timer configuration
    baseTime = 11000, -- Base search time in milliseconds
    levelReductions = { -- Time reduction based on level
        {minLevel = 10, maxLevel = 19, reduction = 1000},
        {minLevel = 20, maxLevel = 29, reduction = 2000},
        {minLevel = 30, maxLevel = 40, reduction = 3000},
        {minLevel = 41, maxLevel = nil, reduction = 4000}
    }
}

Config.LockPicking = { -- Lock picking configuration
    lockpickBreakChance = 70, -- Chance to break lockpick on success (0-100)
    itemName = "lockpick", -- Name of the lockpick item
    shouldAlertOnFail = true, -- Alert police on failed lockpick attempt
}

Config.NoiseAlarm = { -- Noise alarm configuration (when player makes too much noise inside house)
    levelThreshold = 50, -- Minimum level required to avoid alarm when making noise (set to false to always trigger alarm regardless of level)
    enabled = true, -- Set to false to disable noise-based alarms entirely
    noiseThreshold = 6, -- Noise level that triggers alarm (higher = louder)
}

Config.TierChances = { -- Chances for each tier based on player level
    {minLevel = 0,  maxLevel = 24,  chances = {100, 0, 0, 0}},  -- 100% Tier 1
    {minLevel = 25, maxLevel = 34,  chances = {20, 80, 0, 0}},  -- 20% T1, 80% T2
    {minLevel = 35, maxLevel = 49,  chances = {10, 30, 60, 0}}, -- 10% T1, 30% T2, 60% T3
    {minLevel = 50, maxLevel = nil, chances = {5, 10, 35, 50}}, -- 5% T1, 10% T2, 35% T3, 50% T4
}

Config.Rewards = { -- Reward configuration for house robbery loot
    levelScalingFactor = 1.1, -- How much weight increases per level above requirement
    multipleItemsPerSearch = true, -- Set to true to allow multiple items from a single search
    itemsPerSearch = { min = 1, max = 4 }, -- Number of different items to give per search (only if multipleItemsPerSearch is true)
    
    lootTiers = { -- Config each tier with its own items, XP range, amount range, and weight
        { -- Tier 1: Nothing found
            type = "water",
            weight = 100,
            levelRequirement = 0,
        },
        { -- Tier 2: Common items
            items = {  "bread"},
            xp = { min = 1, max = 8 },
            amount = { min = 1, max = 8 },
            weight = 653,
            levelRequirement = 0,
        },
        { -- Tier 3: Uncommon items
            items = { "lockpick", "ring"},
            xp = { min = 8, max = 16 },
            amount = { min = 1, max = 5 },
            weight = 195,
            levelRequirement = 10,
        },
        { -- Tier 4: Rare items
           items = { "gold"},
            xp = { min = 16, max = 32 },
            amount = { min = 1, max = 3 },
            weight = 140,
            levelRequirement = 15,
        },
        { -- Tier 5: Very rare items
            items = { "gold_bar", "sports_memorabilia"},
            xp = { min = 16, max = 32 },
            amount = { min = 1, max = 2 },
            weight = 4,
            levelRequirement = 20,
        },
        { -- Tier 6: Legendary items
            items = {  "book", "phone"},
            xp = { min = 100, max = 100 },
            amount = { min = 1, max = 2 },
            weight = 1,
            levelRequirement = 20,
        },
    }
}

Config.Tiers = {
    [1] = { -- Tier 1
        shellModel = "modernhotel_shell",
        lootZones = {
            { -- Side Table (Entry)
                offset = vector3(5.723999, 0.019287, -0.822818),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 271.892822,
            },
            { -- Wardrobe (Right)
                offset = vector3(2.997864, -3.723877, -0.822818),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 179.558594,
            },
            { -- Wardrobe (Left)
                offset = vector3(-3.012817, -3.652832, -0.822818),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 184.483353,
            },
            { -- Bedside Table (Left)
                offset = vector3(-5.448608, -1.424072, -0.822818),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 90.480133,
            },
            { -- Side Table (Bed Side)
                offset = vector3(-4.167786, 3.633789, -0.822818),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 5.738424,
            },
            { -- Bedside Table (Right)
                offset = vector3(-5.540283, 1.697754, -0.822818),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 95.346771,
            },
        },
        leaveZone = {
            offset = vector3(4.967224, 4.187256, -0.822819),
            size = vec3(1.0, 1.0, 10.0),
            rotation = 4.326821,
        },
    },
    [2] = { -- Tier 2
        shellModel = "furnitured_midapart",
        lootZones = {
            { -- Entry Side Table
                offset = vector3(4.184875, -5.083740, -0.499468),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 181.667953,
            },
            { -- Entry Side Table 2
                offset = vector3(0.974365, 1.306152, -0.495447),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 92.775414,
            },
            { -- Bedroom Box
                offset = vector3(6.853333, 3.910156, -0.498444),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 271.189941,
            },
            { -- Bedroom Wardrobe
                offset = vector3(5.975037, 9.372559, -0.496044),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 357.978271,
            },
            { -- Bedroom Sink
                offset = vector3(2.215942, 8.757324, -0.493817),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 86.976715,
            },
            { -- Living Room Shevlves
                offset = vector3(0.229248, 9.385986, -0.492334),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 269.535767,
            },
            { -- TV Stand
                offset = vector3(-7.030701, 4.504395, -0.489135),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 88.231430,
            },
            { -- Fridge
                offset = vector3(-1.051147, 1.705322, -0.493992),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 268.487122,
            },
            { -- Dining Room Shevlves
                offset = vector3(-4.323914, -0.677246, -0.492655),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 189.955750,
            },
            { -- Bedside Table
                offset = vector3(4.178711, 7.867920, -0.495373),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 94.659798,
            },
        },
        leaveZone = {
            offset = vector3(1.418884, -10.189453, 1.000033),
            size = vec3(1.0, 1.0, 10.0),
            rotation = 2.629680,
        },
    },
    [3] = { -- Tier 3
        shellModel = "t2_furn_shell",
        lootZones = {
            { -- Living Room Side Table
                offset = vector3(1.307617, -7.975830, 1.000035),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 89.652725,
            },
            { -- Living Room TV
                offset = vector3(7.239502, -9.063232, 1.000035),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 179.742203,
            },
            { -- Kitchen Fridge
                offset = vector3(5.876526, 0.949707, 1.000035),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 347.700653,
            },
            { -- Kitchen Cabinets
                offset = vector3(8.530701, 0.873291, 1.000035),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 359.696503,
            },
            { -- Bedroom Wardrobe
                offset = vector3(-3.090942, -6.592285, 1.000035),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 140.110916,
            },
            { -- Bedroom Cest of Drawers
                offset = vector3(-0.606384, -4.055908, 1.000036),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 271.772583,
            },
            { -- Bedroom Bed
                offset = vector3(-3.663696, -3.380371, 1.000033),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 184.513275,
            },
            { -- Living Room TV 2
                offset = vector3(3.830139, -9.090088, 1.000041),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 184.369553,
            },
            { -- Entry Side Table
                offset = vector3(3.272827, -2.298096, 1.000041),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 358.416718,
            },
            { -- Kitchen Counter 2
                offset = vector3(5.757080, -1.748291, 1.000041),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 358.958893,
            },
            { -- Couch
                offset = vector3(7.085266, -5.230957, 1.000041),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 10.170958,
            },
            { -- Couch 2
                offset = vector3(4.921936, -7.537842, 1.000031),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 92.976746,
            },
        },
        leaveZone = {
            offset = vector3(1.439026, 0.868652, 1.000033),
            size = vec3(1.0, 1.0, 10.0),
            rotation = 183.437042,
        },
    },
    [4] = { -- Tier 4
        shellModel = "t3_furn_shell",
        lootZones = {
            { -- Kitchen Fridge
                offset = vector3(1.910217, -2.228760, 1.000113),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 183.667496,
            },
            { -- Kitchen Cabinets
                offset = vector3(2.324158, -0.998047, 1.000113),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 6.590929,
            },
            { -- Kitchen Cabients 2
                offset = vector3(5.474792, -0.939453, 1.000114),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 359.461609,
            },
            { -- TV Stand
                offset = vector3(0.009277, -9.658691, 1.000113),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 90.417740,
            },
            { -- Couch
                offset = vector3(5.445312, -8.472656, 1.000119),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 317.254791,
            },
            { -- Bedside Table (Left)
                offset = vector3(-5.804138, -10.863525, 1.000113),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 89.727592,
            },
            { -- Bedside Table (Right)
                offset = vector3(-5.802856, -7.181641, 1.000113),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 94.879051,
            },
            { -- Bedroom TV
                offset = vector3(-2.060547, -8.997803, 1.000111),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 273.466431,
            },
            { -- Bedroom Wardrobe (Left)
                offset = vector3(-4.795105, -4.589355, 1.000122),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 86.411850,
            },
            { -- Bedroom Wardrobe (Right)
                offset = vector3(-3.233521, -4.597168, 1.000122),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 274.574310,
            },
            { -- Bathroom Skin Cabinet
                offset = vector3(-3.515747, 0.025391, 1.000122),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 351.089172,
            },
            { -- Entry Way Shelf
                offset = vector3(-0.948853, -4.549561, 1.000120),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 89.700035,
            },
            { -- Couch 2
                offset = vector3(5.446777, -10.800781, 1.000113),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 273.294434,
            },
            { -- Living Room Table
                offset = vector3(1.471802, -9.748535, 1.000113),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 269.774719,
            },
            { -- Bedroom Wardrobe (Left) 2
                offset = vector3(-4.694702, -3.310791, 1.000122),
                size = vec3(1.0, 1.0, 10.0),
                rotation = 90.861664,
            },
        },
        leaveZone = {
            offset = vector3(-0.002441, 0.714844, 1.000113),
            size = vec3(1.0, 1.0, 10.0),
            rotation = 179.342880,
        },
    }
}

Config.Houses = { -- House locations for the robbery
    { houseloc = vector3(2618.248047, 3275.336670, 55.738152) },
    { houseloc = vector3(2634.322754, 3292.091064, 55.728233) },
    { houseloc = vector3(2632.355957, 3257.825439, 55.463356) },
    { houseloc = vector3(2318.759766, 2553.687500, 47.690487) },
    { houseloc = vector3(2352.329834, 2523.429443, 47.689392) },
    { houseloc = vector3(2357.779297, 2609.483398, 47.243305) },
    { houseloc = vector3(1436.294800, 3639.115723, 34.946220) },
    { houseloc = vector3(1435.748413, 3657.129639, 34.351387) },
    { houseloc = vector3(1859.397339, 3865.141846, 33.057632) },
    { houseloc = vector3(1894.342041, 3896.046143, 33.187836) },
    { houseloc = vector3(1936.522339, 3891.642822, 32.965813) },
    { houseloc = vector3(2418.523682, 4020.444824, 36.834049) },
    { houseloc = vector3(1142.220703, 2654.751953, 38.151714) },
    { houseloc = vector3(1121.625366, 2641.687256, 38.144852) },
    { houseloc = vector3(983.816772, 2718.790771, 39.503479) },
    { houseloc = vector3(980.541138, 2666.111084, 40.022621) },
    { houseloc = vector3(471.184509, 2607.481201, 44.477196) },
    { houseloc = vector3(379.879242, 2629.337402, 44.672455) },
    { houseloc = vector3(341.661987, 2615.232910, 44.671921) },
    { houseloc = vector3(241.831512, 3107.669189, 42.502510) },
    { houseloc = vector3(191.165497, 3081.989014, 43.472851) },
    { houseloc = vector3(194.888214, 3030.766602, 43.894962) },
    { houseloc = vector3(1719.039307, 4677.290039, 43.655785) },
    { houseloc = vector3(1682.872314, 4689.614258, 43.065971) },
    { houseloc = vector3(1664.070435, 4739.354004, 42.011360) },
    { houseloc = vector3(2221.972656, 5614.630859, 54.901646) },
    { houseloc = vector3(1207.351196, -620.296875, 66.438622) },
    { houseloc = vector3(1221.334106, -669.317688, 63.588886) },
    { houseloc = vector3(1250.886719, -515.526550, 69.349060) },
    { houseloc = vector3(1259.645142, -480.253845, 70.188789) },
    { houseloc = vector3(1046.081787, -498.097717, 64.281288) },
    { houseloc = vector3(1090.387207, -484.532349, 65.660461) },
    { houseloc = vector3(930.648865, -245.114456, 69.003006) },
    { houseloc = vector3(840.705261, -182.381714, 74.585556) },
    { houseloc = vector3(-1753.225464, -724.062500, 10.412036) },
    { houseloc = vector3(-1813.751221, -664.009216, 10.977730) },
    { houseloc = vector3(-1826.880249, -651.780151, 14.568566) },
    { houseloc = vector3(-1836.532471, -631.734863, 10.751719) },
    { houseloc = vector3(-1845.958130, -634.023315, 11.160978) },
    { houseloc = vector3(-1880.673584, -606.852783, 12.026731) },
    { houseloc = vector3(-1901.381592, -586.218628, 11.872354) },
    { houseloc = vector3(1385.116455, 3659.419678, 34.924561) },
    { houseloc = vector3(-1975.679932, -524.943787, 18.924364) },
    { houseloc = vector3(-1084.578491, -1559.333374, 4.781219) },
    { houseloc = vector3(-2992.975586, 707.570435, 28.689945) },
    { houseloc = vector3(1214.688110, -1644.344116, 48.645992) },
    { houseloc = vector3(1245.353394, -1627.007324, 53.278961) },
    { houseloc = vector3(1286.592529, -1604.510376, 54.824879) },
    { houseloc = vector3(1230.731934, -1590.773926, 53.766270) },
    { houseloc = vector3(1286.420654, -1604.558350, 54.824886) },
    { houseloc = vector3(1327.490112, -1553.162720, 54.050659) },
    { houseloc = vector3(1338.128784, -1524.220459, 54.587696) },
    { houseloc = vector3(1315.632202, -1526.534180, 51.806492) },
    { houseloc = vector3(1360.478149, -1556.387573, 56.342735) },
    { houseloc = vector3(919.973206, -569.508850, 58.366367) },
    { houseloc = vector3(976.893188, -580.505066, 59.850037) },
    { houseloc = vector3(987.923828, -525.714417, 60.691013) },
    { houseloc = vector3(1056.046631, -448.921692, 66.257576) },
    { houseloc = vector3(-1076.897339, -1553.968384, 4.630700) },
    { houseloc = vector3(-1065.942627, -1545.837524, 4.902400) },
    { houseloc = vector3(-1058.513184, -1657.390625, 4.672600) },
    { houseloc = vector3(-1059.740601, -1658.515625, 4.673200) },
    { houseloc = vector3(-1077.164429, -1620.997681, 4.474400) },
    { houseloc = vector3(-1078.744507, -1616.402710, 4.429300) },
    { houseloc = vector3(-1093.616089, -1608.145630, 8.458800) },
    { houseloc = vector3(-1105.647827, -1596.939331, 4.613300) },
    { houseloc = vector3(-1114.849243, -1577.735962, 4.543100) },
    { houseloc = vector3(844.080627, -562.637085, 57.992599) },
    { houseloc = vector3(861.717285, -583.645203, 58.156502) },
    { houseloc = vector3(886.773621, -608.202209, 58.430054) },
    { houseloc = vector3(902.980225, -615.441772, 58.446899) },
    { houseloc = vector3(928.813171, -639.850525, 58.227783) },
    { houseloc = vector3(980.254944, -627.613159, 59.221924) },
    { houseloc = vector3(996.936279, -729.692322, 57.806641) },
    { houseloc = vector3(979.173645, -716.241760, 58.210938) },
    { houseloc = vector3(1381.898926, -1544.676880, 57.098877) },
    { houseloc = vector3(1379.169189, -1514.901123, 58.430054) },
    { houseloc = vector3(1261.556030, -1616.782471, 54.739990) },
    { houseloc = vector3(1193.643921, -1656.487915, 43.012451) },
    { houseloc = vector3(-2.070324, -1442.070312, 30.947998) },
    { houseloc = vector3(-32.320877, -1446.382446, 31.874756) },
    { houseloc = vector3(-45.441757, -1445.419800, 32.413940) },
    { houseloc = vector3(-64.523071, -1449.534058, 32.515015) },
    { houseloc = vector3(-34.153847, -1847.103271, 26.179443) },
    { houseloc = vector3(-20.505493, -1858.984619, 25.404419) },
    { houseloc = vector3(21.323078, -1844.755981, 24.595581) },
    { houseloc = vector3(30.026377, -1854.619751, 24.056396) },
    { houseloc = vector3(45.956047, -1864.127441, 23.264526) },
    { houseloc = vector3(38.914288, -1911.586792, 21.950195) },
    { houseloc = vector3(56.624176, -1922.835205, 21.899658) },
    { houseloc = vector3(101.103302, -1912.219727, 21.394165) },
    { houseloc = vector3(85.938461, -1959.758301, 21.107666) },
    { houseloc = vector3(126.764839, -1929.982422, 21.377319) },
    { houseloc = vector3(-640.971436, 520.536255, 109.872559) },
    { houseloc = vector3(-667.252747, 471.441772, 114.135498) },
    { houseloc = vector3(-721.701111, 490.483521, 109.619751) },
    { houseloc = vector3(-762.026367, 430.799988, 100.183838) },
    { houseloc = vector3(-824.637329, 422.004395, 92.112793) },
    { houseloc = vector3(-339.626373, 625.516479, 171.340698) },
    { houseloc = vector3(-307.556030, 643.476929, 176.125977) },
    { houseloc = vector3(-232.707687, 588.158264, 190.532593) },
    { houseloc = vector3(-189.375824, 618.356018, 199.648315) },
    { houseloc = vector3(-185.248352, 591.151672, 197.811768) },
    { houseloc = vector3(-126.487907, 588.276917, 204.703247) },
    { houseloc = vector3(-305.129669, 431.050537, 110.479126) },
    { houseloc = vector3(-401.208801, 427.595612, 112.400024) },
    { houseloc = vector3(-450.923065, 395.472534, 104.767090) },
    { houseloc = vector3(-564.382446, 684.804382, 146.621948) },
    { houseloc = vector3(-606.237366, 672.250549, 151.592651) },
    { houseloc = vector3(2320.364746, 2535.903320, 47.696655) },
    { houseloc = vector3(2336.070312, 2566.496826, 47.713501) },
    { houseloc = vector3(2355.942871, 2564.439453, 47.090088) },
    { houseloc = vector3(1803.454956, 3913.912109, 37.047607) },
    { houseloc = vector3(1781.578003, 3911.208740, 34.907715) },

}
```
