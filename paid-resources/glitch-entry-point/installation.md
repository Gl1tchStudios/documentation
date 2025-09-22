# Installation

## Prerequisites <a href="#prerequisites" id="prerequisites"></a>

Before installing this resource, ensure you have the required dependencies:

* **ESX** - Recommended framework for the resource. This resource is NOT set up for Glitch Abstraction, but you may convert manually as ESX aspects are unencrypted.
* **OX lib, inventory, and target.**
* **bob74\_ipl** - Required for spawning interiors and customising them
* Glitch Abstraction - **Required only if you want the features of abstraction like or if you are using QBCore or QBox** for communication between various frameworks and our scripts. It allows for us to streamline development through the use of an abstraction layer. [Click Here to find out more.](../../free-resources/glitch-abstraction/)

## Installation Steps <a href="#installation-steps" id="installation-steps"></a>

### 1. Download

Clone the repository to your local machine.

## 2. Dependencies

Verify that all required dependencies listed in the prerequisites section are properly installed and running on your server prior to starting Entry Point.

## 3. Server Configuration

Add the resource to your `server.cfg` file:

```
start glitch-entryPoint
```

## 4. Configuration

Feel free to go through all the files inside of the `shared`  folder, these files should be encrypted and provide customisability such as toggles in config-main.lua, locations in config-locations.lua.

## Final Notes <a href="#final-notes" id="final-notes"></a>

Once installation is complete, restart your server to activate the electrical job system. The resource will automatically integrate with your existing framework through Glitch Abstraction.
