# Theme Configuration

Glitch Minigames features a fully customizable theming system that allows you to change both the color scheme and visual style of all minigames.

***

### 🎨 Color Themes

Color themes control all the colors used throughout the minigames, including backgrounds, buttons, text, success/failure indicators, and more.

#### Setting the Active Color Theme

In `shared/config.lua`, set the `ActiveTheme` value to one of the available themes:

```lua
config.ActiveTheme = 'cyan' -- Options: 'cyan', 'monochrome'
```

#### Available Color Themes

| Theme        | Description                                                                      |
| ------------ | -------------------------------------------------------------------------------- |
| `cyan`       | The original Glitch Studios theme with blue gradients and a dark blue background |
| `monochrome` | A sleek black & white theme with grayscale UI elements                           |

#### Theme Color Properties

Each color theme contains the following customizable properties:

**Primary Colors**

| Property    | Description                                                    | Cyan Default | Monochrome Default |
| ----------- | -------------------------------------------------------------- | ------------ | ------------------ |
| `primary`   | Main accent color for highlights, active states, and gradients | `#33b5e5`    | `#ffffff`          |
| `secondary` | Secondary color for gradient bottoms and hover states          | `#0078d7`    | `#cccccc`          |

**Feedback Colors**

| Property  | Description                                 | Cyan Default | Monochrome Default |
| --------- | ------------------------------------------- | ------------ | ------------------ |
| `success` | Color shown on successful actions           | `#33b5e5`    | `#2dd4a8`          |
| `failure` | Color shown on failed actions               | `#ff4444`    | `#ff4444`          |
| `warning` | Warning indicators (timers, caution states) | `#ff7a30`    | `#ff7a30`          |
| `danger`  | High danger/critical states                 | `#ff3030`    | `#cc0000`          |
| `safe`    | Safe zone indicators                        | `#36ff00`    | `#22c55e`          |

**Background Colors**

| Property              | Description                            | Cyan Default | Monochrome Default |
| --------------------- | -------------------------------------- | ------------ | ------------------ |
| `background`          | Main background color                  | `#0f1e2d`    | `#000000`          |
| `backgroundGradient1` | Gradient start color                   | `#0f1e2d`    | `#000000`          |
| `backgroundGradient2` | Gradient end color                     | `#1e3c5a`    | `#1a1a1a`          |
| `backgroundSecondary` | Secondary backgrounds (buttons, cards) | `#001428`    | `#0d0d0d`          |
| `backgroundTertiary`  | Tertiary backgrounds (nested elements) | `#002038`    | `#1a1a1a`          |

**UI Colors**

| Property        | Description               | Cyan Default | Monochrome Default |
| --------------- | ------------------------- | ------------ | ------------------ |
| `border`        | Border and outline colors | `#33b5e5`    | `#808080`          |
| `text`          | Primary text color        | `#ffffff`    | `#ffffff`          |
| `textSecondary` | Secondary/muted text      | `#969696`    | `#a0a0a0`          |

**Minigame-Specific Colors**

| Property         | Description                           | Default     |
| ---------------- | ------------------------------------- | ----------- |
| `minigameColor1` | VarHack block 1, Memory Colors blue   | `#273cfcff` |
| `minigameColor2` | VarHack block 2, Memory Colors red    | `#2add57ff` |
| `minigameColor3` | VarHack block 3, Memory Colors green  | `#28e757ff` |
| `minigameColor4` | VarHack block 4, Memory Colors yellow | `#edeb64ff` |
| `minigameColor5` | VarHack block 5                       | `#eb87deff` |

#### Creating a Custom Color Theme

You can create your own color theme by adding a new entry to the `config.Themes` table:

```lua
config.Themes = {
    -- Your custom theme
    myTheme = {
        -- Primary Theme Colors
        primary = '#ff6b6b',
        primaryRgba = '255, 107, 107',
        secondary = '#ee5a5a',
        secondaryRgba = '238, 90, 90',
        
        -- Success/Failure Colors
        success = '#4ecdc4',
        successRgba = '78, 205, 196',
        failure = '#ff4444',
        failureRgba = '255, 68, 68',
        
        -- Warning/Caution Colors
        warning = '#ffe66d',
        warningRgba = '255, 230, 109',
        
        -- Neutral/UI Colors
        background = '#2c2c2c',
        backgroundRgba = '44, 44, 44',
        backgroundGradient1 = '#2c2c2c',
        backgroundGradient1Rgba = '44, 44, 44',
        backgroundGradient2 = '#3d3d3d',
        backgroundGradient2Rgba = '61, 61, 61',
        backgroundSecondary = '#1a1a1a',
        backgroundSecondaryRgba = '26, 26, 26',
        backgroundTertiary = '#333333',
        backgroundTertiaryRgba = '51, 51, 51',
        border = '#ff6b6b',
        borderRgba = '255, 107, 107',
        text = '#ffffff',
        textRgba = '255, 255, 255',
        textSecondary = '#b0b0b0',
        textSecondaryRgba = '176, 176, 176',
        
        -- Additional Colors
        danger = '#ff3030',
        dangerRgba = '255, 48, 48',
        safe = '#36ff00',
        safeRgba = '54, 255, 0',
        
        -- Minigame Specific Colors
        minigameColor1 = '#273cfcff',
        minigameColor2 = '#2add57ff',
        minigameColor3 = '#28e757ff',
        minigameColor4 = '#edeb64ff',
        minigameColor5 = '#eb87deff',
    },
}
```

Then set your theme as active:

```lua
config.ActiveTheme = 'myTheme'
```

{% hint style="info" %}
**RGBA Values:** Each color property has a corresponding `Rgba` property (e.g., `primaryRgba`). These contain the RGB values without the hash symbol, used for CSS `rgba()` functions where opacity needs to be applied.
{% endhint %}

***

### 🪟 Visual Themes

Visual themes control the overall appearance and style of the minigame UI, including layout, animations, and design elements.

#### Setting the Active Visual Theme

In `shared/config.lua`, set the `ActiveVisualTheme` value:

```lua
config.ActiveVisualTheme = 'classic' -- Options: 'classic', 'modern'
```

#### Available Visual Themes

| Theme     | Description                                                 |
| --------- | ----------------------------------------------------------- |
| `classic` | The original Glitch Studios design with traditional styling |
| `modern`  | A sleek, contemporary design with updated visual elements   |

#### Visual Theme Differences

| Feature      | Classic                 | Modern                     |
| ------------ | ----------------------- | -------------------------- |
| Border Style | Standard borders        | Softer, rounded edges      |
| Animations   | Traditional transitions | Smoother, fluid animations |
| Layout       | Compact design          | More spacious layout       |
| Shadows      | Minimal shadows         | Enhanced shadow effects    |

***

### Background Opacity

You can customize the background transparency for each visual theme independently:

```lua
config.BackgroundOpacity = {
    classic = 0.80,  -- 80% opacity for classic theme
    modern = 0.90    -- 90% opacity for modern theme
}
```

| Value | Effect                                   |
| ----- | ---------------------------------------- |
| `0.0` | Fully transparent (invisible background) |
| `0.5` | 50% transparent (semi-transparent)       |
| `1.0` | Fully opaque (solid background)          |

***

### Color Theme Preview

#### Cyan Theme

The cyan theme features a blue-gradient design:

* **Tiles & Buttons:** Gradient from light blue (`#33b5e5`) to neon blue (`#0078d7`)
* **Background:** Dark blue (`#0f1e2d`)
* **Success:** Light blue flash
* **Failure:** Red flash (`#ff4444`)
* **Timer Warnings:** Dark orange (`#ff7a30`)

#### Monochrome Theme

The monochrome theme features a grayscale design:

* **Tiles & Buttons:** White to light gray gradient
* **Background:** Pure black (`#000000`)
* **Success:** Cyan/green flash (`#2dd4a8`)
* **Failure:** Red flash (`#ff4444`)
* **Borders:** Medium gray (`#808080`)



#### Cyan Color Theme with Modern Visual Theme

<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

#### Monochrome Color Theme with Modern Visual Theme

<figure><img src="../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>
