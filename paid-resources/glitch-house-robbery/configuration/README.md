# Configuration

### **Configuration Guide**

The House Robbery script offers extensive customisation options through configuration files and open source integration files. This guide will walk you through each configuration option to help you set up the perfect criminal progression experience for your server.

### **Configuration Files**

The configuration is split across multiple lua files:

**Shared Folder:**

* **config.lua** - Core gameplay settings including:
  * XP system and level progression
  * Loot tier configuration and reward tables
  * Lockpicking mechanics and success rates
  * Noise alarm system and detection thresholds
  * Search timers and level-based reductions
  * Starting locations and NPC spawns
  * Police notification delays
* **apiKeys.lua** - External integration settings:
  * Discord webhook URLs for logging

**Open Source Files:**

* **open\_source.lua** - Client-side integration functions:
  * Skill check/minigame system configuration
  * Notification system (easily modify for your preferred notification resource)
  * Weather control and environmental effects
  * Framework-specific client functions
* **open\_source.lua** - Server-side integration functions:
  * Player identification and license retrieval
  * XP gain and level-up notifications
  * Phone notification system (adapt to your phone resource if not using lb-phone)
  * Police alert integration (adapt to your dispatch system)
  * Framework-specific server functions

All files are fully accessible and commented, allowing you to tailor every aspect of the robbery system to your server's needs.
