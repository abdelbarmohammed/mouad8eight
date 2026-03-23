```markdown
# Design System Document: High-End DJ Portfolio

## 1. Overview & Creative North Star: "The Sonic Monolith"
This design system is engineered to capture the raw, industrial prestige of Berlin’s techno scene. The Creative North Star is **The Sonic Monolith**: a visual language that feels architectural, heavy, and immutable. 

We break the "template" look by rejecting standard web grids in favor of **Intentional Asymmetry**. Large-scale typography acts as a physical structure, while generous whitespace (the "void") creates a sense of premium exclusivity. Elements should feel "carved" out of the dark background rather than pasted onto it. By utilizing extreme typographic contrast and tonal depth, we evoke the feeling of a dimly lit, high-end club environment where focus is singular and intense.

---

## 2. Colors & Tonal Depth
The palette is rooted in absolute darkness, using the `surface` tokens to create a sensory, immersive experience.

### The "No-Line" Rule
**Explicit Instruction:** Prohibit the use of 1px solid borders for sectioning. Structural separation must be achieved exclusively through background color shifts. For example, a tracklist section using `surface_container_low` should sit directly against a `background` page, creating a "felt" boundary rather than a seen one.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
- **Base:** `surface` (#131313) for the primary page canvas.
- **Nesting:** Use `surface_container_lowest` (#0e0e0e) to create "sunken" areas for utility content (footer, technical specs). Use `surface_container_high` (#2a2a2a) for elevated elements like active player controls or featured "Hero" cards.

### The "Glass & Accent" Rule
- **Electric Blue (`secondary`):** Use sparingly. This is a surgical strike of color—a "laser in the dark." Reserve it for active states, playback progress, or critical CTAs.
- **Glassmorphism:** For navigation bars or floating music players, use `surface` with 80% opacity and a `20px` backdrop-blur. This allows the high-contrast photography of the artist to bleed through the UI, softening the industrial edges.

---

## 3. Typography: Editorial Brutalism
The typography system relies on the tension between the aggressive, condensed nature of `Space Grotesk` (functioning as our proxy for the "Bebas" impact) and the clinical precision of `Inter`.

- **Display & Headlines (`Space Grotesk`):** These are the architecture. Use `display-lg` for artist names or track titles. Letter-spacing should be set to `-0.02em` to feel compact and "heavy."
- **Body & Labels (`Inter`):** These provide the technical metadata. Use `body-md` for biographies. For technical rider details or track timestamps, use `label-sm` in all-caps with `+0.1em` letter-spacing to mimic industrial labeling.

---

## 4. Elevation & Depth
In this system, depth is a shadow-less transition. We do not use traditional drop shadows; we use **Tonal Layering**.

- **The Layering Principle:** To lift a "Gig Card" from the background, shift the card's background to `surface_container_highest`. The contrast between `#131313` and `#353534` is enough to signify elevation without visual clutter.
- **Ambient Shadows:** If a floating element (like a mobile menu) requires a shadow, use a blur of `40px` with the color `surface_container_lowest` at 50% opacity. It should feel like a soft occlusion of light, not a "web effect."
- **The Ghost Border:** If a boundary is required for accessibility (e.g., input fields), use `outline_variant` at 15% opacity. It should be barely perceptible—a "ghost" of a line.

---

## 5. Components

### Buttons
- **Primary:** `surface_fixed` (White-ish) background with `on_surface_fixed` (Dark) text. Sharp `0px` corners. No hover movement—only a color shift to `secondary` (Electric Blue).
- **Secondary:** Transparent background, `outline` ghost border, `primary` text.
- **Tertiary:** Text only, `label-md` style, with a `secondary` 2px underline that expands on hover.

### Cards & Lists (The DJ Setlist)
- **Rule:** Absolute prohibition of divider lines.
- **Structure:** Use `spacing-8` (2.75rem) to separate list items. A "hover" state on a list item should simply shift the background to `surface_container_low`.

### The "Pulse" Progress Bar (Unique Component)
- **Visual:** A 2px height bar using `surface_variant`. The progress "fill" uses the `secondary` (Electric Blue) with a subtle outer glow (neon effect) using a `4px` blur of the same color.

### Input Fields
- Underline-only style using `outline_variant`. On focus, the underline transforms into `secondary` (Electric Blue). Error states use `error` (#ffb4ab) text only, no red boxes.

---

## 6. Do’s and Don'ts

### Do:
- **Use the Grid for Asymmetry:** Align text to the far left and CTA buttons to the far right with vast empty space in between.
- **Embrace the Dark:** Ensure `on_surface_variant` is used for secondary text to maintain a sophisticated, low-contrast hierarchy.
- **Scale Typography:** Use `display-lg` for section numbers (e.g., "01", "02") to create an editorial feel.

### Don't:
- **No Rounded Corners:** Every element must have a `0px` radius. Rounded corners break the "Berghain" industrial aesthetic.
- **No Standard Gradients:** Avoid any "button gradients." If a gradient is used, it must be a large-scale "aura" in the background, transitioning subtly from `surface` to `surface_container_high`.
- **No Clutter:** If a piece of information isn't vital, remove it. The "void" is a design element itself.

### Accessibility Note:
While the aesthetic is dark, ensure all `primary` text on `surface` backgrounds maintains a contrast ratio of at least 4.5:1. Use the `secondary` (Electric Blue) accent carefully to guide the user's eye to the most critical interactions.```