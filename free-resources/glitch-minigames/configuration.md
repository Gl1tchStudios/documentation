# Configuration

The following configuration options are available in shared/config.lua:

`config.DebugCommands (boolean):`\
Enable debug commands for testing purposes. Set to false for production.

`config.usingGlitchNotification (boolean):`\
Enable Glitch notification system integration.

## ⬆️ Exports

The following exports are available for use in your scripts:

### StartDrilling

Starts the Fleeca Bank drilling minigame.

```lua
exports['glitch-minigames']:StartDrilling()
```

Returns:

* success (boolean): Whether the drilling was successful

### StartCircuitBreaker

Starts the Circuit Breaker hacking minigame.

```lua
exports['glitch-minigames']:StartCircuitBreaker(levelNumber, difficultyLevel)
```

Parameters:

* levelNumber (number): Level layout to use (1-5)
* difficultyLevel (number): Difficulty setting (0-3)  \
  Returns:
* success (boolean): Whether the hack was successful

### StartDataCrack

Starts the Data Crack hacking minigame.

```lua
exports['glitch-minigames']:StartDataCrack(difficulty)
```

Parameters:

* difficulty (number): Number of layers to crack (default: 3)  \
  Returns:
* success (boolean): Whether the hack was successful

### StartBruteForce

Starts the Brute Force hacking minigame.

```lua
exports['glitch-minigames']:StartBruteForce()
```

Returns:

* success (boolean): Whether the hack was successful

### StartPlasmaDrilling

Starts the Plasma Drilling minigame.

```lua
exports['glitch-minigames']:StartPlasmaDrilling()
```

Returns:

* success (boolean): Whether the drilling was successful

### StartFirewallPulse

Starts the Firewall Pulse hacking minigame.

```lua
exports['glitch-minigames']:StartFirewallPulse(requiredHacks, initialSpeed, safeZoneSize, moveSpeed, timeLimit, progressMultiplier, dangerMultiplier)
```

Parameters:

* requiredHacks (number): Number of successful pulses needed
* initialSpeed (number): Starting speed of the pulse
* safeZoneSize (number): Size of the safe zone (1-100)
* moveSpeed (number): Speed of safe zone movement
* timeLimit (number): Time limit in seconds
* progressMultiplier (number): Success progress multiplier
* dangerMultiplier (number): Failure penalty multiplier  \
  Returns:
* success (boolean): Whether the hack was successful

### StartBackdoorSequence

Starts the Backdoor Sequence hacking minigame.

```lua
exports['glitch-minigames']:StartBackdoorSequence(requiredSequences, sequenceLength, timeLimit, maxAttempts, timePenalty, minKeys, maxKeys, possibleKeys, keyHintText)
```

Parameters:

* requiredSequences (number): Number of sequences to complete
* sequenceLength (number): Length of each sequence
* timeLimit (number): Time limit per sequence in seconds
* maxAttempts (number): Maximum failed attempts allowed
* timePenalty (number): Time penalty multiplier for failures
* minKeys (number): Minimum simultaneous keys per sequence
* maxKeys (number): Maximum simultaneous keys per sequence
* possibleKeys (table): Array of possible keys to use
* keyHintText (string): Text shown to explain available keys  \
  Returns:
* success (boolean): Whether the hack was successful

### StartVarHack

Starts the VAR System hack minigame.

```lua
exports['glitch-minigames']:StartVarHack(blocks, speed)
```

Parameters:

* blocks (number): Number of blocks to memorize (default: 5)
* speed (number): Speed of the game (default: 5)  \
  Returns:
* success (boolean): Whether the hack was successful

## Example Usage

```lua
RegisterCommand('testhack', function()
    local success = exports['glitch-minigames']:StartCircuitBreaker(1, 2)
    if success then
        print("Hack completed successfully!")
    else
        print("Hack failed!")
    end
end)
```



Any minigame that wasn't mentioned here does not have configuration and can only be performed one way. You can find how to use them in the [Examples ](../glitch-notifications/examples.md)section
