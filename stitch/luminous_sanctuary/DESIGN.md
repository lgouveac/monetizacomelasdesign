# Design System Strategy: The Digital Sanctuary

## 1. Overview & Creative North Star
**Creative North Star: "The Luminous Garden"**

This design system reimagines the interface not as a software tool, but as a living, breathing environment. We are moving away from the rigid, boxed-in constraints of traditional SaaS to create a "Digital Sanctuary." 

To break the "template" look, we utilize **intentional asymmetry** and **organic layering**. By leveraging blob-like geometry and a high-contrast typography scale, we guide the user’s eye through a landscape of information. Elements should feel as though they are floating on different planes of soft, frosted glass, creating a sense of depth that invites interaction rather than demanding it.

---

## 2. Colors
Our palette is a curated selection of nature-inspired tones designed to evoke warmth and tranquility while maintaining a playful, modern energy.

### Color Tokens (Material Design Convention)
- **Primary / Action:** `primary` (#006a2d) and `primary_container` (#6bff8f).
- **Secondary / Warmth:** `secondary` (#705900) and `secondary_container` (#fdd34d).
- **Tertiary / Calm:** `tertiary` (#00628c) and `tertiary_container` (#40bbff).
- **Surface Foundations:** `surface` (#f5f7f5) to `surface_container_highest` (#d9dedb).

### The "No-Line" Rule
**Explicit Instruction:** Solid 1px borders for sectioning are strictly prohibited. Boundaries must be defined solely through background color shifts. For instance, a `surface_container_low` card sits atop a `surface` background. The change in tone is the boundary.

### Surface Hierarchy & Nesting
Treat the UI as physical layers. Use the `surface_container` tiers to create "nested" depth:
1.  **Base Layer:** `background` or `surface`.
2.  **Section Layer:** `surface_container_low` for large content areas.
3.  **Content Cards:** `surface_container_lowest` (Pure White) to create a soft, natural "pop" against the off-white background.

### The "Glass & Gradient" Rule
To elevate the experience, use **Glassmorphism** for floating elements (like navigation bars or hovering action buttons). Use semi-transparent surface colors with a `backdrop-filter: blur(20px)`. 
**Signature Textures:** Incorporate subtle linear gradients transitioning from `primary` to `primary_container` on high-priority CTAs to provide a "soulful" polish that flat color cannot achieve.

---

## 3. Typography
The typography is the voice of the sanctuary: rounded, friendly, and authoritative in its clarity.

- **The Typeface:** **Plus Jakarta Sans**. Its geometric yet soft counters provide a perfect balance of modern professionalism and approachability.
- **Display & Headline Scale:** Use `display-lg` (3.5rem) and `headline-lg` (2rem) with tight letter-spacing (-0.02em) to create editorial-style focal points.
- **Body & Labels:** `body-lg` (1rem) provides ample legibility for long-form wellness content, while `label-md` (0.75rem) is used for meta-data, always in `on_surface_variant` to reduce visual noise.

---

## 4. Elevation & Depth
In this system, depth is a feeling, not a drop-shadow.

- **The Layering Principle:** Depth is achieved by "stacking" surface tiers. A `surface_container_lowest` card on a `surface_container_low` background creates a "lift" that feels organic and light.
- **Ambient Shadows:** Shadows should only be used on elements that physically "float" (like a FAB or a modal). Use the `on_surface` color at 4%–8% opacity with a blur radius of 32px or higher. This mimics natural, ambient light rather than a digital effect.
- **The "Ghost Border" Fallback:** If a border is required for accessibility, it must be a **Ghost Border**: use `outline_variant` at 15% opacity. Never use 100% opaque borders.
- **Organic Geometry:** Use the `xl` (3rem) and `full` (9999px) roundedness scale to soften the corners of containers, making them feel like river stones rather than boxes.

---

## 5. Components

### Buttons
- **Primary:** Gradient fill (`primary` to `primary_dim`), `full` roundedness, `headline-sm` type.
- **Secondary:** `surface_container_highest` background with `on_surface` text. No border.
- **Tertiary:** Text-only with an icon, using `primary` color.

### Input Fields
- **Styling:** Use `surface_container_low` as the field background. On focus, transition to `surface_container_lowest` with a "Ghost Border" of `primary` at 20%. 
- **Shape:** `DEFAULT` (1rem) roundedness.

### Cards & Lists
- **Rule:** Forbid the use of divider lines. 
- **Execution:** Separate list items using `spacing-3` (1rem) of vertical white space or by alternating background tones (`surface_container_low` vs `surface_container_lowest`).

### Chat Bubbles (The Agent Context)
- **User Bubbles:** `primary_container` with `on_primary_container` text.
- **Agent Bubbles:** `surface_container_high` with an organic "blob" shape (asymmetric corner radii, e.g., `2rem 2rem 2rem 0.5rem`).

### Signature Component: "The Ambient Pulse"
A background element using the `tertiary_container` color with a massive blur (100px+) that slowly moves behind the content, creating a sense of life and "pulse" within the app.

---

## 6. Do's and Don'ts

### Do
- **Do** use `spacing-16` and `spacing-20` to create dramatic breathing room between major sections.
- **Do** use asymmetric layouts. If a card is on the left, let a decorative organic shape bleed off the right edge.
- **Do** ensure all interactive elements have a minimum touch target of 44px, despite the "soft" aesthetic.

### Don't
- **Don't** use black (#000000) for text. Always use `on_surface` (#2c2f2e) to maintain the soft tonal range.
- **Don't** use standard Material Design "elevated" shadows. They are too heavy for the "Digital Sanctuary" feel.
- **Don't** use sharp corners (0px-4px). The minimum corner radius for any container should be `sm` (0.5rem).
- **Don't** use dividers to separate content. Let the whitespace do the work.