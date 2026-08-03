# Color System And Interaction States

Use this reference when defining, implementing, auditing, or repairing palette, hierarchy, semantic feedback, light/dark themes, and component states. Color is a system of roles and relationships, not a collection of attractive swatches.

## Interpret The Principles Correctly

The supplied UI/UX guidance contributes five useful ideas:

1. control the visual share of base, supporting, and accent colors;
2. use salience to guide attention;
3. use conventional status colors to speed recognition;
4. design dark mode instead of mechanically inverting light mode;
5. distinguish interaction states clearly.

Treat these as contextual design principles, not universal formulas. Existing identity, domain conventions, accessibility, cultural context, content, and task risk take precedence.

## Build A Role-Based Color Model

Separate three layers:

1. **Primitive palette:** raw hue, chroma, and lightness steps. Keep these implementation details in token code.
2. **Semantic roles:** canvas, surface, text, border, action, focus, selection, information, success, warning, error, destructive, disabled, and overlay.
3. **Component states:** map semantic roles to each component's default, hover, pressed, focus-visible, selected, disabled, loading, error, and success states.

Do not name reusable tokens after a raw appearance such as `greenButton` or `lightGrayText`. Prefer meanings such as `action-primary`, `status-success-text`, or `control-disabled-surface`. Keep brand accent and status colors separate even when they share a hue.

For every semantic family, define only the roles actually needed:

- foreground/text/icon;
- background or subtle surface;
- border or strong edge;
- solid action or emphasis;
- on-solid foreground;
- hover, pressed, selected, and focus relationships where relevant.

## Use 60-30-10 As A Heuristic

The `60-30-10` rule can be a useful starting hypothesis for a restrained screen:

- roughly 60 percent low-salience base/canvas and open space;
- roughly 30 percent supporting surfaces or identity-bearing color;
- roughly 10 percent high-salience accent and critical emphasis.

Judge visual weight, not literal pixel area. A small saturated button can outweigh a large muted panel. Dense tools, data visualizations, editorial pages, dark themes, photography-led layouts, and established brand systems may need a different balance.

Use the heuristic to diagnose color noise:

- too many saturated regions competing at once;
- primary and secondary actions carrying equal salience;
- every section using its own accent;
- decorative color consuming the attention budget needed by state and action;
- accent color spread so widely that it stops signaling priority.

Never force a valid existing system into exact percentages.

## Create A Salience Hierarchy

Guide attention with a combination of position, spacing, size, typography, luminance contrast, chroma, and color. Do not ask color to repair weak structure.

- Reserve the strongest action salience for the page's current primary task.
- Let secondary actions remain discoverable without competing with the primary action.
- Keep tertiary and repeated controls quieter, especially in dense product surfaces.
- Use saturated color sparingly on operational screens; a brand surface may use a broader color field when the offer remains clear.
- Do not make a destructive action look like the routine primary action. Give it explicit wording and appropriate confirmation or undo behavior.
- Re-evaluate salience in context: the brightest swatch is not always the most visible against its actual background.

Run a grayscale or squint check. The task hierarchy should remain legible when hue is unavailable.

## Semantic Feedback Colors

Common conventions can accelerate recognition:

- success or confirmation often uses green;
- error, danger, or destructive action often uses red;
- warning or pending attention often uses amber/yellow/orange;
- information or neutral progress often uses blue or a product-neutral role.

These mappings are defaults, not meaning by themselves. For every status:

- pair color with clear text and, where useful, an icon or shape;
- distinguish error from destructive action and warning from passive information;
- state what happened and how to recover;
- keep status meaning stable across pages and themes;
- avoid using a brand hue for an incompatible status simply because it is available;
- verify the complete surface/text/border/icon combination, not an isolated swatch;
- do not assume red/green differentiation will be perceivable by every user.

Use neutral status styling when urgency is low. Excessive red, amber, or green creates alarm fatigue and weakens genuinely important feedback.

## Interaction State Matrix

Every relevant control needs a deliberate state relationship:

| State | Required visual/behavioral distinction |
|---|---|
| Default | Stable affordance and readable label |
| Hover | Subtle pointer feedback only on hover-capable devices |
| Pressed/active | Immediate tactile acknowledgement without layout shift |
| Focus-visible | Persistent, high-contrast focus indicator independent of hover |
| Selected/expanded | Clear current state that does not rely on hue alone |
| Disabled/read-only | Unavailable or immutable meaning, still legible and programmatically correct |
| Loading/progress | Stable dimensions, status communication, duplicate-action prevention |
| Validation/error | Field and message relationship plus recovery guidance |
| Success/confirmation | What completed and the next useful action |

Do not create states by applying arbitrary lighter/darker variants. Derive them from a consistent change in surface, border, foreground, elevation, or motion. Keep state contrast visible in light, dark, high-contrast, and forced-colors environments.

Disabled is not a substitute for explaining why an action is unavailable. Prefer leaving a control enabled with useful validation when the user can resolve the problem. When disabled is necessary, do not make essential labels illegible.

## Design Dark Mode As A Theme

Dark mode is a semantic remapping, not color inversion.

- Define dark canvas, surface, elevated surface, text, border, action, focus, selection, and status roles independently.
- Preserve information hierarchy and recognizable brand relationships while adjusting lightness and chroma for the dark surround.
- Avoid large fields of pure black or pure white when a softer neutral improves comfort, unless the product or display context justifies them.
- Do not lower contrast below the project's accessibility target in the name of comfort.
- Re-tune saturated accents and status colors; values that work on white often glow, vibrate, or lose detail on dark surfaces.
- Communicate elevation with controlled surface lightness, borders, and bounded shadows rather than mechanically copying light-theme shadows.
- Verify images, logos, charts, disabled states, overlays, browser chrome, and native controls in both themes.
- Set an intentional theme-loading strategy so the initial render does not flash the wrong theme.

Do not derive dark mode with a global filter, inversion, or automatic hue rotation.

## Data Visualization

When color encodes categories or values:

- choose a palette sized to the actual number of categories;
- preserve category assignments across views and themes;
- use direct labels, patterns, line styles, markers, or grouping when color alone is insufficient;
- reserve semantic red/amber/green for status when mixing status and categorical data;
- test neighboring series, small marks, selected states, and tooltips on their real backgrounds;
- provide a readable table or textual equivalent when the chart carries essential information.

Do not use a rainbow palette merely to make a chart look rich.

## Implementation Contract

- Reuse existing theme and token infrastructure; do not add a parallel color system.
- Keep exact primitive values canonical in code and document semantic intent in `DESIGN.md`.
- Map every component to semantic tokens rather than raw color values.
- Keep light and dark theme parity: the same role may use a different value but must retain its meaning and hierarchy.
- Avoid hard-coded colors in component-local CSS unless the value is genuinely asset-specific and documented.
- Include native control color, `color-scheme`, focus, selection, autofill, placeholder, scrollbar, and system-status behavior where relevant.
- Test state changes without resizing controls or causing layout shift.
- Preserve user theme preference and avoid hydration or first-paint theme flashes.

## Color Verification Gate

At minimum, verify:

1. the primary action remains identifiable without making every action saturated;
2. semantic roles are consistent across pages and components;
3. text, icons, boundaries, focus, and status combinations meet the project's contrast target;
4. no meaning or interactive availability depends on color alone;
5. default, hover, pressed, focus-visible, selected, disabled, loading, error, and success states are distinguishable where relevant;
6. light, dark, high-contrast, forced-colors, grayscale, and common color-vision simulations retain task clarity;
7. status colors remain understandable with long text, localization, CJK, 200 percent zoom, and touch input;
8. charts and legends remain distinguishable in both themes;
9. screenshots at target mobile and desktop viewports show no color noise, accidental competition, or low-contrast content;
10. automated contrast checks are followed by manual inspection of the real rendered state.

Treat failures that hide an action, state, focus indicator, error, or essential content as blocking or major defects, not visual polish.
