# Design System Document: Precision Field Editorial

## 1. Overview & Creative North Star
### Creative North Star: "The Elemental Command"
This design system moves beyond the generic utility of ag-tech to create an experience of **Atmospheric Precision**. We are designing for a user who operates in high-glare, high-stakes environments where clarity is paramount. The system rejects the "dashboard" aesthetic in favor of a "High-End Editorial" approach—utilizing bold, authoritative typography, intentional asymmetry, and deep tonal layering. 

We break the "template" look by treating the interface as a digital cockpit. By leveraging extreme white space (negative space) and over-scaled data points, we ensure that a farmer can read the status of a center-pivot system from an arm’s length in direct sunlight. This is not just an app; it is a premium tool of architectural scale.

---

## 2. Colors
Our palette is rooted in the landscape: the deep green of healthy crops, the vibrant blue of water, and the urgent red of machinery alerts.

*   **Primary (#0d631b):** Represents life and active operation. Use for "System Running" states and primary progress indicators.
*   **Secondary (#005faf):** Represents the water resource. Reserved exclusively for hydration metrics and flow controls.
*   **Tertiary (#ac0c18):** High-visibility red for critical stoppages or hardware failures.

### The "No-Line" Rule
To achieve a premium editorial feel, **1px solid borders are strictly prohibited** for sectioning. Structural boundaries must be defined solely through background color shifts. Use `surface-container-low` for large section backgrounds sitting on a `surface` base. This creates a modern, seamless flow that feels integrated into the hardware.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
1.  **Base:** `surface` (#f8f9fa)
2.  **Sectioning:** `surface-container-low` (#f3f4f5)
3.  **Interactive Elements:** `surface-container-lowest` (#ffffff) for high-contrast "pop."

### The "Glass & Gradient" Rule
To provide "visual soul," floating control modules (like a pivot manual override) should use **Glassmorphism**. Apply `surface-container-lowest` at 80% opacity with a `backdrop-blur` of 20px. 
*   **Signature Texture:** Use a subtle linear gradient on main CTAs—transitioning from `primary` (#0d631b) to `primary_container` (#2e7d32) at a 135-degree angle—to give buttons a tactile, high-end machined quality.

---

## 3. Typography
We use **Inter** to provide a clean, Swiss-style precision. The hierarchy is designed to be "glanceable."

*   **Display-LG (3.5rem):** Reserved for the single most important number on the screen (e.g., "98%" Pivot Completion).
*   **Headline-LG (2rem):** Used for screen titles to anchor the user’s location.
*   **Title-MD (1.125rem):** Used for actionable labels and section headers.
*   **Body-LG (1rem):** High-readability weight for status descriptions.

**Editorial Style Tip:** Use `display-lg` in a **Bold** weight alongside `body-sm` in a **Regular** weight. This high-contrast scale creates an authoritative, modern look that guides the eye immediately to the data that matters.

---

## 4. Elevation & Depth
Depth is conveyed through **Tonal Layering** rather than traditional skeletal structures.

### The Layering Principle
Instead of a flat grid, stack surfaces. A card containing pivot sector data should be `surface-container-lowest` placed upon a `surface-container-low` background. This creates a "soft lift."

### Ambient Shadows
For floating action buttons or critical pop-overs, use an "Ambient Shadow." 
*   **Specs:** `X: 0, Y: 12, Blur: 32, Spread: 0`. 
*   **Color:** Use the `on-surface` color at 6% opacity. Never use pure black; the shadow should feel like a soft glow of depth.

### The "Ghost Border" Fallback
If a visual separator is required for accessibility, use a **Ghost Border**: `outline-variant` (#bfcaba) at 15% opacity. It should be felt, not seen.

---

## 5. Components

### Buttons (Primary & Secondary)
*   **Sizing:** Minimum height of **56dp** for outdoor gloved-hand use.
*   **Rounding:** `xl` (1.5rem/24px) for a sophisticated, rounded-tablet feel.
*   **Styling:** Primary buttons use the Signature Gradient. Secondary buttons use `secondary_container` with `on_secondary_container` text.

### The "Pulse" Card
A specialized component for this system. A large `surface-container-lowest` card with a thick 4px left-accent bar in `primary`. No dividers. Use 24px internal padding (`xl` spacing) to let the data breathe.

### Input Fields
*   **Visual Style:** Do not use "outlined" boxes. Use a "Filled" style with `surface-container-high` and a 2px bottom-weighted indicator in `primary`. 
*   **Touch Targets:** Ensure all input fields are at least **64dp** tall to accommodate outdoor vibration and movement.

### Selection Chips
*   **Rounding:** `full` (9999px).
*   **State:** Unselected chips should be `surface-container-highest` with no border. Selected chips "activate" into `primary` with `on_primary` text.

### The Radial Progress Indicator (System Specific)
Since this is for Center Pivot irrigation, use a thick-stroke (8px) circular progress bar in `secondary` to represent the pivot's physical position in the field.

---

## 6. Do's and Don'ts

### Do:
*   **Do** prioritize one main action per screen. If the pivot needs to "Start," that button should occupy the bottom 20% of the screen.
*   **Do** use asymmetrical layouts. Place large data on the left and supporting labels on the right to break the "web-template" feel.
*   **Do** use `on_error_container` text for alerts to ensure readability against `error_container` backgrounds in high sunlight.

### Don't:
*   **Don't** use 1px dividers between list items. Use 16px of vertical white space to separate thoughts.
*   **Don't** use small icons. All icons must be "Thick-Stroke" (2px minimum weight) and at least 32x32px within a 48dp touch target.
*   **Don't** use "Light Grey" text for sub-labels. In outdoor environments, this fails contrast. Use `on_surface_variant` for secondary text to maintain a minimum 4.5:1 ratio.