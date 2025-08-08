# Adding Locations

### Spawn Points & Maps

#### Map Configuration Structure

Each map follows this structure:

```lua
mapName = {
    menu = {
        menuId = 'map_selection_external', -- or 'map_selection_interior'
        title = 'Display Name',
        icon = 'fa-solid fa-icon-name',
        description = 'Brief tactical description',
        image = 'https://your-image-url.jpg',
    },
    
    recommendedSet = {
        SoldierRec = 16,    -- Recommended enemy count
        SoldierMax = 30,    -- Maximum enemy count
        hostageRec = 1,     -- Recommended hostage count  
        hostageMax = 10,    -- Maximum hostage count
    },
    
    vehicleSpawns = {
        {coords = vector4(x, y, z, heading), vehicle = 'vehicle_name'},
    },
    
    polyZone = {
        -- Defines the playable area boundary
        vector3(x, y, z),
        -- Add more points to define the polygon
    },
    
    playerSpawns = {
        vector4(x, y, z, heading), -- Player spawn points
    },
    
    guardCoords = {
        vector4(x, y, z, heading), -- Enemy spawn locations
    }
}
```

#### Adding New Maps

1. **Choose Category**: Decide if it's external or interior
2. **Set Menu Info**: Configure the menu display options
3. **Define Boundaries**: Create a polygon zone for the playable area
4. **Add Spawn Points**: Place player and enemy spawn coordinates
5. **Test Balance**: Adjust recommended enemy/hostage counts

#### Coordinate Tools

* Use `/coords` command (if available) to get current position
* Format: `vector4(x, y, z, heading)` for spawns
* Format: `vector3(x, y, z)` for polygon zones

***

### Interior Maps

Interior maps may include additional `mapData` configuration:

```lua
mapData = {
    get = function()
        return exports['bob74_ipl']:GetInteriorObject()
    end,
    setup = function(interior)
        -- Configure interior settings
        interior.Style.Set(interior.Style.modern)
    end
}
```

#### IPL Integration

Many interiors use the `bob74_ipl` resource for loading. Ensure it's installed and started before your training resource.

***

### Small Interiors

Small interiors are simpler configurations for quick training scenarios:

```lua
smallInteriorName = {
    spawnCoords = vector3(x, y, z), -- Single spawn point inside
    guardCoords = {
        vector4(x, y, z, heading), -- Enemy positions
    },
    mapData = {
        -- Optional IPL configuration
    }
}
```
