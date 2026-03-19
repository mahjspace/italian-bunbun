# Design System Strategy: The Tactile Scholar

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Tactile Scholar."** 

Mahjong is a game of ritual, touch, and social intellect. This system moves away from the "app-like" utility of standard trackers and toward a high-end editorial experience. We aim to replicate the feeling of a private social club—think heavy paper stock, gold-leaf detailing, and the quiet atmosphere of a forest retreat. 

To break the "template" look, we utilize **Intentional Asymmetry**. Instead of perfectly centered grids, we use generous, uneven white space and overlapping elements (e.g., a gold-accented button partially overlapping a forest green card) to create a sense of human touch and bespoke craftsmanship.

---

## 2. Colors
Our palette is rooted in the "Zen Social" philosophy: deep, grounding greens and luminous, celebratory golds.

*   **Primary (#072b14)** & **Primary Container (#1f4128)**: These represent the "Forest." Use these for deep immersion—hero sections, active states, and primary navigation.
*   **Secondary (#745a27)** & **Secondary Container (#fedb9b)**: The "Gold." These are your highlights. Use them sparingly to draw the eye to "Zen" moments: a winning streak, a social invite, or a "New Game" trigger.

### The "No-Line" Rule
Standard UI relies on 1px borders to separate content. In this system, **1px solid borders are prohibited for sectioning.** 
Boundaries must be defined through:
1.  **Background Color Shifts:** A `surface-container-low` section sitting on a `surface` background.
2.  **Tonal Transitions:** Using the hierarchy of `surface-container-lowest` to `highest` to define depth.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked physical layers. 
*   **Base:** `surface` (#fcf9f4).
*   **Secondary Sections:** `surface-container-low`.
*   **Interactive Cards:** `surface-container-lowest` (pure white) to provide a "lift" against the cream background.
*   **Floating Elements:** Use **Glassmorphism**. For search bars or overlays, use `surface` at 80% opacity with a `backdrop-blur` of 12px.

### Signature Textures
Main CTAs should never be flat. Use a subtle linear gradient from `primary` (#072b14) to `primary-container` (#1f4128) at a 135-degree angle. This adds a "silk" sheen to the buttons that feels premium and intentional.

---

## 3. Typography
We use a high-contrast typographic scale to balance the "Scholar" (Serif) with the "Data" (Sans).

*   **Display & Headline (Noto Serif):** These are our editorial anchors. Use `display-lg` for welcome screens and `headline-md` for social group names. The serif reflects the history and sophistication of Mahjong.
*   **Title, Body, & Label (Manrope):** This is our functional engine. Use `title-md` for player names and `body-sm` for game statistics. Manrope provides a clean, modern counterpoint to the serif, ensuring data remains legible at small sizes.

**Editorial Rule:** Always pair a `headline-sm` (Serif) with a `label-md` (Sans, All Caps, tracked out +10%) to create a sophisticated, magazine-style header.

---

## 4. Elevation & Depth
Depth is achieved through **Tonal Layering**, not structural shadows.

*   **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` background. This creates a natural "paper on felt" lift without the need for heavy shadows.
*   **Ambient Shadows:** When an element must float (like a social invite modal), use a shadow with a blur of `24px`, an opacity of `6%`, and a tint derived from `on-surface` (#1c1c19). Never use pure black shadows.
*   **The "Ghost Border" Fallback:** If a container requires more definition for accessibility, use the `outline-variant` token at **15% opacity**. It should be felt, not seen.

---

## 5. Components

### Social Cards
*   **Structure:** No dividers. Use `surface-container-lowest` for the card body. 
*   **Social Grouping:** Cluster friend avatars using the `spacing-1` scale. 
*   **Accents:** A 4px vertical "tab" of `secondary` (Gold) on the left edge of a card to denote a "High Priority" or "Live Game" status.

### Buttons (Invite & Action)
*   **Primary:** Gradient of `primary` to `primary-container`. `rounded-md`.
*   **Invite (Secondary):** `secondary-container` background with `on-secondary-container` text. Use a thin-stroke "Plus" icon (0.75pt).
*   **Tertiary:** Text-only with an `outline-variant` "Ghost Border" that appears only on hover.

### Search Bars
*   **Style:** `surface-container-high` background with `rounded-full`. 
*   **Iconography:** Use a thin-stroke (light) search icon.
*   **Focus State:** Shift background to `surface-container-highest` and add a 1px `secondary` (Gold) Ghost Border at 20% opacity.

### Lists & Social Feeds
*   **Forbid Dividers:** Use `spacing-4` or `spacing-6` between items. 
*   **Visual Shift:** Alternate background colors between `surface` and `surface-container-low` for long data lists to maintain rhythm without lines.

### Inputs
*   **Text Fields:** Minimalist. A bottom-only `outline-variant` (20% opacity). On focus, the line transitions to `secondary` (Gold) and the label shifts to `label-sm` using the Gold color.

---

## 6. Do's and Don'ts

### Do:
*   **Do** use asymmetrical margins. If the left margin is `spacing-6`, try making the right margin of a nested element `spacing-8` to create "breathing room."
*   **Do** use `secondary` (Gold) for small, meaningful moments—like a dot indicating an unread message or a gold-tinted icon for a "Pro" player.
*   **Do** prioritize the Serif typeface for anything that feels "human" (names, quotes, welcome messages).

### Don't:
*   **Don't** use 100% opaque black for text. Always use `on-surface` (#1c1c19) to maintain a soft, organic feel.
*   **Don't** use standard "drop shadows." If it looks like a default Material UI card, it’s too heavy for this system.
*   **Don't** crowd the interface. If a screen feels busy, increase the spacing using the `spacing-8` or `spacing-10` tokens. In "Zen Social," space is a luxury.