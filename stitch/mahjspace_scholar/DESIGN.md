# The Design System: Editorial Tactility & The Scholar’s Study

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Archivist"**
This design system rejects the sterile, flat aesthetic of modern SaaS in favor of a "Digital Archivist" approach. The experience should feel like navigating a high-end, private library at midnight—intellectual, weighted, and profoundly immersive. 

To break the "template" look, we employ **Intentional Asymmetry**. Rather than perfectly centered grids, we utilize the spacing scale to create editorial "breathing room," where text blocks might be offset to the left while imagery floats with organic, oversized margins. We prioritize tonal depth over structural lines, creating a UI that feels grown rather than built.

---

## 2. Colors & Atmospheric Depth
Our palette is rooted in deep botanical greens and oxidized metallics. It is designed to reduce eye strain while conveying a sense of heritage.

### The Palette
- **Background (`#001807`):** The "Infinite Forest." This is the foundation of every page.
- **Primary (`#c8c6c2`):** A warm, parchment-tinted off-white for high-readability text.
- **Secondary (`#e4c285`):** Our signature "Brass" accent. Use sparingly for call-to-actions and critical highlights.
- **Surface Tiers:** Use `surface_container_low` (`#00210c`) for subtle depth and `surface_bright` (`#1e4027`) for interactive elements.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to define sections. A "boxed" layout is the antithesis of this system. Boundaries must be defined solely through background color shifts. If a section needs to end, transition from `surface` to `surface_container_low`. 

### Surface Hierarchy & Nesting
Treat the UI as a series of nested physical layers. 
- **The Base:** `surface_dim` or `background`.
- **The Object:** Place a `surface_container` card on top.
- **The Interactive:** Use `surface_container_highest` for hover states.
By shifting tones rather than adding lines, the UI feels like a continuous, carved object rather than a collection of disparate parts.

### Signature Textures
Apply a subtle linear gradient to main CTAs using `secondary` transitioning into `secondary_container`. This mimics the way light hits a metallic surface, providing a "soul" that flat hex codes cannot achieve.

---

## 3. Typography: The Editorial Voice
We use a high-contrast typographic pairing to balance "Scholarly Authority" with "Modern Utility."

*   **Headings (The Newsreader Scale):** Used for all `display` and `headline` levels. This serif typeface carries the weight of a classic broadsheet. 
    *   *Implementation:* Use `display-lg` (3.5rem) with tighter letter-spacing (-0.02em) for hero moments to create a "printed" feel.
*   **Body & Labels (The Manrope Scale):** Used for `title`, `body`, and `label` levels. This geometric sans-serif ensures that even dense scholarly data remains legible.
    *   *Implementation:* For `body-lg`, use a generous line-height (1.6) to allow the deep green background to "bleed" through the lines of text.

---

## 4. Elevation & Depth: Tonal Layering
In this system, "Up" does not mean "Shadow." It means "Lighter."

### The Layering Principle
To create hierarchy, stack your tokens:
1.  **Level 0 (Floor):** `surface`
2.  **Level 1 (Section):** `surface_container_low`
3.  **Level 2 (Card):** `surface_container`
4.  **Level 3 (Pop-over):** `surface_container_highest`

### Ambient Shadows
If a floating element (like a modal) is required, use an "Ambient Shadow." 
- **Shadow Color:** `#001205` (a tinted version of our deepest green).
- **Blur:** 40px - 60px.
- **Opacity:** 15%.
This creates a soft glow of darkness rather than a harsh synthetic drop shadow.

### Glassmorphism & Depth
For navigation bars and floating chips, use `surface_variant` at 70% opacity with a `backdrop-blur` of 12px. This allows the lush forest green of the background to soften the edges of the UI, making the interface feel integrated into the environment.

---

## 5. Components: Tactile Primitives

### Buttons (The "Brass" Standard)
- **Primary:** Background `secondary`, Text `on_secondary`. Use `rounded-sm` (0.125rem) to maintain a sharp, scholarly edge.
- **Secondary:** Transparent background, `ghost border` (outline-variant at 20% opacity), Text `secondary`.
- **Interaction:** On hover, primary buttons should shift to `secondary_fixed_dim` with a subtle 2px vertical lift.

### Cards & Lists
**Forbid the use of divider lines.** 
- To separate list items, use a `1.5` (0.5rem) vertical gap from the spacing scale. 
- For cards, utilize `surface_container` on top of `background`. If cards are adjacent, use a change in `surface_container_high` to indicate the active state.

### Input Fields
- **Base State:** Use `surface_container_lowest` for the field background to create a "carved-in" look.
- **Focus State:** No thick blue rings. Instead, use a `secondary` (Brass) 1px bottom-border and transition the label text to `secondary`.

### Signature Component: The "Archivist Chip"
For tags and filters, use `tertiary_container` with `on_tertiary_container` text. These should be `rounded-full` to provide a visual counterpoint to the sharp-edged buttons and cards.

---

## 6. Do’s and Don’ts

### Do:
- **Embrace Negative Space:** Use the `16` (5.5rem) and `20` (7rem) spacing tokens to push content away from the edges. High-end design requires room to breathe.
- **Use Tonal Transitions:** If a button feels too loud, drop it to a `tertiary` color profile to sit back in the hierarchy.
- **Respect the Serif:** Use `Newsreader` for any text that is meant to be "read" (articles, quotes, headers). Use `Manrope` for anything meant to be "used" (buttons, inputs, metadata).

### Don't:
- **Don't use Pure Black:** Never use `#000000`. Our depth comes from `#001807` (Dark Forest).
- **Don't use Default Rounding:** Avoid `rounded-lg` for primary containers; it feels too "app-like." Stick to `sm` or `none` for a more bespoke, architectural feel.
- **Don't Over-Animate:** Transitions should be slow and weighted (300ms+, ease-out). No bouncy or "playful" physics; this is a place of study.