# Design System Document: The Curated Monolith

## 1. Overview & Creative North Star

The Creative North Star for this design system is **"The Curated Monolith."** 

Unlike standard corporate interfaces that rely on repetitive grids and generic components, this system treats the digital screen as a high-end editorial spread. It captures the essence of JS Consulting—authority, precision, and heritage—through a layout strategy that favors **intentional asymmetry** and **tonal depth**. 

We break the "template" look by using exaggerated whitespace (using our `24` and `20` spacing tokens) and overlapping elements that create a sense of bespoke craftsmanship. The experience should feel like walking through a private gallery: quiet, spacious, and undeniably premium.

---

## 2. Colors: Onyx, Pearl & Champagne

The palette is rooted in a high-contrast relationship between deep charcoals and stark whites, stitched together by the warmth of Champagne Gold.

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning. High-end design is defined by volume and mass, not outlines. Boundaries must be established through:
- **Tonal Shifts:** Transitioning from `surface` (#131313) to `surface_container_low` (#1C1B1B).
- **Whitespace:** Using the `16` (5.5rem) or `20` (7rem) spacing tokens to create mental "rooms" for content.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of premium materials. 
- Use `surface_container_lowest` (#0E0E0E) for the primary background to create an infinite "Onyx" void.
- Nest "Pearl" elements using `surface_bright` or semi-transparent `secondary_fixed` for a frosted glass look.
- **The Glass & Gradient Rule:** For hero sections or primary calls-to-action, use a subtle radial gradient transitioning from `primary` (#F2CA50) to `primary_container` (#D4AF37) at a 45-degree angle. This adds "soul" and prevents the gold from appearing flat or "yellow."

---

## 3. Typography: The Editorial Voice

Our typography is a dialogue between the traditional authority of the Serif and the modern efficiency of the Sans-Serif.

*   **Headlines (Display & Headline Scales):** Utilize **Noto Serif** (as a proxy for Playfair/Cinzel). These should be set with tight letter-spacing and generous line-height. Use `display-lg` for hero statements to command immediate respect.
*   **Body & Utility (Title, Body, & Label Scales):** Utilize **Inter**. This provides a clean, neutral counter-balance to the expressive serif. 
*   **The Identity Play:** We use typography as a structural element. Do not hesitate to use a `label-sm` in all-caps with increased letter-spacing as a category marker above a `headline-lg` to create an "Editorial Tag" aesthetic.

---

## 4. Elevation & Depth

We eschew traditional drop shadows in favor of **Tonal Layering**. Depth is a result of light behavior, not artificial "fuzz."

*   **The Layering Principle:** To lift an element, place a `surface_container_high` card onto a `surface_dim` background. The subtle shift in hex value creates a "soft lift" that feels architectural.
*   **Ambient Shadows:** If a floating element (like a Modal or Dropdown) requires a shadow, it must use the `on_surface` color at 5% opacity with a blur of `32px` or greater. It should feel like an atmospheric glow, not a shadow.
*   **The "Ghost Border" Fallback:** For interactive states (like a focused input), use a "Ghost Border"—the `outline_variant` token at 20% opacity. Never use 100% opacity on borders; it breaks the "Onyx & Pearl" fluid aesthetic.
*   **Glassmorphism:** Use `backdrop-filter: blur(12px)` on containers using semi-transparent `surface_container` tokens. This ensures the "Onyx" background bleeds through, keeping the layout integrated.

---

## 5. Components

### Buttons
- **Primary:** High-contrast. Background: `primary` (#F2CA50); Text: `on_primary` (#3C2F00). Shape: `sm` (0.125rem) for a sharp, tailored look.
- **Secondary:** The "Ghost" style. Background: Transparent; Border: `outline_variant` at 20%; Text: `primary`.
- **Tertiary:** Text-only with a `primary` underline that expands on hover.

### Input Fields
- Avoid boxes. Use a single bottom-border (`outline_variant` at 40%). 
- Labels should use `label-md` and be positioned above the field, never as placeholder text. This maintains a "Consulting Form" professional rigor.

### Cards & Lists
- **Prohibition:** Divider lines between list items are forbidden. 
- **Execution:** Use the Spacing Scale `4` (1.4rem) to separate list items. For cards, use `surface_container_low` with a `0.25rem` (DEFAULT) corner radius. The lack of heavy rounding maintains the "professional/sophisticated" requirement.

### Signature Component: The "Editorial Block"
A custom layout component consisting of a `display-sm` heading overlapping a `secondary_fixed_dim` image container. This creates the "bespoke" feel of a high-end magazine, breaking the rigid verticality of standard web grids.

---

## 6. Do's and Don'ts

### Do:
- **Embrace the Asymmetric:** Offset your text columns. Let a headline hang over the edge of a container.
- **Use "Champagne" Sparingly:** The gold (`primary`) is a highlighter, not a primary fill. Use it for icons, text links, and small accents.
- **Prioritize Legibility:** Ensure `on_background` (#E5E2E1) is used for all long-form body text to maintain high trust and readability against the dark surfaces.

### Don't:
- **Don't use "Round" shapes:** Avoid the `full` (pill) roundedness for buttons. It feels too "App-like" and casual. Stick to `sm` or `none`.
- **Don't use pure Black (#000000) for text:** Use `on_surface` or `on_background`. Pure black on white (or vice versa) is too harsh for a "luxury" experience.
- **Don't crowd the content:** If you feel you need a divider line, you likely need more whitespace instead. Reference the `12` or `16` spacing tokens.