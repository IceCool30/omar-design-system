# Scroll-Beat Storytelling & Cross-Browser Motion

Derived from Omar Farook's `scroll-beat-kit` architecture for building scroll-driven product stories and motion sections.

## 1. The 4-Beat Narrative Structure

A scroll-beat section pins in place while the user scrolls and plays a 4-beat sequence where copy and visual state move together and rewind cleanly on scroll up.

Before writing code:

1. **Extract brand tokens from the target site/app:** Colors, fonts, button shape, logo, and WCAG contrast.
2. **Propose the 4 beats as a compact table first** (Beat #, Visual Move, Narrative Line) and get approval before building.

## 2. Core Move Vocabulary

- `assemble`: Scattered UI parts snap into a unified product window.
- `flip`: A product window flips to reveal a before/after comparison.
- `spin`: Smooth 3D rotation to highlight depth or a state transition.
- `split-two` / `split-three`: One unified canvas splits into two comparisons or three pricing/feature tiers.
- `fold`: Multiple cards or tiers fold cleanly back into one core element.
- `responsive`: Desktop viewport smoothly morphs into a mobile frame.
- `3d-parts`: Exploded 3D layer view showing how components stack.

## 3. Motion & Timing Rules

- **Move, rest, hand off:** Every beat must have an active transition window, a brief readable rest window so the user can read the copy, and a clean handoff to the next beat.
- **Never overlap text:** Narrator copy blocks must fade/translate cleanly without colliding during fast scroll or reverse scroll.
- **Use GPU-composited properties:** Animate `transform` and `opacity` rather than `top`, `left`, `width`, or `height` to keep 60fps.

## 4. Cross-Browser & Mobile Verification

Before shipping any scroll-driven or motion-heavy page, verify:

1. **Multi-width clipping check:** Inspect at multiple widths (from 375px mobile through 1440px+ desktop) to ensure zero horizontal overflow or clipped labels.
2. **Safari / WebKit address-bar jump guard:** Use `100svh` / `100dvh` carefully and avoid recalculating pinned container heights on minor viewport height changes triggered when the mobile Safari URL bar collapses/expands.
3. **Reduced-motion fallback:** Respect `@media (prefers-reduced-motion: reduce)` by rendering a clean static stacked layout of the beats.
