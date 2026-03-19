# Design System Strategy: The Tactile Editorial

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Ephemera."** 

We are moving away from the cold, clinical nature of standard SaaS interfaces and embracing the warmth and authority of professional physical printing. Inspired by the iconic National Mah Jongg League cards, this system prioritizes information density, rhythmic repetition, and the tactile quality of ink on premium paper. 

To break the "template" look, we employ **Intentional Asymmetry**. Information is not always perfectly centered; instead, it follows a structured, multi-column editorial grid. We use high-contrast typography scales where massive headers sit alongside delicate, highly-detailed labels, mimicking the hierarchy of a reference document that is meant to be studied, not just glanced at.

## 2. Colors
Our palette is rooted in the "Tri-Color Tile" tradition, utilizing high-chroma accents against a sophisticated, weathered neutral base.

*   **Surface Hierarchy:** The primary background is `surface` (#faf9f5). To create depth without shadows, we utilize **Tonal Nesting**. A section of content should sit within a `surface-container-low` block, while interactive elements or nested "tiles" use `surface-container-lowest` (pure white) to provide a crisp, printed-page contrast.
*   **The "No-Line" Rule:** Standard 1px solid borders are strictly prohibited for structural sectioning. Boundaries must be defined by shifts in background color (e.g., a `surface-container-high` header bar against a `surface` body).
*   **Signature Textures:** While the UI is "flat," CTAs should utilize a subtle linear gradient from `primary` (#004d29) to `primary-container` (#22663e). This mimics the slight sheen of fresh ink and provides a "soul" that flat hex codes lack.
*   **Accent Logic:** 
    *   `Primary` (Dragon Green): Primary actions and success states.
    *   `Secondary` (Joker Red): Critical hand values and high-priority alerts.
    *   `Tertiary` (Crak Blue): Informational badges and secondary suit logic.

## 3. Typography
The typographic soul of the system lies in the tension between a robust, geometric sans-serif and a scholarly, structured serif.

*   **Display & Headlines (Noto Serif):** Used for section titles (e.g., "QUINTS," "SINGLES AND PAIRS"). The serif conveys authority and the heritage of professional printing. Use `headline-md` for secondary headers to maintain a "bookish" feel.
*   **Titles & Body (Manrope):** This is our "Hand" font. Manrope’s geometric clarity ensures that complex Mah Jongg hands (e.g., `111 222 3333 4444`) remain legible at small sizes.
*   **Labels (Manrope Bold):** Used for "VALUE" markers and "X 25" indicators. These should be high-contrast (using `on-surface`) to ensure they pop against the cream background.

## 4. Elevation & Depth
We reject the standard Material Design shadow-heavy approach in favor of **Tonal Layering**.

*   **The Layering Principle:** Depth is achieved by stacking. A `surface-container-lowest` card placed on a `surface-container-low` background creates a "natural lift" that feels like a physical card sitting on a table.
*   **Ambient Shadows:** If a floating element (like a Modal or FAB) is required, use an extra-diffused shadow: `blur: 24px`, `opacity: 6%`, color tinted with `on-surface` (#1b1c1a). Never use pure black shadows.
*   **The "Ghost Border":** For tile containers where separation is critical, use the `outline-variant` token at 15% opacity. It should be felt, not seen.
*   **Glassmorphism:** For overlays or navigation bars, use `surface-bright` with a 12px backdrop-blur. This allows the "paper texture" of the background to bleed through, softening the interface.

## 5. Components

### Buttons
*   **Primary:** `primary` fill with `on-primary` text. Use `rounded-sm` (0.125rem) for a sharp, "trimmed card" look.
*   **Tertiary (Editorial):** Underlined text using `primary` color, no container. This mimics the "See Note" style of physical cards.

### Cards (The "Hand" Container)
*   **Style:** No shadows. Use `surface-container-lowest` background with a `px` width `outline-variant` at 20% opacity. 
*   **Layout:** Forbid dividers. Use `spacing-4` (0.9rem) of vertical white space to separate different hands. Use "dotted-leader" patterns (e.g., `.......`) to connect hands to their values, reinforcing the printed card aesthetic.

### Chips (Suits & Tiles)
*   **Selection:** Use `primary-fixed` for the background with a sharp `none` (0px) or `sm` (0.125rem) corner radius. These should look like physical mah jongg tiles.

### Input Fields
*   **Text Inputs:** Use a "bottom-line only" approach or a very subtle `surface-container-highest` fill. Avoid the "boxed-in" look of modern web forms to keep the layout feeling like an open document.

### Tooltips
*   **Appearance:** High-contrast `inverse-surface` with `inverse-on-surface` text. Keep corners sharp (`sm`).

## 6. Do's and Don'ts

### Do:
*   **Embrace Information Density:** The physical card is dense; the digital version should feel efficient, not sparse. Use `spacing-2` and `spacing-3` for tight data groupings.
*   **Use Monospaced Alignment:** Ensure hand numbers align vertically across different rows to allow for easy scanning of patterns.
*   **Play with Case:** Use All-Caps for `label-sm` and `headline-sm` to mimic the "Section Header" style of the original card.

### Don't:
*   **Don't use Rounded-XL:** Avoid large border-radii. This system is about the precision of a cut card, not the softness of a mobile app. Stick to `sm` (0.125rem) or `none`.
*   **Don't use Dividers:** Never use a solid 1px line to separate list items. Use a shift to `surface-container-low` or simply increase the vertical padding.
*   **Don't use Pure Black:** Always use `on-surface` (#1b1c1a) or the charcoal (#333) for text. Pure #000 is too harsh for the "cream paper" background.