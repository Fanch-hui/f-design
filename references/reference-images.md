# Reference Images

Use this reference for user-supplied visual targets and for pages selected under generated-reference or hybrid delivery mode. Do not load it merely because a direct implementation will produce browser QA screenshots. A generated reference set visualizes an already approved Design Package; it does not create the product scope or design system.

## User-Supplied Website Or Upload

Accept references through uploaded screenshots, mockups, design files, GIFs, recordings, public website URLs, localhost/current pages, or a user-authored combination. Do not reduce the choice to a fixed list of style adjectives.

When the user provides a website URL, inspect the live page before visual analysis when tools and access permit. Record the URL, date, viewport, route/state, and what the user wants to emulate. Capture representative desktop and mobile states separately; inspect navigation, overlays, responsive transformations, image crops, and motion instead of relying only on the first static viewport. If access is blocked or partial, state exactly what was and was not observed and ask for screenshots or a recording rather than inventing evidence.

Separate imitation targets into:

- structure and information architecture;
- hierarchy, spacing, typography, palette, and material treatment;
- component and interaction behavior;
- image identity, crop, layering, and transitions;
- motion choreography and timing evidence;
- content, brand assets, trademarks, or unique expression that must not be copied.

A reference website is evidence, not a license. Recreate approved principles and behavior in the target project's identity. Do not copy proprietary text, trademarks, unique illustrations, photography, source code, or remote assets without permission. Do not hotlink assets. Preserve attribution and license requirements for any reusable public resource.

## Preconditions

Before generating images, complete the shared [Design Package](visual-system.md#design-package) and resolve the delivery mode, reference intake, and architecture choices in [discovery-and-architecture.md](discovery-and-architecture.md). The delivery-mode record must name the pages/states selected for generated references. Reuse the package's content canon, asset inventory, media gaps, and desktop/mobile priorities.

Do not generate a polished homepage while the product, page scope, visual system, responsive rules, media intent, or content canon remain undefined. Do not ask the image model to invent product scope or make unresolved design decisions. Direct implementation pages stop here and do not create generated artifacts.

## Design Before Image Generation

Resolve structure through the Surface Strategy Record and any required Structural Direction Matrix before resolving visual direction through the Product Brief, visual-system alternatives, layout plans or wireframes, token/type/media decisions, responsive composition, and the project design contract. Then approve or explicitly delegate the complete Design Package.

Only after that approval may generated-reference or hybrid pages be rendered. Generated page images must visualize the selected design; they may not choose the layout, palette, component language, content, or product scope. If an image exposes a contradiction, correct the Design Package first and regenerate from it rather than treating image drift as a new design decision.

## Page Content Canon

Use the shared [Page Content Canon](discovery-and-architecture.md#page-content-canon). Generated desktop and mobile references must visualize that same canon; the parity audit below checks the selected reference set without creating another source of content truth.

## Reference Matrix

Every page/state selected for generated references receives:

- one named desktop reference at a realistic target viewport;
- one named mobile reference with an independently composed first viewport derived from the same Page Content Canon and asset manifest;
- additional references for critical states whose composition materially differs, such as empty, error, onboarding, editor-fullscreen, checkout confirmation, or destructive recovery.

Selected pages that share a shell may share navigation and token decisions, but they still need separate references showing their actual content and primary task. Direct pages require no generated image. Do not call one generic dashboard image a reference for five different routes.

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

Run this comparison only for generated-reference pages or when the user explicitly requested fidelity to a supplied visual target. At implementation review, compare:

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

If the user selected generated-reference or hybrid mode for affected pages, state the limitation once and ask whether to switch those pages to direct implementation, wait for an image-capable tool, or use one of these explicit fallbacks:

- a user-provided visual target;
- code-rendered high-fidelity static compositions captured as screenshots;
- a structured wireframe set plus the project design contract when high-fidelity generation is impossible.

Do not silently change the selected mode. Direct implementation is a valid user-approved mode, not a failure or fallback artifact.
