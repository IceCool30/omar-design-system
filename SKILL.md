---
name: omar-design-system
description: Design and build high-craft websites, web apps, mobile apps, desktop apps, and AI agent interfaces using Omar Farook's (@buildwithomar) anti-AI-slop methodology. Use whenever the user asks to design, redesign, prototype, or audit a UI, landing page, navbar, hero, form, dashboard, mobile screen, desktop app, or AI interface, or asks to avoid generic AI-generated UI.
---

# Omar Design System (@buildwithomar)

Build high-craft, brand-grounded interfaces with AI coding agents by replacing generic one-shot layouts with state-first HTML scratch prototypes, strict visual hierarchy, purposeful motion, and multi-viewport verification.

## When to Use

- Designing or redesigning a website, landing page, SaaS dashboard, desktop app, or mobile app UI.
- Auditing an existing interface to remove generic "AI slop" patterns.
- Building interactive AI agent interfaces, orbs, or status indicators.
- Prototyping new product features or visual effects before touching production code.
- Creating scroll-driven product stories or marketing hero sections.

## Core Workflow

### Step 1: Ground in Brand & Design Tokens First

Never design in a vacuum. Before generating any layout:

1. Extract or confirm the brand's real tokens: primary/surface/muted/accent colors, display and body fonts, button radius, spacing scale (strict 4px/8px "rule of fours"), and logo variants.
2. If working in an existing codebase, read its CSS tokens and component files first so prototypes mirror production styling.
3. Define the product's "world" (its industry, physical/tactile metaphor, and tone) so every visual choice belongs to that brand rather than a generic SaaS template.

### Step 2: Prototype in an Isolated HTML Scratch File

Never dump experimental UI or unverified visual effects straight into production code, and never make the user read a wall of text specs instead of seeing the UI.

1. Read `references/scratch-file-protocol.md` and start from `assets/scratch-template.html`.
2. Build a single, self-contained throwaway HTML file using the app's real CSS tokens.
3. Wire every UI state into a top state-switcher bar: `empty`, `loading`, `populated`, and `error` (plus `thinking`, `working`, `success`, and `stuck` for AI/agent UIs).
4. For any motion, glow, particle, or layout effect, include live HTML range sliders (density, speed, randomness, blur, glow, timing) so the user can dial in exact numbers and lock them into production code.
5. Only port to production framework code after the scratch prototype is approved.

### Step 3: Apply the Anti-AI-Slop Ruleset

Before presenting any design, audit it against `references/anti-slop-checklist.md`. Key non-negotiables:

- **Single-line buttons:** Never allow button labels to wrap onto two lines (`white-space: nowrap`).
- **Real vector icons:** Never use raw Unicode symbols or emojis (`✓`, `✕`) as UI icons; use crisp SVG icons.
- **No lazy left-border card bars:** Replace generic left-accent borders on cards with subtle inner corner radial gradients or clean 1px outlines.
- **Order-of-operations hierarchy:** Group elements by user workflow, fold secondary details into accordions, and group left-nav items under labeled sections with icons.
- **Compact `Cmd+K` search:** Replace oversized top search bars with a compact `Cmd+K` trigger pill that opens a quick-actions modal.
- **Deliberate navbar mode:** Choose either a floating translucent navbar (`8px` padding, `backdrop-filter: blur`, 4-column mega menu with live visual preview) OR a flush technical navbar (100% width, zero radius, zero padding, edge-to-edge borders). Never ship a generic unstyled bar.
- **Purposeful AI states:** Never ship a generic glowing 4-point star orb. Match the AI indicator to the brand and differentiate `thinking`, `working`, `success`, and `stuck` states visually.

### Step 4: Elevate Storytelling & Motion

For landing pages, heroes, and product explainers, read `references/scroll-beat-and-motion.md`:

- Give photography subtle tactile texture (such as halftone treatments) while preserving realism.
- Use scroll-driven 4-beat narratives (`assemble`, `flip`, `split`, `fold`, `3D parts`) where copy and visuals move together and rewind cleanly on scroll up.
- Add purposeful hover delight on primary CTAs (e.g., micro-copy shift + animated icon loop).

### Step 5: Isolate & Orchestrate Complex Assets

For multi-asset pages or complex components, read `references/agent-orchestration-and-handoff.md`:

- Prototype complex effects in isolation before integrating into the main repo to avoid context bloat and hallucinations.
- When delegating visual/image generation or sub-components to worker agents, write tight technical briefs specifying exact dimensions, brand context, and strict simplicity ("one title, one CTA, one on-brand visual").
- Verify layouts at both desktop and mobile breakpoints (including Safari/WebKit scroll smoothness) before finishing.

## Reference Library

- `references/anti-slop-checklist.md`: Concrete component rules for navbars, heroes, forms, dashboards, cards, buttons, icons, and AI states.
- `references/scratch-file-protocol.md`: State-first HTML scratch mockup and parameter-slider tuning workflow.
- `references/scroll-beat-and-motion.md`: 4-beat scroll storytelling model, move vocabulary, and cross-browser verification.
- `references/agent-orchestration-and-handoff.md`: Boss/worker briefing patterns, isolated prototyping, and design-system-as-Markdown conventions.
- `assets/scratch-template.html`: Ready-to-use single-file HTML scratch prototype starter with state switcher and live tuner sliders.
