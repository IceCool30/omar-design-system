# Agent Orchestration & Design-System-as-Markdown

How to structure multi-agent workflows and project documentation so any coding agent builds with consistent visual taste.

## 1. Design System as Markdown (Source of Truth)

Maintain a living `DESIGN_SYSTEM.md` (or section in `AGENTS.md` / `CLAUDE.md`) inside the project repo so every agent session inherits the exact rules:

- **Token map:** Exact hex/HSL values, semantic roles (`--bg`, `--surface`, `--fg`, `--muted`, `--accent`), font families, and 4px spacing scale.
- **Component mirror rule:** Keep an isolated `/components` or `/prototype` showcase page wired to the same source components as the main app so style updates propagate everywhere automatically.
- **Explicit negative rules:** List what the agent must NOT do (no Unicode icons, no two-line buttons, no generic left-border stripes, no unapproved new colors).

## 2. Isolate Before Integrating

- When creating a complex visual effect (a dot-matrix orb, a custom chart, a scroll-beat section, or a multi-step form), build it in an isolated scratch file or standalone chat first.
- Feeding an entire repository's context into an early visual experiment wastes tokens and causes the agent to hallucinate or break unrelated files.
- Once the isolated component is visually verified, feed the clean HTML/CSS/JS into the main codebase.

## 3. Boss / Worker Delegation Pattern

When a page requires both layout engineering and custom visual assets (illustrations, product mockups, lifestyle photos, ad creatives):

1. **Boss Agent (Architect / Layout):** Owns the overall page structure, responsive breakpoints, typography, and component integration.
2. **Worker Agent (Asset / Sub-component):** Receives a tight, self-contained brief from the Boss Agent for one task at a time:
   - Brand summary and visual tone.
   - Exact target dimensions / aspect ratio (avoid oversized assets that waste tokens).
   - Strict simplicity rule for promotional/card visuals: **one title, one CTA, one on-brand visual.**
3. **Dual-Breakpoint QA:** After the Boss Agent merges Worker outputs, inspect the final result at both desktop (100% full view) and mobile breakpoints before declaring completion.
