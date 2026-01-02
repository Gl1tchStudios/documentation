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

{% hint style="info" %}
All Minigames below here are apart of the Glitch Minigames v2 Update
{% endhint %}

### StartMemoryGame

Starts the Memory minigame.

```lua
exports['glitch-minigames']:StartMemoryGame()
```

Returns:

| Parameter       | Default | Description                                                |
| --------------- | ------- | ---------------------------------------------------------- |
| gridSize        | 5       | Will set the minigame to use a 5x5 grid.                   |
| numOfSquares    | 8       | Number of squares to show                                  |
| numOfRounds     | 3       | Number of rounds                                           |
| showTime        | 3000    | Will show the squares for 3 seconds before they are hidden |
| maxWrongPresses | 3       | Max wrong presses allowed                                  |

***

### StartSequenceMemoryGame

Starts the Sequence Memory minigame.

```lua
exports['glitch-minigames']:StartSequenceMemoryGame()
```

Returns:

| Parameter       | Default | Description                        |
| --------------- | ------- | ---------------------------------- |
| gridSize        | 4       | Size of the grid (e.g., 4 for 4x4) |
| numOfRounds     | 5       | Number of rounds                   |
| maxWrongPresses | 3       | Max wrong presses allowed          |
| showTime        | 1000    | Time each round is shown (in ms)   |
| delayBetween    | 300     | Delay between rounds (in ms)       |

***

### StartVerbalMemoryGame

Starts the Verbal Memory minigame.

```lua
exports['glitch-minigames']:StartVerbalMemoryGame()
```

Returns:

| Parameter   | Default | Description                     |
| ----------- | ------- | ------------------------------- |
| maxStrikes  | 3       | Number of max strikes           |
| numOfWords  | 50      | Total words to show             |
| timePerWord | 5000    | Time each word is shown (in ms) |



***

### StartNumberedSequenceGame

Starts the Numbered Sequence minigame.

```lua
exports['glitch-minigames']:StartNumberedSequenceGame()
```

Returns:

| Parameter       | Default | Description                        |
| --------------- | ------- | ---------------------------------- |
| gridSize        | 4       | Size of the grid (e.g., 4 for 4x4) |
| sequenceLength  | 6       | Length of number sequence          |
| numOfRounds     | 3       | Number of rounds                   |
| showTime        | 4000    | Time to show the sequence (in ms)  |
| answerTime      | 10000   | Time to input the sequence (in ms) |
| maxWrongPresses | 3       | Max wrong presses allowed          |

***

### StartSymbolSearchGame

Starts the Symbol Search minigame.

```lua
exports['glitch-minigames']:StartSymbolSearchGame()
```

Returns:

| Parameter     | Default   | Description                                                                                                                  |
| ------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------- |
| gridSize      | 8         | Size of the grid (e.g., 8 for 8x8)                                                                                           |
| shiftInterval | 1000      | Time in ms between symbol shifts                                                                                             |
| timeLimit     | 30000     | Time limit (in ms)                                                                                                           |
| minKeyLength  | 1         | Minimum length of the symbol key                                                                                             |
| maxKeyLength  | 3         | Maximum length of the symbol key                                                                                             |
| symbolType    | "symbols" | There is four different symbol types you can choose from this includes "symbols", "letters", "numbers", "emojis" and "dots". |

***

### StartPipePressureGame

Starts the Pipe Pressure minigame.

```lua
exports['glitch-minigames']:StartPipePressureGame()
```

Returns:

| Parameter | Default | Description                        |
| --------- | ------- | ---------------------------------- |
| gridSize  | 6       | Size of the grid (e.g., 6 for 6x6) |
| timeLimit | 30000   | Time limit (in ms)                 |

***

### StartPairsGame

Starts the Pairs minigame.

```lua
exports['glitch-minigames']:StartPairsGame()
```

Returns:

| Parameter       | Default | Description                           |
| --------------- | ------- | ------------------------------------- |
| gridSize        | 4       | Size of the grid (e.g., 4 for 4x4)    |
| timeLimit       | 120000  | Time limit (in ms) or 0 for unlimited |
| maxWrongPresses | 0       | Max attempts or 0 for unlimited       |

***

### StartMemoryColorsGame

Starts the Memory Colors minigame.

```lua
exports['glitch-minigames']:StartMemoryColorsGame()
```

Returns:

| Parameter    | Default | Description                        |
| ------------ | ------- | ---------------------------------- |
| gridSize     | 5       | Size of the grid (e.g., 5 for 5x5) |
| memorizeTime | 5000    | Time to memorize colors            |
| answerTime   | 10000   | Time to answer                     |
| numOfRounds  | 3       | Number of rounds                   |

***

### StartUntangleGame

Starts the Untangle minigame.

```lua
exports['glitch-minigames']:StartUntangleGame()
```

Returns:

| Parameter | Default | Description                 |
| --------- | ------- | --------------------------- |
| nodeCount | 8       | Number of nodes to untangle |
| timeLimit | 60000   | Time limit (in ms)          |

***

### StartFingerprintGame

Starts the Fingerprint minigame.

```lua
exports['glitch-minigames']:StartFingerprintGame()
```

Returns:

| Parameter            | Default | Description                                              |
| -------------------- | ------- | -------------------------------------------------------- |
| timeLimit            | 30000   | Time limit (in ms)                                       |
| showAlignedCount     | true    | Makes it so the aligned count is shown, default true     |
| showCorrectIndicator | true    | Makes it so the correct indicator is shown, default true |

***

### StartCodeCrackGame

Starts the Code Crack minigame.

```lua
exports['glitch-minigames']:StartCodeCrackGame()
```

Returns:

| Parameter   | Default | Description              |
| ----------- | ------- | ------------------------ |
| timeLimit   | 60000   | Time limit (in ms)       |
| digitCount  | 4       | Number of digits in code |
| maxAttempts | 6       | Max attempts allowed     |

***

### StartWordCrackGame

Starts the Word Crack minigame.

```lua
exports['glitch-minigames']:StartWordCrackGame()
```

Returns:

| Parameter   | Default | Description                                                                                                                                                                                           |
| ----------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| timeLimit   | 120000  | Time limit (in ms)                                                                                                                                                                                    |
| wordCount   | 5       | <p>Number of letters in word.</p><p></p><p>(This should not be changed as the words list only contains 5 letter words so changing this would require you to update the word list in wordCrack.js)</p> |
| maxAttempts | 6       | Max attempts allowed                                                                                                                                                                                  |

***

### StartBalanceGame

Starts the Balance minigame.

```lua
exports['glitch-minigames']:StartBalanceGame()
```

Returns:

| Parameter       | Default | Description                          |
| --------------- | ------- | ------------------------------------ |
| timeLimit       | 10000   | Time limit (in ms)                   |
| driftSpeed      | 3       | How fast needle drifts               |
| sensitivity     | 8       | How much Q/E moves needle            |
| greenZoneWidth  | 30      | Width of safe green zone             |
| yellowZoneWidth | 25      | Width of warning yellow zone         |
| driftRandomness | 2       | How unpredictable the drift is       |
| maxDangerTime   | 1000    | Time allowed in red before fail (ms) |

***

### StartAimTestGame

Starts the Aim Test minigame.

```lua
exports['glitch-minigames']:StartAimTestGame()
```

Returns:

| Parameter      | Default | Description                             |
| -------------- | ------- | --------------------------------------- |
| timeLimit      | 30000   | Time limit (in ms)                      |
| targetsToHit   | 10      | Number of targets to win                |
| targetLifetime | 1500    | How long target stays (ms)              |
| targetSize     | 60      | Target diameter in pixels               |
| shrinkTarget   | true    | Whether target shrinks over time        |
| maxMisses      | 5       | Max missed targets before fail          |
| timePenalty    | 0       | Time removed on miss (ms), 0 = disabled |

***

### StartCircleClickGame

Starts the Circle Click minigame.

```lua
exports['glitch-minigames']:StartAimTestGame()
```

Returns:

| Parameter          | Default              | Description                   |
| ------------------ | -------------------- | ----------------------------- |
| numOfRounds        | 5                    | Number of rounds to complete  |
| rotationSpeed      | 2                    | Degrees per frame             |
| targetZoneSize     | 45                   | Target zone in degrees        |
| maxFailures        | 3                    | Max failures before game over |
| speedIncrease      | 0.15                 | Speed increase per round      |
| randomizeDirection | true                 | Randomize rotation direction  |
| keys               | {'W', 'A', 'S', 'D'} | Possible keys to display      |

***

### StartLockpickGame

Starts the Lockpick minigame.

```lua
exports['glitch-minigames']:StartLockpickGame()
```

Returns:

| Parameter     | Default | Description                                    |
| ------------- | ------- | ---------------------------------------------- |
| numOfRounds   | 3       | Number of locks to pick                        |
| sweetSpotSize | 30      | Sweet spot size in degrees (smaller = harder)  |
| maxFailures   | 2       | Max failures before game over                  |
| shakeRange    | 40      | How far from sweet spot shake starts (degrees) |
| lockTime      | 500     | How long to hold to lock (ms)                  |

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
