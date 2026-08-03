# Reference Images

Use this reference in Phase 4 and during visual comparison in Phases 6, 7, and 9. A reference set is a page-by-page design contract, not loose inspiration.

## Preconditions

Before generating images, have:

- a confirmed or explicitly delegated Product Brief;
- a complete Page and State Map;
- a confirmed project design contract;
- a project `DESIGN.md` when this work creates or changes a multi-page visual system;
- a Page Content Canon for every affected page;
- real content roles and approximate content lengths;
- a list of existing assets and media gaps;
- desktop and mobile first-viewport priorities for every page.

Do not generate a polished homepage while the rest of the product is undefined. Do not ask the image model to invent product scope.

## Direction Probe

When visual direction is not already fixed:

1. Generate two or three probes using the same product facts and content.
2. Change topology, hierarchy, density, image treatment, or typographic voice between probes. Do not make palette-only variants.
3. Show enough content to demonstrate the system beyond the first viewport.
4. Explain the tradeoff of each direction in product terms.
5. Ask the user to choose, combine specific traits, or delegate the decision.

Use one direction approval gate. After approval or delegation, lock the project design contract and produce the full page set. Do not repeatedly pause after every page unless a page reveals a real contradiction.

Skip probes when the user supplied an exact visual target or the repository has an established system. Still produce page references that apply that direction to the requested scope.

## Page Content Canon

Freeze the page's meaning before generating viewport variants. Use stable IDs so the same item can be traced through prompts, references, code, and tests.

```markdown
## Page Content Canon: <route and state>

- User and state:
- Primary task and success action:
- Navigation IDs and labels:
- Content blocks: ID, exact approved copy or data role, priority, required/optional
- Asset IDs: source, subject identity, focal point, allowed desktop/mobile crops
- Controls and CTA IDs: label, outcome, priority
- Invariants across viewports:
- Allowed mobile transforms: reorder, condense, progressive disclosure, alternate crop
- Explicitly prohibited changes:
```

Desktop and mobile references are two compositions of this same canon. Mobile may defer secondary material behind a discoverable control, shorten approved secondary copy, or use a different crop of the same asset when the canon allows it. It may not change product claims, user/data state, core copy, asset subject, navigation meaning, CTA outcome, or required content.

## Reference Matrix

Every planned page receives:

- one named desktop reference at a realistic target viewport;
- one named mobile reference with an independently composed first viewport derived from the same Page Content Canon and asset manifest;
- additional references for critical states whose composition materially differs, such as empty, error, onboarding, editor-fullscreen, checkout confirmation, or destructive recovery.

Pages that share a shell may share navigation and token decisions, but they still need separate references showing their actual content and primary task. Do not call one generic dashboard image a reference for five different routes.

Use filenames that sort and remain traceable:

```text
design/references/01-home-desktop.png
design/references/01-home-mobile.png
design/references/02-sign-in-desktop.png
design/references/02-sign-in-mobile.png
design/references/03-projects-desktop.png
design/references/03-projects-mobile.png
design/references/03-projects-empty-mobile.png
```

Follow repository conventions if a design/reference directory already exists.

## Reference Manifest

Maintain a manifest next to the images:

| ID | Page/route | State | Viewport | Canon version | Primary task | First-viewport content IDs | Shared shell | Required asset IDs/crops | Motion evidence | Semantic UI vs raster | Status |
|---|---|---|---|---|---|---|---|---|---|---|---|

For each image, add implementation notes:

- hierarchy and reading order;
- grid, columns, and max-width behavior;
- mobile reorder/collapse decisions;
- real asset or media roles, subject identity, focal point, crop, object position, mask/edge, layering, and transition state;
- repeated components;
- active theme, color-role hierarchy, semantic status, and visible component states;
- interaction cues, motion evidence, expected states, and start/middle/end transition frames when specified;
- what must remain semantic HTML;
- intentional deviations from the project design contract, if any.

## Prompt Construction

Give the image generator concrete constraints:

1. **Product facts:** audience, job, page purpose, content/data, and state.
2. **Viewport:** exact aspect and intended device context.
3. **Locked inputs:** project `DESIGN.md`, Page Content Canon version, exact content IDs, and exact asset IDs.
4. **Visual system:** Color Role Table, Theme Matrix, Component State Matrix, type character, density, radius, surfaces, icon language, imagery, and signature motif.
5. **Composition:** first viewport, primary action, navigation, content order, and below-fold hint.
6. **Behavioral implications:** what collapses, remains sticky, scrolls, or moves to a secondary surface.
7. **Media contract:** asset subject, focal point, crop, aspect, object position, edge/mask, layering, and visible transition state.
8. **Avoid list:** content invention, asset substitution, card wall, nested cards, fake charts, placeholder panels, generic copy, AI gradients, blobs/orbs, excessive pills, desktop squeezed into mobile.

Generate or approve the desktop reference first. Build the mobile prompt by copying the canon, asset IDs, copy, data state, controls, and shared system verbatim, then describing only the allowed composition transformations. Do not create the mobile prompt from memory or ask the image model to reinterpret the product.

For mobile prompts, state the task priority and invariants explicitly. Example:

```text
Compose a 390x844 mobile sign-in page for a returning user. The first viewport must lead with the product name, sign-in heading, identity fields or provider action, password recovery, and primary sign-in button. Brand imagery may support the page only after the task content is clearly visible. Respect safe areas and the on-screen keyboard. Do not adapt by merely stacking the desktop columns.
```

Append: `Use the same user state, exact approved labels, CTA outcome, content IDs, and asset subject as the desktop reference. Change only the composition and approved crop.`

## Consistency Lock

Keep these invariant across the set unless the Page and State Map says otherwise:

- shell dimensions and navigation behavior;
- palette roles, salience hierarchy, semantic status meaning, theme mappings, and contrast logic;
- type families and role hierarchy;
- spacing scale and density;
- radius, borders, and elevation;
- icon family and stroke weight;
- component shapes and color/state relationships;
- imagery treatment and signature motif;
- mobile navigation and safe-area policy.

If generated pages drift, regenerate the outlier. Do not normalize drift later through improvised code.

## Desktop And Mobile Parity Audit

Audit each pair before approval and coding:

| Contract item | Desktop evidence | Mobile evidence | Allowed transformation | Pass/fail |
|---|---|---|---|---|
| User/data state | | | none unless specified | |
| Content IDs and copy | | | reorder/approved condensation only | |
| Asset IDs and subject | | | approved crop/art direction only | |
| Navigation meaning | | | alternate mobile pattern | |
| CTA labels and outcomes | | | reposition/sticky treatment | |
| Required states | | | viewport-specific presentation | |
| Shared visual system | | | responsive token rules | |

Fail and regenerate when a viewport invents or removes core content, changes a claim, swaps the image subject, changes the represented state, or changes what an action does. Do not resolve a failed pair by implementing two inconsistent products.

## Mobile Reference Requirements

Each mobile reference must answer:

- What is the user's first task, and is it visible immediately?
- What content is reordered, condensed, deferred, or moved behind progressive disclosure?
- Where is the primary action relative to the thumb zone?
- How do navigation, sidebars, tables, filters, and toolbars transform?
- What happens when the keyboard opens?
- How are safe areas and browser chrome handled?
- Are labels, controls, and touch targets still clear without hover?
- Does supporting imagery consume more space than the task deserves?

Reject a mobile reference that is only the desktop design in one column.

## Generated Text Policy

Image models often produce unreliable text. Treat generated text as a layout proxy only.

- Keep approved product copy in a separate content inventory.
- Recreate all interface text as semantic HTML.
- Do not bake buttons, fields, tables, charts, labels, or navigation text into raster assets.
- Do not infer final copy from unreadable generated text.

## Fidelity Inventory

Before coding each reference, inventory every major visible ingredient:

| Ingredient | Role | Implementation source | Required fidelity | Notes |
|---|---|---|---|---|
| Navigation | orientation/action | semantic HTML + existing components | exact hierarchy | mobile variant differs |
| Hero/product media | subject/evidence | existing, sourced, or generated raster | preserve crop and prominence | responsive art direction |
| Chart/table | product information | semantic component/library | preserve hierarchy, use real data | not raster |
| Signature motif | identity | CSS/SVG/canvas/raster | preserve character | keep performant |

Choose one of:

- semantic HTML/CSS;
- existing project component;
- selected open-source component adapted locally;
- icon library;
- existing raster;
- generated or verified sourced raster;
- semantic SVG;
- canvas/WebGL/Three.js;
- accepted omission with user approval.

If the implementation drops the reference's main composition, subject, image role, or signature motif, it is not faithful even when colors and spacing are similar.

For every media ingredient, also record:

```text
Asset ID and subject identity:
Source and license:
Desktop/mobile source or crop:
Aspect ratio and focal point:
Container, edge, mask, and background relationship:
Layer order and overlap:
Reference transition evidence:
State A / midpoint / State B:
Trigger and scroll relationship:
Timing/ease if evidenced or approved:
Reduced-motion result:
```

A static image can define a transition's visual state, crop, overlap, or mask, but it does not by itself authorize invented temporal choreography. Derive timing and movement from supplied video/GIF/prototype, an explicit user request, or an approved Motion Fidelity Manifest.

## Reference-To-Code Comparison

At implementation review, compare:

- first-viewport silhouette;
- primary/secondary hierarchy;
- content density and grouping;
- typography roles and line breaks;
- major image crops and asset presence;
- image edge treatment, layering, overlap, and start/middle/end transition frames;
- navigation and primary action placement;
- section sequence and below-fold signal;
- surface and card usage;
- mobile transformation;
- signature motif and approved motion cues.

Use side-by-side screenshots at the same viewport. Log differences as:

- **Blocking:** changes the page's task, composition, identity, or usability.
- **Material:** visible drift in hierarchy, density, assets, or mobile behavior.
- **Polish:** optical alignment, minor spacing, or subtle state treatment.

Fix blocking and material drift. Do not chase generated pixel noise that would harm semantics, accessibility, responsiveness, or maintainability.

## When Native Image Generation Is Unavailable

State the limitation once. Use one of these fallbacks:

- a user-provided visual target;
- code-rendered high-fidelity static compositions captured as screenshots;
- a structured wireframe set plus the project design contract when high-fidelity generation is impossible.

Do not silently skip the per-page reference contract.
