# Design System Specification

## 1. Overview & Creative North Star: "The Kinetic Sanctuary"
This design system is built upon the concept of **The Kinetic Sanctuary**. In the fitness-tech space, users are often overwhelmed by cluttered dashboards and aggressive red-and-orange "hustle" aesthetics. This system rejects that noise. It prioritizes restorative performance through an "Apple-Editorial" lens—combining the precision of high-end automotive interfaces with the spacious, breathable luxury of a premium wellness lounge.

We break the "template" look by utilizing massive typography scales, intentional asymmetry (e.g., staggering cards or overlapping text onto containers), and a rejection of traditional structural lines. The goal is a UI that feels "carved" out of the darkness rather than "built" on top of it.

---

## 2. Colors: Tonal Architecture
The palette is rooted in deep obsidian tones, punctuated by high-energy electric cyan. We do not use color to decorate; we use it to direct focus.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections or cards. 
*   **Definition through Tonality:** Boundaries must be established solely through background color shifts. For example, a `surface_container_low` card should sit on a `surface` background. 
*   **The Depth Stack:** Use `surface_container_lowest` (#0e0e0e) for the deepest background layers and `surface_container_highest` (#353534) for floating elements.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers.
*   **Nesting:** When a component lives inside another (e.g., a progress chip inside a workout card), the inner component must move one step "up" or "down" the surface tier. 
*   **The Glass & Gradient Rule:** For primary CTAs and high-impact hero sections, use a subtle linear gradient: `primary` (#48f1f0) to `primary_container` (#00d4d4) at a 135-degree angle. This adds "soul" and dimension that flat hex codes lack.

### Signature Textures
Apply Glassmorphism to floating navigation bars or modal overlays:
*   **Fill:** `surface_variant` at 60% opacity.
*   **Effect:** Background blur at 20px–40px.
*   **Result:** This allows the vibrant cyan accents to bleed through the UI, creating a high-end, integrated feel.

---

## 3. Typography: Editorial Authority
We use **Inter** to create a high-contrast, sophisticated hierarchy.

*   **Display & Headline (The Statement):** Use `display-lg` (3.5rem) and `headline-lg` (2rem) with **Bold** weights. These should be left-aligned with tight letter spacing (-0.02em) to mimic premium editorial magazines.
*   **Body (The Clarity):** `body-lg` (1rem) must be used for all primary reading. Increase line-height to 1.6 to ensure the "Spacious" requirement is met.
*   **Labels:** `label-md` should be used sparingly for metadata, always in `on_surface_variant` (#bacac9) to maintain hierarchy.

**Design Strategy:** Don't be afraid of "wasted" space. A massive headline in the top-left with a single piece of data in the bottom-right creates a custom, bespoke feel that standard grids cannot replicate.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are often a crutch for poor contrast. In this system, depth is a product of light and layering.

*   **The Layering Principle:** To lift a card, move it from `surface_container` (#201f1f) to `surface_container_high` (#2a2a2a). The eye perceives the lighter shade as being closer to the light source.
*   **Ambient Shadows:** If a "floating" modal is required, use a shadow with a 40px blur and 6% opacity. The shadow color must be a dark teal-tinted black, not a neutral grey, to maintain the color harmony of the dark environment.
*   **The "Ghost Border" Fallback:** If accessibility requirements demand a container edge, use the `outline_variant` token at 15% opacity. It should be felt, not seen.
*   **Tactile Feedback:** On interaction (hover/active), elements should not just change color; they should "glow." Use a soft outer glow using the `primary` color at 10% opacity to simulate a screen emitting light.

---

## 5. Components: Precision Primitives

### Buttons
*   **Primary:** Solid `primary_container` gradient. Rounded corners at `full` (pill shape). No border.
*   **Secondary:** `surface_container_highest` background with `on_surface` text.
*   **Tertiary:** Text-only in `primary` color, strictly for low-priority actions.

### Cards & Lists
*   **No Dividers:** Forbid the use of line-separators. Use `24px` or `32px` vertical spacing to separate list items. 
*   **Fitness Metrics:** Use `display-sm` for large numerical data (e.g., heart rate, rest time) to give the user immediate visual feedback.

### Input Fields
*   **State:** Background should be `surface_container_lowest`. 
*   **Focus:** Transition the "Ghost Border" from 15% to 100% `primary` opacity. 
*   **Icons:** Use flat line icons only. Ensure stroke weight matches the typography weight (approx 1.5px to 2px).

### Fitness-Tech Specifics: "The Rest Ring"
*   **Data Visualization:** Use the `primary` cyan for "active" data and `surface_variant` for "depleted" or "background" data.
*   **Progress Indicators:** Use non-rounded ends on progress bars for a more "tech-precision" look, contrasted against the heavily rounded corners of the containers.

---

## 6. Do's and Don'ts

### Do:
*   **Left-Align Everything:** Maintain a strong vertical axis for body text to mimic high-end documentation.
*   **Embrace the Dark:** Ensure `background` (#131313) remains the dominant color to reduce eye strain and highlight the cyan accents.
*   **Use Asymmetric Margins:** For example, give a section a 10% left margin but a 20% right margin to create a dynamic, modern rhythm.

### Don't:
*   **Don't use 100% White:** Use `on_surface` (#e5e2e1) for text to avoid "smearing" on OLED screens and to keep the look "premium muted."
*   **Don't use Colored Circles for Icons:** Icons must be "naked" (no circular background) to maintain the Apple-like clean aesthetic.
*   **Don't use Standard Shadows:** Avoid heavy, dark drop-shadows that make the UI feel like a 2014 material design clone.