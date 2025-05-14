# Configuration

The following configuration options are available in shared/config.lua:

`config.DebugCommands (boolean):`\
Enable debug commands for testing purposes. Set to false for production.

`config.usingGlitchNotification (boolean):`\
Enable Glitch notification system integration.

***

## ⬆️ Exports

The following exports are available for use in your scripts:

### StartFirewallPulse

Starts the Firewall Pulse hacking minigame.

```lua
exports['glitch-minigames']:StartFirewallPulse(requiredHacks, initialSpeed, safeZoneSize, moveSpeed, timeLimit, progressMultiplier, dangerMultiplier)
```

Parameters:

| Parameter            | Default | Description                                                |
| -------------------- | ------- | ---------------------------------------------------------- |
| requiredHacks        | 3       | Number of successful hacks needed to complete the minigame |
| initialSpeed         | 2       | Starting speed of the pulse                                |
| maxSpeed             | 10      | Maximum speed the pulse can reach                          |
| timeLimit            | 10      | Time limit in seconds for each hack attempt                |
| safeZoneMinWidth     | 40      | Minimum width of the safe zone (in pixels)                 |
| safeZoneMaxWidth     | 120     | Starting width of the safe zone (in pixels)                |
| safeZoneShrinkAmount | 10      | How much the safe zone shrinks after each successful hack  |

***

### StartBackdoorSequence

Starts the Backdoor Sequence hacking minigame.

```lua
exports['glitch-minigames']:StartBackdoorSequence(requiredSequences, sequenceLength, timeLimit, maxAttempts, timePenalty, minKeys, maxKeys, possibleKeys, keyHintText)
```

Parameters:

| requiredSequences   | 3                             | Number of successful sequences needed to complete the minigame |
| ------------------- | ----------------------------- | -------------------------------------------------------------- |
| sequenceLength      | 5                             | Total number of keys in the sequence                           |
| timeLimit           | 15                            | Time limit in seconds for each sequence attempt                |
| maxAttempts         | 3                             | Maximum number of input mistakes allowed per sequence          |
| timePenalty         | 1.0                           | Time deducted (in seconds) when a wrong key is pressed         |
| minSimultaneousKeys | 1                             | Minimum number of keys shown at once for each stage            |
| maxSimultaneousKeys | 3                             | Maximum number of keys shown at once for each stage            |
| customKeys          | W,A,S,D,arrows,0-9            | Array of keys to use in sequences (e.g., {'W','A','S','D'})    |
| keyHintText         | "W, A, S, D, ←, →, ↑, ↓, 0-9" | Text displayed to hint available keys                          |

***

### StartCircuitRhythm

Starts the Circuit Rhythm hacking minigame.

```lua
exports['glitch-minigames']:StartCircuitRhythm(lanes, keys, noteSpeed, noteSpawnRate, requiredNotes, difficulty, maxWrongKeys, maxMissedNotes)
```

Parameters:

| Parameter      | Default            | Description                                                            |
| -------------- | ------------------ | ---------------------------------------------------------------------- |
| lanes          | 4                  | Number of lanes for notes to fall down                                 |
| keys           | \['A','S','D','F'] | Array of keys to use for each lane (must match number of lanes)        |
| noteSpeed      | 150                | Speed at which notes fall (higher = faster)                            |
| noteSpawnRate  | 1000               | Milliseconds between note spawns (lower = more frequent)               |
| requiredNotes  | 20                 | Number of notes player must hit to complete the minigame               |
| difficulty     | "normal"           | Difficulty level: "easy", "normal", or "hard" (affects timing windows) |
| maxWrongKeys   | 5                  | Maximum wrong key presses allowed before failure                       |
| maxMissedNotes | 3                  | Maximum notes that can be missed before failure                        |

***

### StartSurgeOverride

Starts the Surge Override hacking minigame.

```lua
exports['glitch-minigames']:StartSurgeOverride(possibleKeys, requiredPresses, decayRate, multiKeyMode, keyCombinations)
```

Parameters:

| Parameter       | Default                      | Description                                                                    |
| --------------- | ---------------------------- | ------------------------------------------------------------------------------ |
| possibleKeys    | \['E']                       | Array of possible keys for the game to randomly select from (single-key mode)  |
| requiredPresses | 50                           | Number of key presses needed to complete the minigame                          |
| decayRate       | 2                            | How quickly the progress bar depletes when not pressing keys (higher = faster) |
| multiKeyMode    | false                        | Enable multiple simultaneous key press mode                                    |
| keyCombinations | \[\['E','F'],\['SPACE','B']] | Array of key combinations for multi-key mode                                   |

***

### StartCircuitBreaker

Starts the Circuit Breaker hacking minigame.

```lua
exports['glitch-minigames']:StartCircuitBreaker(levelNumber, difficultyLevel...)
```

Parameters:

| Parameter            | Default              | Description                                                           |
| -------------------- | -------------------- | --------------------------------------------------------------------- |
| levelNumber          | random(1, 6)         | Circuit board layout (1-6)                                            |
| difficultyLevel      | 0 (Beginner)         | Difficulty level (0-3) affects cursor speed and disconnect chance     |
| delayStart           | 1000                 | Delay before minigame starts (ms)                                     |
| minFailureDelay      | 5000                 | Minimum delay for failure screen (ms)                                 |
| maxFailureDelay      | 5000                 | Maximum delay for failure screen (ms)                                 |
| disconnectChance     | 0 (for Beginner)     | Chance of random disconnects (0-1)                                    |
| disconnectChanceRate | 10000 (for Beginner) | Decimal between 0 and 1, chance of disconnection (0-0.9)              |
| minReconnectTime     | 3000                 | Minimum time in milliseconds to reconnect after disconnection (3000+) |
| maxReconnectTime     | 30000                | Maximum time in milliseconds to reconnect after disconnection         |

***

### StartDataCrack

Starts the Data Crack hacking minigame.

```lua
exports['glitch-minigames']:StartDataCrack(difficulty)
```

Parameters:

| Parameter  | Default | Description                                   |
| ---------- | ------- | --------------------------------------------- |
| difficulty | 3       | Difficulty level (1-5) affects movement speed |

***

### StartBruteForce

Starts the Brute Force hacking minigame.

```lua
exports['glitch-minigames']:StartBruteForce()
```

Returns:

| Parameter | Default | Description                                      |
| --------- | ------- | ------------------------------------------------ |
| numLives  | 5       | Number of attempts allowed before failure (1-10) |

***

### StartDrilling

Starts the Fleeca Bank drilling minigame.

```lua
exports['glitch-minigames']:StartDrilling()
```

Returns:

| Parameter          | Default | Description                                                                    |
| ------------------ | ------- | ------------------------------------------------------------------------------ |
| difficulty         | 1       | Difficulty level (1-3) affects temperature rise rate and optimal pressure zone |
| numLayers          | 3       | Number of material layers to drill through                                     |
| timeLimit          | 60      | Time limit in seconds (0 for no limit)                                         |
| drillBitDurability | 100     | Starting durability of drill bit (0-100)                                       |

***

### StartVarHack

Starts the VAR System hack minigame.

```lua
exports['glitch-minigames']:StartVarHack(blocks, speed)
```

Parameters:

| blocks | 5 | Number of blocks to memorize (1-10)               |
| ------ | - | ------------------------------------------------- |
| speed  | 5 | Time limit in seconds for completing the sequence |

***

### StartPlasmaDrilling

Starts the Plasma Drilling minigame.

```lua
exports['glitch-minigames']:StartPlasmaDrilling()
```

Returns:

| Parameter  | Default | Description                                                                       |
| ---------- | ------- | --------------------------------------------------------------------------------- |
| difficulty | 5       | Difficulty level (1-10) affects temperature rise rate and drill speed sensitivity |

***

## Testing Usage

```lua
RegisterCommand('testhack', function()
    local success = exports['glitch-minigames']:WriteHackNameHere()
    if success then
        print("Hack completed successfully!")
    else
        print("Hack failed!")
    end
end)
```

Any minigame that wasn't mentioned here does not have configuration and can only be performed one way. You can find how to use them in the [Examples ](../glitch-notifications/examples.md)section
