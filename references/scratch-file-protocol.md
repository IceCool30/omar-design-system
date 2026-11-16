# Scratch-File Prototyping Protocol

Omar Farook's core speed and quality rule: **stop reading verbose agent plans and stop testing visual ideas inside production code.**

## Why Scratch Files Work

1. **Zero token waste:** Agents write single-file HTML/CSS/JS fast and accurately without loading or breaking an entire framework codebase.
2. **Visual alignment first:** Humans can judge a rendered HTML page in 3 seconds, whereas a 500-word technical spec hides layout flaws.
3. **Every edge state up front:** You catch `empty`, `loading`, and `error` layout bugs before writing a single production component.
4. **Exact parameter handoff:** Live sliders let the user dial in exact numbers (blur, density, speed, glow, radius) and hand absolute values back to the agent.

## Rules for Every Scratch File

1. **Single self-contained file:** Put HTML, CSS, and vanilla JS in one standalone `.html` file (start from `assets/scratch-template.html`).
2. **Use real app tokens:** Copy the project's actual CSS variables (colors, typography, radii, shadows) into `:root` so the mockup looks like the real app, not a generic wireframe.
3. **Include a State Switcher bar:** Always provide clickable state pills at the top of the scratch file:
   - Standard UI: `Empty`, `Loading`, `Populated`, `Error`
   - AI / Agent UI: Add `Thinking`, `Working`, `Success`, `Stuck`
4. **Include a Parameter Tuner drawer when designing effects or motion:**
   - Expose 3 to 6 live `<input type="range">` sliders controlling key CSS/JS variables (e.g., `--density`, `--speed`, `--glow`, `--blur`, `--radius`, `--randomness`).
   - Display the live numeric values and provide a "Copy Values" button so the user can paste the exact tuned numbers back into the production prompt.
5. **Port only after approval:** Once the user approves the scratch file and tuned numbers, translate the exact structure and token values into the production framework (React, Next.js, Expo, Framer, etc.).
