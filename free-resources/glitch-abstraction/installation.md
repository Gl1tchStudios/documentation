# Installation

### Setup Instructions

1. **Clone the repository** to your local machine.
2. **Place the `glitch-abstraction`folder** into your FiveM resources directory.
3.  **Add the resource** to your `server.cfg`:&#x20;

    ```
    start glitch-abstraction
    ```
4.  **Reference the library in your scripts:**

    ```lua
    local GlitchAbst = exports['glitch-abstraction']:getAbstraction()
    ```

