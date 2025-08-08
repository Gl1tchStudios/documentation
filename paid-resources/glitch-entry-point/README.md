---
hidden: true
---

# 🎯 Glitch Entry Point

A comprehensive tactical training system for FiveM law enforcement, featuring dynamic breach scenarios, hostage situations, and immersive police training environments.

**Entry Point**\
Video Showcase: \[Coming Soon]\
Tebex Resource: \[URL]

### **Overview**

**Entry Point** is a sophisticated tactical training resource designed specifically for FiveM police roleplay servers. This system provides realistic breach-and-clear scenarios, hostage rescue operations, and comprehensive tactical training environments. With support for both exterior and interior maps, dynamic AI behaviour, and fully configurable difficulty settings, Entry Point transforms police training from basic shooting ranges into immersive, scenario-based learning experiences.

### **Features**

* **🏠 Diverse Training Environments**: Multiple exterior and interior maps including mansions, industrial facilities, nightclubs, offices, and more
* **🤖 Dynamic AI System**: Intelligent enemy placement with configurable hostage behaviour and hostile response mechanics
* **👥 Multi-Player Support**: Coordinate team-based training scenarios with scalable difficulty
* **🎮 Immersive Experience**: Realistic breach scenarios with proper equipment spawning and tactical positioning
* **⚙️ Fully Configurable**: Extensive configuration options for difficulty, AI behaviour, weapons, and map settings
* **🎭 Role-Based Access**: Integrated job and grade restrictions with optional Discord role verification
* **📍 Professional Map System**: Categorized map selection with detailed briefings and tactical assessments
* **🚁 Vehicle Integration**: Helicopter and ground vehicle spawns for realistic approach scenarios
* **🏆 Consequence System**: Realistic penalties for civilian casualties and tactical failures
* **🎯 Weapon Variety**: Comprehensive weapon selection system for different training scenarios

### **Training Scenarios**

#### **Exterior Maps**

* **BanHam Canyon Drive**: Multi-level mansion with elevation advantages and limited visibility
* **Little Bighorn Ave**: Industrial facility with rooftop positions and wide exterior zones
* **Orchardvile Avenue**: Meat processing plant with narrow hallways and close-quarters combat
* **Aircraft Carrier**: Military vessel with unique tactical challenges
* **O'Neil Farm**: Rural compound with multiple structures and ambush potential

#### **Interior Maps**

* **The Palace Nightclub**: Dynamic lighting with civilian-heavy environment
* **Agency Building**: Corporate office with glass partitions and minimal cover
* **Recording Studio**: Multi-level facility with soundproof booths and narrow corridors
* **Residential Apartments**: Various apartment layouts for domestic response training
* **Executive Office**: High-rise corporate suite with boardrooms and executive areas

### **System Components**

#### **AI Behaviour System**

* Configurable hostage response (peaceful, hostile, or mixed)
* Dynamic enemy positioning and patrol routes
* Realistic threat assessment and engagement rules
* Scalable difficulty based on team size and experience

#### **Equipment Management**

* Automatic loadout assignment based on scenario requirements
* Vehicle spawning for tactical approaches
* Radio channel assignment for team coordination
* Health, armour, and accuracy standardization

#### **Performance Tracking**

* Hostage casualty monitoring
* Mission completion metrics
* Team coordination assessment
* Training progression tracking

### **Configuration Options**

#### **Access Control**

```lua
-- Job-based restrictions
Config.PoliceRole = { 'police', 'offpolice' }
Config.PoliceGrade = 3 -- Minimum rank requirement

-- Discord integration (optional)
Config.DiscordRoleCheck = false
Config.DiscordRolesToCheck = { "Tactical Operations Unit", "Police Leaders" }
```

#### **Scenario Difficulty**

```lua
-- Hostage behavior settings
Config.hostileHostageChance = 40 -- Percentage of hostile hostages
Config.deadHostageResponse = 'mask' -- Consequences for civilian casualties

-- AI Configuration
Config.defaultAccuracy = 80 -- Enemy accuracy level
Config.SoldierModels = { 's_m_y_swat_01', 's_m_y_marine_02' } -- Enemy types
```

#### **Map Customization**

Each training environment includes:

* Recommended team size and enemy count
* Tactical briefing and scenario description
* Custom vehicle spawns and equipment loadouts
* Polygon boundaries for contained training areas
* Professional imagery and mission context

### **Installation Requirements**

#### **Dependencies**

* **ox\_lib**: Modern UI framework for menu systems and notifications
* **bob74\_ipl**: Interior loading for complex building environments (optional for some maps)
* **ESX**: Job framework integration for role-based access. May be converted to QB core or other frameworks but that will need to do that manually.

#### **Recommended**

* Voice and radio system for communication allowing for team coordination

### **⭐ Credits**

* **Developed by** DexterTheCat3 in collaboration with Glitch Studios

### **💖 Special Thanks**

We extend our appreciation to the FiveM development community for their continued innovation in police roleplay resources. Special recognition goes to:

* **ESX Framework** developers for providing robust job management systems
* **ox\_lib** contributors for modern UI components and notification systems
* **bob74\_ipl** project for comprehensive interior loading capabilities
* **FiveM Police Roleplay Community** for feedback and scenario testing

Your contributions have enabled the creation of realistic, engaging, and educationally valuable training scenarios that enhance the quality of police roleplay across the FiveM ecosystem.
