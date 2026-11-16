# Anti-AI-Slop Design Checklist

Use this checklist to audit every website, web app, desktop app, mobile app, and AI interface before presenting it to the user.

## 1. Visual Hierarchy & Layout Discipline

- **Rule of Fours spacing:** Derive all padding, gaps, and margins from a strict 4px/8px scale (4, 8, 12, 16, 24, 32, 48, 64).
- **Order-of-operations grouping:** Organize screens around the sequence the user actually performs tasks, not database tables. Group related controls visually and fold secondary or rarely used settings into accordions.
- **No generic left-border card stripes:** Avoid the common AI habit of putting a thick colored `border-left` on cards. Highlight active or featured cards with a subtle inner corner radial gradient glow or a crisp 1px border shift instead.
- **Desktop frosted glass layering:** On desktop apps, apply subtle `backdrop-filter: blur(...)` with semi-transparent surfaces on stacked panels and sidebars so background depth seeps through gently.
- **Compact `Cmd+K` search:** Do not place a giant, overbearing search input across the top of an app shell. Use a compact search trigger widget with a `Cmd+K` shortcut badge that opens a focused quick-actions modal.
- **Scannable left navigation:** Fold related links into grouped sections, add uppercase/mono group labels, and pair every primary nav item with a clean icon.

## 2. Typography, Buttons & Icons

- **Single-line buttons:** Buttons must never wrap onto two lines of text. Enforce `white-space: nowrap` and keep button copy concise.
- **Real SVG icons only:** Never render raw Unicode characters (`✓`, `✕`, `→`) or emojis as functional UI icons. Always use clean, consistent-stroke SVG icons.
- **Primary CTA hover delight:** Upgrade primary CTAs from static color shifts to purposeful micro-interactions (for example, shifting the label copy on hover to an outcome-oriented phrase and animating the icon in a subtle loop).
- **Consistent component symmetry:** When two sibling actions exist in the same popover or form (for example, "Due date" and "Add deadline"), use the exact same trigger pattern, button styling, and inline expansion behavior for both.
- **Compact inline popovers:** When picking dates or configuring sub-options inside a popover, expand one inline panel at a time (closing others automatically) so vertical height stays compact.

## 3. Navigation Bar Modes (Pick One Intentionally)

### Mode A: Floating Translucent Navbar (Editorial / Brand-Led)

- Rounded container separated from the viewport edges with `8px` outer/inner padding.
- Translucent background with `backdrop-filter: blur(12px)` so scrolling content blurs softly underneath while nav text remains legible.
- Replace narrow basic dropdowns with a **full-width Mega Menu** flush to the width of the navbar:
  - Use a multi-column grid (3 link columns + 1 visual preview column).
  - Update the 4th column dynamically to show a visual card/image for whichever menu item is currently hovered.

### Mode B: Flush Technical Navbar (Architectural / Precision / SaaS)

- Pinned flush to the top (`top: 0`, `100%` width across every viewport).
- Zero `border-radius`, zero outer padding.
- Make every menu item, divider, and right-edge CTA flush to the top and bottom edges of the bar, with the logo inside a flush top-left container.

## 4. Hero Sections & "Add a World"

- **Tell the product story visually:** Avoid static stock hero photos next to generic H1 + 2 buttons.
- **Tactile photo treatment:** Apply subtle texture (such as a light halftone dot treatment or warm grain) to hero photography while preserving realism.
- **Interactive transformation:** Where applicable, use a scroll-driven or interactive before/after reveal (for example, raw wireframe/sketch on the left transitioning into the finished outcome on the right as the user scrolls).

## 5. Multi-Step Forms & Inputs

- Break long forms into focused, single-intent steps (for example, "Where are you based?" grouping Country, City, and Time zone cleanly) with clear progress and keyboard support.
- Avoid sterile white boxes with default browser inputs; style focus rings, helper text, and validation states using the brand's semantic tokens.

## 6. AI Agent Interfaces & Status Indicators

- **Kill the generic 4-point spark/orb:** Never drop a default glowing orange/purple gradient sphere with a 4-point star into an AI interface.
- **Design a brand-matched motif:** For example, an architectural AI might use a structured dot-matrix sphere or geometric wireframe rather than a soft blob.
- **Choreograph every agent state distinctly:**
  - `Idle / Ready`: Calm, minimal resting state.
  - `Thinking`: Organic pulsing or subtle outward dot protrusion.
  - `Working / Running Tools`: Directional motion (e.g., rotating dot circumferences across multiple angles) paired with live step labels.
  - `Success`: Smooth settle into a slow resting rotation with a soft ambient glow.
  - `Stuck / Needs User Action`: Clear visual lock (e.g., morphing a sphere into a static cube) so the user immediately knows execution is paused for input.
