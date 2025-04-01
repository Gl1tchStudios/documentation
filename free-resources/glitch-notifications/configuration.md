# Configuration

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
