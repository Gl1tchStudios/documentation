---
description: >-
  A sleek and customizable notification system for FiveM, designed for clarity
  and performance. Deliver real time alerts with smooth animations and flexible
  styling.
---

# Glitch Notifications

## Glitch Notifications System [![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

Github Resource: [https://github.com/Gl1tchStudios/glitch-notifications](https://github.com/Gl1tchStudios/glitch-notifications)

### Overview

Glitch Notifications is a dynamic notification system for FiveM, allowing developers to display customizable notifications with titles, dividers, and multiple text boxes. The system supports adding, updating, and removing individual text boxes, as well as toggling notifications on and off.

### Features

* Customizable notifications with titles, dividers, and text boxes.
* Add, update, or remove individual text boxes dynamically.
* Toggle notifications on or off with a single command.
* Support for custom colors and animations.
* Easy integration with FiveM using exports.

**Multiple Notifications Example:**

<div align="left"><figure><img src="../.gitbook/assets/ezgif.com-optimize (2).gif" alt=""><figcaption></figcaption></figure></div>

**Coloured Notifications Example:**

<div align="left"><figure><img src="../.gitbook/assets/Discord_PrRp28EYVy-min (1).gif" alt=""><figcaption></figcaption></figure></div>

**Timer Notifications Example:**

![](../.gitbook/assets/Discord_HWEEQlgrkK-min.gif)

### File Structure

```
glitch-notifications
├── client
│   ├── main.lua        # Main client-side script
│   └── ui
│       ├── index.html  # HTML structure for the UI
│       ├── style.css   # Styles for the UI
│       └── script.js   # JavaScript logic for dynamic notifications
├── server
│   └── main.lua        # Main server-side script
├── fxmanifest.lua      # Resource manifest
└── README.md           # Project documentation
```

### Setup Instructions

1. **Clone the repository** to your local machine.
2. **Place the `glitch-notifications` folder** into your FiveM resources directory.
3.  **Add the resource** to your `server.cfg`:

    ```
    start glitch-notifications
    ```
4. **Ensure you have the necessary permissions** to run the script on your server.

### Exports

The following exports are available for use in your scripts:

#### `ShowNotification`

Displays a notification with a title, message, and optional customizations.

```lua
exports['glitch-notifications']:ShowNotification(title, message, duration, color, noAnimation)
```

* **Parameters**:
  * `title` (string): The title of the notification.
  * `message` (string): The main text of the notification.
  * `duration` (number): Duration in milliseconds (0 for persistent).
  * `color` (string): Hex color code for the title (e.g., `#ff4500`).
  * `noAnimation` (boolean): If `true`, disables animations.

#### `AddBoxToNotification`

Adds a new text box to an existing notification.

```lua
exports['glitch-notifications']:AddBoxToNotification(notificationId, title, message, color, noAnimation)
```

* **Parameters**:
  * `notificationId` (number): The ID of the notification to update.
  * `title` (string): The title of the notification (used for grouping).
  * `message` (string): The text to add as a new box.
  * `color` (string): Hex color code for the title (optional).
  * `noAnimation` (boolean): If `true`, disables animations.

#### `RemoveBoxFromNotification`

Removes a specific text box from a notification.

```lua
exports['glitch-notifications']:RemoveBoxFromNotification(notificationId, boxId)
```

* **Parameters**:
  * `notificationId` (number): The ID of the notification.
  * `boxId` (number): The ID of the text box to remove.

#### `RemoveNotification`

Removes an entire notification, including all its text boxes.

```lua
exports['glitch-notifications']:RemoveNotification(notificationId)
```

* **Parameters**:
  * `notificationId` (number): The ID of the notification to remove.

#### `UpdateBoxContent`

Updates the content of a specific text box without animations.

```lua
exports['glitch-notifications']:UpdateBoxContent(notificationId, boxId, newMessage, newTitle, newColor)
```

* **Parameters**:
  * `notificationId` (number): The ID of the notification.
  * `boxId` (number): The ID of the text box to update.
  * `newMessage` (string): The updated text for the box.
  * `newTitle` (string): The updated title for the notification (optional).
  * `newColor` (string): The updated color for the title (optional).

#### `ToggleNotification`

Toggles a notification on or off.

```lua
exports['glitch-notifications']:ToggleNotification(id, title, message, color)
```

* **Parameters**:
  * `id` (number): A unique ID for the notification.
  * `title` (string): The title of the notification.
  * `message` (string): The main text of the notification.
  * `color` (string): Hex color code for the title.

### Examples

#### Basic Notification

```lua
exports['glitch-notifications']:ShowNotification("Maze Bank", "Transaction completed", 5000, "#ff4500")
```

#### Persistent Notification with Multiple Boxes

```lua
local notifId = exports['glitch-notifications']:ShowNotification("Diamond Casino", "Welcome to the Casino!", 0, "#4a90e2")

-- Add more boxes
exports['glitch-notifications']:AddBoxToNotification(notifId, "Diamond Casino", "Enjoy your stay!", "#22bb33")
exports['glitch-notifications']:AddBoxToNotification(notifId, "Diamond Casino", "Check out the VIP lounge!", "#ff5500")
```

#### Remove a Specific Box

```lua
exports['glitch-notifications']:RemoveBoxFromNotification(notifId, boxId)
```

#### Update a Box

```lua
exports['glitch-notifications']:UpdateBoxContent(notifId, boxId, "Updated message!", nil, "#00ff00")
```

#### Toggle a Notification

```lua
exports['glitch-notifications']:ToggleNotification(12345, "Maze Bank", "Your balance is low!", "#ff0000")
```

### 📜 Credits

* **Developed by** Luma in collaboration with Glitch Studios
* **Special thanks** to the FiveM community for support and inspiration

***

### 📜 License

This project is licensed under the **GNU General Public License v3.0** - see the LICENSE file for details.

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

For support or inquiries, please join and open a ticket [**https://discord.gg/uZ7bJwtM4c**](https://discord.gg/uZ7bJwtM4c).
