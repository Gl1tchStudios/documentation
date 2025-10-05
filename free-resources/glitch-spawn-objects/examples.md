---
description: >-
  Glitch Spawn Objects is a lightweight and efficient FiveM resource designed to
  spawn, synchronise, and persist world objects seamlessly across all players on
  the server.
---

# Examples

### Usage Examples

Spawning Objects

```lua
-- Basic object spawning
/spawnobject
```

Managing Synced Objects

```lua
-- View all synced objects in the area
/syncedobjects
```

### Client Exports

```lua
-- Standard get closest object
local closestObj, distance = exports['glitch-spawnobjects']:getClosestObject()

-- Get closest object to specific coordinates
local coords = vector3(100.0, 200.0, 30.0)
local closestObj, distance = exports['glitch-spawnobjects']:getClosestObject(coords)

-- Get closest object within 50 units of player
local closestObj, distance = exports['glitch-spawnobjects']:getClosestObject(nil, 50.0)

-- Get closest object within 25 units of specific coordinates  
local coords = vector3(100.0, 200.0, 30.0)
local closestObj, distance = exports['glitch-spawnobjects']:getClosestObject(coords, 25.0)

-- Check if an object was found
if closestObj then
    print('Found closest object:', closestObj.model, 'at distance:', distance)
    print('Object ID:', closestObj.id)
    print('Position:', closestObj.posX, closestObj.posY, closestObj.posZ)
else
    print('No objects found within range')
end
```

### Server Exports

<pre class="language-lua"><code class="lang-lua"><strong>-- Spawn object
</strong><strong>exports['glitch-spawnobjects']:createObject(source, "prop_bench_01a", {
</strong>    position = {x = 100.0, y = 200.0, z = 30.0},
    rotation = {x = 0.0, y = 0.0, z = 45.0}
}, "park")

-- Update a object
exports['glitch-spawnobjects']:updateObject(source, "prop_bench_01a", {
    position = {x = 150.0, y = 250.0, z = 30.0},
    rotation = {x = 0.0, y = 0.0, z = 90.0}
}, 123)

-- Delete a object
exports['glitch-spawnobjects']:deleteObject(source, 123)
</code></pre>
