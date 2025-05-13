# Examples

Below are quick usage examples for how to use Glitch Security Cameras:

You must ensure you do not use the same id twice for any given camera, but you also do not have to go in order thus you could make cameras like 1, 2, 3, 80...

### Adding a New Camera using the Config

```lua
config.Cameras = {
    {
        id = 1,                                                     -- Unique ID for the camera
        name = "Security Staff Facilities",                         -- Camera name
        location = "Diamond Casino & Resort",                       -- Location of the camera
        modes = { -- both set to true by default
            nightVision = true,
            thermal = false
        },
        position = vector3(2530.2432, -265.8049, -56.6363),         -- Camera position
        rotation = vector3(-15.0, 0.0, 229.2701),                       -- Camera rotation
        rotationLimits = {
            x = {min = -75.0, max = -5},                            -- Vertical limits
            z = {min = 175, max = 265}                               -- Horizontal limits
        },
        interactiveProps = {
            -- Example using an export for the minigame
            {
                propUniqueId = "door1",                             -- Unique ID for the prop
                position = vector3(2530.8559, -273.8801, -58.5731), -- Prop position
                hash = 1243560448,                                  -- Hash of the prop model
                interactionText = "Disable the Door Locks",         -- Text displayed when interacting with the prop
                successText = "Security system bypassed",           -- Text displayed on success
                failText = "Security alert triggered",              -- Text displayed on failure
                highlightColor = {r = 255, g = 165, b = 0, a = 200},-- Color of the highlight

                hackExport = "glitch-minigames:StartSurgeOverride", -- Export to call for hack minigame
                hackParams = {                                      -- Parameters for the hack minigame
                    keys = {'E', 'F'},
                    requiredPresses = 30,
                    decayRate = 2
                },
            }
        }
    },
}
```

### Adding a New Camera using an Export

```lua
local newCamera = {
        id = 2,                                                     -- Unique ID for the camera
        name = "Security Entrance",                                 -- Camera name
        location = "Diamond Casino & Resort",                       -- Location of the camera
        modes = { -- both set to true by default
            nightVision = true,
            thermal = true
        },
        position = vector3(2519.4429, -252.3573, -53.3036),         -- Camera position
        rotation = vector3(-10.0, 0.0, 25.0),                       -- Camera rotation
        rotationLimits = {
            x = {min = -75.0, max = -5},                            -- Vertical limits
            z = {min = 89, max = 175.0}                             -- Horizontal limits
        },
        interactiveProps = {
            -- Example using an export for the minigame
            {
                propUniqueId = "security_mainframe",                -- Unique ID for the prop
                position = vector3(2509.0986, -260.3841, -54.0064), -- Prop position
                hash = -1498975473,                                 -- Hash of the prop model
                interactionText = "Disable the Door Locks",         -- Text displayed when interacting with the prop
                successText = "Security system bypassed",           -- Text displayed on success
                failText = "Security alert triggered",              -- Text displayed on failure
                highlightColor = {r = 0, g = 255, b = 0, a = 200},  -- Color of the highlight
                
                hackExport = "glitch-minigames:StartSurgeOverride", -- Export to call for hack minigame
                hackParams = {                                      -- Parameters for the hack minigame
                    keys = {'E', 'F'},
                    requiredPresses = 30,
                    decayRate = 2
            },
        }
    }
}
-- Add the camera to the security system
exports['glitch-securityCameras']:AddCamera(newCamera)
```

### Attempting to Hack a Camera using an Export

```lua
-- Attempt to hack a specific camera and prop
local success = exports['glitch-securityCameras']:AttemptCameraHack(1, "security_mainframe", {1})
if success then
    -- Execute code after successful hack (e.g., unlock doors)
    TriggerServerEvent('glitch-casinoHeist:server:setdoor', 8, 0)
end
```

#### Parameter Explanation for AttemptCameraHack:

1. **First parameter**: The camera ID of the first camera you want to show when going into the cameras
2. **Second parameter**: The unique ID of the interactive prop you're hacking
3. **Third parameter**: Optional but you can do a table of all the camera IDs you want the player to be able to access&#x20;

The function returns `true` if the hack is successful or `false` if it fails, allowing for conditional actions based on the result.

For more information on the AttemptCameraHack check [here](configuration.md#attemptcamerahack-cameraindex-propid-allowedcameras)
