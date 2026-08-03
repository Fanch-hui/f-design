# Existing Surface Optimization

Use this reference when a webpage, component, flow, or application already exists and the user asks to optimize layout, typography, visual design, responsiveness, accessibility, consistency, standards, or overall quality. Preserve working behavior and identity while removing verified defects.

## Contents

- [Choose The Optimization Mode](#choose-the-optimization-mode)
- [Establish The Contract](#establish-the-contract)
- [Capture The Baseline](#capture-the-baseline)
- [Diagnose Root Causes](#diagnose-root-causes)
- [Prioritize Findings](#prioritize-findings)
- [Optimization Passes](#optimization-passes)
- [Reference Image Decision](#reference-image-decision)
- [Before And After Verification](#before-and-after-verification)
- [Delivery Contract](#delivery-contract)
- [Prohibited Behavior](#prohibited-behavior)

## Choose The Optimization Mode

Select the smallest mode that matches the request:

### Tune-Up

Use when the product direction is sound but execution is rough. Improve hierarchy, layout, spacing, typography, component consistency, responsive behavior, states, accessibility, and polish. Keep architecture and visual identity intact. The existing page and before screenshots are the visual baseline.

### Structural Improvement

Use when the page works but information architecture, workflow shape, content priority, or mobile composition is wrong. Reorganize the surface while preserving product scope, data behavior, and recognizable identity. Confirm material changes to user flow before implementation when the intent is not clear.

### Visual Redesign

Use when the user explicitly requests a new direction or the current design system fundamentally prevents the desired outcome. Document what remains, what changes, and why. Generate approved desktop and mobile references before broad implementation.

### Standards Repair

Use when the primary need is accessibility, responsiveness, metadata, performance, state coverage, design-system drift, or code quality. Fix standards defects without unnecessary visual churn.

Do not turn every request into a redesign. Do not limit a redesign request to tiny cosmetic patches.

## Establish The Contract

Before changing files, determine:

- page/surface and primary task;
- target audience and usage context;
- existing visual identity and design evidence;
- shared tokens, components, icons, motion, and layout patterns;
- functional behaviors and states that must remain unchanged;
- known user-authored or in-progress changes;
- supported viewports, browsers, languages, and accessibility requirements;
- requested quality level and scope;
- explicit anti-goals and out-of-scope areas.

Use repository evidence first: product/design docs, existing neighboring pages, tokens, components, assets, screenshots, tests, and source history when useful. For structural improvement or visual redesign, run the guided Discovery Gate in `discovery-and-architecture.md` before presenting a new direction or coding it. A tune-up or standards repair should not force an interview when the contract is already evident.

Write a compact contract:

```text
Target surface:
Primary task:
Optimization mode:
Identity and behavior to preserve:
Evidence that defines the system:
Requested improvements:
Out of scope:
Viewports/states to verify:
```

## Capture The Baseline

Start the real development server. Do not audit source code in isolation when the surface can render.

Capture and inspect:

- initial desktop viewport;
- wide desktop if max-width behavior matters;
- tablet portrait and landscape;
- phone at 320, 375/390, and 430 pixels;
- primary interaction flow;
- navigation, overlays, menus, forms, and sticky/fixed UI;
- loading, empty, error, success, disabled, permission, and long-content states that can occur;
- keyboard focus path and reduced motion;
- current interaction feedback, async status, view continuity, media transitions, and any brand/signature sequence;
- soft keyboard or realistic mobile form behavior when relevant.

Read every screenshot you create. Record observable symptoms and source ownership. A screenshot path without visual inspection is not evidence.

When the page is long, capture major sections separately. A scaled full-page thumbnail hides spacing, clipping, and hierarchy defects.

Reconcile documented intent with rendered reality before treating either as truth:

| Rule/surface | Intended evidence | Rendered observation | Code owner | Confidence: verified/inferred/proposed | Intentional / code drift / docs stale | Action |
|---|---|---|---|---|---|---|

When changing a shared token or component, identify its consumers and verify representative neighboring surfaces. Update the project `DESIGN.md` only when the change creates a durable rule; do not record one-off polish as a system principle.

## Diagnose Root Causes

Classify each issue before editing.

### Product And Information Architecture

- wrong primary task or action;
- unclear entry, next step, cancellation, or completion;
- competing actions with equal emphasis;
- necessary decision context separated from the action;
- dashboard framing where a list, report, workflow, or creation surface fits better;
- excessive choices or unnecessary steps;
- mobile first viewport serving decoration instead of the task.

### Layout And Composition

- arbitrary spacing or one gap used everywhere;
- weak grouping and alignment;
- inappropriate grid, column count, max-width, or density;
- card walls, nested cards, or unnecessary framed sections;
- content stretching on wide screens;
- fixed dimensions that break realistic data;
- decorative empty space displacing important content;
- unstable dimensions across loading, hover, focus, or dynamic states.

### Typography And Content

- unclear role hierarchy;
- too many nearby sizes or weights;
- display typography used in controls or data;
- unreadable line length, line height, or mobile size;
- viewport-proportional type that becomes too large or too small;
- negative/tracked letter spacing used as decoration;
- long labels, translations, CJK, or identifiers overflowing;
- vague buttons, redundant explanation, inconsistent terminology, or unrecoverable errors.

### Visual System

- hard-coded values bypassing tokens;
- inconsistent color meaning, radius, border, shadow, icon, or surface treatment;
- saturated color spread across too many regions, leaving no clear attention hierarchy;
- brand, primary action, focus, selection, status, and destructive colors sharing ambiguous meaning;
- light/dark themes produced by inversion or local overrides instead of semantic mappings;
- state or feedback meaning conveyed only by red/green/yellow or by lighter/darker color;
- a generic one-note palette or AI-gradient treatment;
- low contrast or gray text on colored surfaces;
- a new component visually importing another product's design language;
- imagery that is decorative when users need to inspect a real product, place, object, or state.
- imagery inserted as an isolated rectangle without preserving reference crop, focal point, edge, overlap, or background relationship;
- image or section transitions reduced to generic fades despite approved reference evidence.

### Components And Interaction

- duplicate primitives or competing component systems;
- missing hover, focus-visible, active, disabled, loading, error, or success states;
- divs acting as buttons, placeholder-only labels, or hover-only functionality;
- clipped overlays and incorrect focus trap/restoration;
- unstable controls or content shift during interaction;
- custom behavior where a mature accessible primitive would lower risk.

### Responsive And Mobile

- desktop compressed into one column without reprioritization;
- wrong first-viewport content;
- horizontal overflow, clipping, overlap, or excessive fixed/sticky space;
- desktop tables, sidebars, filters, or toolbars made tiny instead of transformed;
- action placement outside useful reach;
- keyboard, safe area, browser chrome, or orientation covering content;
- touch targets below practical size or controls depending on hover.

### Standards And Engineering

- semantic/accessibility failures;
- missing realistic states and recovery;
- broken metadata or asset provenance;
- layout shift, oversized media, avoidable JavaScript, or motion jank;
- console, hydration, build, type, lint, or test failures;
- duplicated styles, orphaned code, or abstractions that no longer match use.

Name the root cause as one of:

- missing or incorrect product decision;
- design-system drift;
- missing shared token/component;
- one-off implementation;
- responsive composition failure;
- incomplete state/accessibility behavior;
- content problem;
- performance/engineering defect.

Fix the cause, not only the visible symptom.

## Prioritize Findings

Use impact and sequence:

1. **P0:** primary task blocked, data loss, blank render, or dangerous behavior.
2. **P1:** major confusion, WCAG failure, mobile first-viewport failure, clipping/overlap, broken navigation/state, or severe responsive defect.
3. **P2:** material hierarchy, layout, typography, design-system, content, or performance problem with a workaround.
4. **P3:** optical alignment and small polish with no task impact.

Prioritize in this order:

1. function and task clarity;
2. mobile/accessibility blockers;
3. structure and hierarchy;
4. design-system consistency;
5. responsive behavior and state completeness;
6. typography, color, imagery, and component craft;
7. purposeful motion and final polish.

When the user asks for optimization, implement the verified items that fit scope. A findings-only report is incomplete unless the user explicitly asked for an audit or plan.

## Optimization Passes

### Pass 1: Structure And Hierarchy

- Make the page's purpose and primary action obvious.
- Remove, defer, or regroup competing secondary content.
- Match navigation and flow shape to neighboring product surfaces.
- Use progressive disclosure only when the hidden content remains discoverable and available at the decision point.
- Replace unnecessary dialogs with inline or route-based flow when that improves context.
- Preserve URLs, data ownership, and expected behavior unless the change is explicitly in scope.

### Pass 2: Layout And Rhythm

- Establish a consistent spacing scale and use `gap` for sibling relationships.
- Tighten related elements and separate distinct groups.
- Choose grid, flex, table, list, or direct flow from content relationships.
- Set max-width, columns, aspect ratios, and stable dimensions intentionally.
- Remove card wrappers that fail the card decision test; never nest cards.
- Align visually and optically without speculative nudges.
- Keep page sections unframed unless a real boundary is needed.

### Pass 3: Typography And Copy

- Define a small role-based type scale using project tokens.
- Strengthen hierarchy through size, weight, position, and space.
- Keep body text readable and prose roughly 45-75 characters wide.
- Use stable `rem` sizes with explicit responsive steps, not viewport-proportional type.
- Keep letter spacing at `0`.
- Use one product UI family unless the existing brand requires a second.
- Fix labels, buttons, empty states, errors, and terminology at the same time as layout so text and containers are tested together.

### Pass 4: Visual System Alignment

- Reuse or repair semantic tokens instead of adding local color values.
- Normalize radius, border, surface, shadow, icon, focus, and status treatment.
- Preserve existing identity before introducing a new visual language.
- Use color for meaning and hierarchy, not decoration.
- Replace generic gradients, blobs/orbs, fake metrics, and filler imagery with real product evidence or intentional restraint.
- Keep controls recognizable and use the project's icon family.
- Reconcile lasting design rules with the nearest project `DESIGN.md`; mark uncertain observations as verified, inferred, or proposed.

### Pass 4A: Color System And States

- Inventory primitive values, semantic roles, theme mappings, and component state usage before changing swatches.
- Use `60-30-10` only to diagnose base/support/accent visual weight; do not force literal percentages.
- Reserve the strongest salience for the primary task and reduce accidental competition from repeated or decorative accents.
- Separate brand, action, focus, selection, information, success, warning, error, and destructive roles.
- Pair status color with text, icon, shape, border, or another persistent cue.
- Complete default, hover, pressed, focus-visible, selected, disabled, loading, validation/error, and success mappings where relevant.
- Rebuild dark mode as semantic token mappings rather than inversion; check theme preference and first-paint behavior.
- Verify light/dark, grayscale, high-contrast, forced-colors, and common color-vision conditions. Follow `color-system-and-states.md`.

### Pass 4B: Media Integration

- Map each prominent image to an asset ID, product role, focal point, desktop/mobile crop, edge treatment, layering, and loading fallback.
- Rebuild the surrounding composition when the image currently feels appended; do not solve it only with radius, shadow, or a card wrapper.
- Preserve the same subject across responsive art direction unless product requirements explicitly change it.
- When approved evidence contains a transition, specify State A, midpoint, State B, trigger, timing or scroll range, responsive variant, and reduced-motion result before implementation.
- Verify static endpoints first, then follow `media-and-image-transitions.md` and the motion phase.

### Pass 5: Components And Open Source

- Create or update the Component Decision Register. Include every nontrivial primitive and explicitly record an existing/local decision when no dependency is added.
- Replace duplicate local implementations with an existing shared primitive when behavior matches.
- Extract only patterns repeated with the same intent or accessibility behavior.
- Research mature GitHub components only for nontrivial behavior that the project lacks.
- Verify popularity, maintenance, license, accessibility, compatibility, cost, and theming.
- Wrap and restyle selected components so they consume local tokens and interaction conventions.
- Do not add a full component system for one widget.

### Pass 6: Responsive And Mobile Composition

- Write the phone first-viewport priority before changing CSS.
- Reorder, condense, collapse, or reposition content from the user's mobile task.
- Transform navigation, sidebars, tables, filters, charts, and toolbars instead of shrinking them.
- Reserve space for sticky/fixed controls and safe areas.
- Test the virtual keyboard and active form controls.
- Fix the owner of overflow instead of hiding page overflow globally.
- Confirm 320, 375/390, 430, tablet, 1280, and 1440+ behavior.

### Pass 7: States, Accessibility, And Resilience

- Complete relevant default, hover, focus-visible, active, disabled, loading, empty, error, success, permission, offline, and long-content states.
- Use semantic elements and accessible names.
- Verify keyboard flow, focus management, announcements, contrast, zoom, touch targets, and reduced motion.
- Preserve user input and provide recovery.
- Test realistic minimum, typical, maximum, translation, CJK, and interrupted states.

### Pass 8: Motion And Performance

- Add or refine motion only after layout and states are stable.
- Create a Motion Coverage Matrix across direct controls, state/overlays, async feedback, navigation/layout, media, and brand/narrative motion. Every category needs an implementation, a concrete `not applicable` reason, or an accepted omission.
- Create a Motion Fidelity Manifest and implement every approved reference cue or record an accepted omission. Motion is not optional when the approved direction depends on it.
- Do not call the motion pass complete with only a button press and toast fade when the approved surface is expressive, image-led, or contains reference choreography.
- Keep frequent product actions fast and state-led.
- Remove animation without a named purpose.
- Avoid `transition: all`, casual layout animation, unbounded blur/filter, and offscreen loops.
- Measure actual bottlenecks before optimizing bundles or rendering.
- Verify frame stability, LCP, INP, CLS, assets, and console behavior where relevant.

## Reference Image Decision

Use the existing live page and before screenshots as the baseline for tune-ups and standards repair.

Generate new references when:

- the user requests a redesign or alternate direction;
- the existing hierarchy/composition is fundamentally wrong;
- several pages need one newly defined visual system;
- a major new page or flow has no visual evidence;
- image-led composition cannot be resolved safely in code alone.

Do not generate references only to adjust spacing, typography, responsive behavior, component states, accessibility, metadata, or performance. When references are needed, create desktop and dedicated mobile references from the same Page Content Canon for every affected page and preserve approved existing identity where required. Reject a pair that changes core copy, data/state, asset subject, navigation meaning, or action outcome between viewports.

## Before And After Verification

Capture matching before and after screenshots at identical viewports and states. Compare:

- first-viewport task clarity;
- reading order and hierarchy;
- layout silhouette, density, and grouping;
- typography and content fit;
- card/container count and nesting;
- design-system consistency;
- mobile reordering and action visibility;
- clipping, overlap, overflow, and sticky behavior;
- interaction states and focus;
- color hierarchy, semantic status, component states, and light/dark theme parity;
- visual identity and real assets.
- image crop, focal point, edge treatment, layering, and transition endpoints/keyframes;
- desktop/mobile content and asset parity.

Then run:

- repository format, lint, typecheck, tests, and production build;
- console and failed-network checks;
- keyboard and primary flow walkthrough;
- accessibility tooling plus manual verification;
- responsive viewport matrix;
- reduced motion and important error/empty/loading states;
- light/dark, grayscale, high-contrast, forced-colors, and relevant color-vision checks;
- performance measurements when the change can affect them.

Do not declare improvement from code diffs alone. The after state must be visibly and behaviorally better without an unintended regression.

## Delivery Contract

Report:

- target and optimization mode;
- root causes fixed, ordered by user impact;
- important layout, typography, visual-system, responsive, and standards changes;
- before/after viewports and states inspected;
- build/tests/accessibility checks run;
- open-source component provenance and adaptations, if any;
- component decisions when no dependency was added, including what was evaluated and why existing/local implementation was selected;
- Motion Coverage Matrix summary, Motion Fidelity Manifest status, and reduced-motion result;
- functionality or identity deliberately preserved;
- remaining risks or device/browser checks not run;
- development URL or openable file.

## Prohibited Behavior

- Do not rewrite the whole interface to express personal taste.
- Do not erase a recognizable identity during a polish request.
- Do not stop at recommendations when implementation was requested.
- Do not fix isolated pixels while leaving the wrong hierarchy or flow.
- Do not wrap every section in cards or convert mobile rows to cards by default.
- Do not add dependencies before checking existing primitives.
- Do not generate a new design system from accidental one-off code.
- Do not claim browser, device, accessibility, or performance verification that was not run.
- Do not improve desktop while leaving mobile as a squeezed derivative.
- Do not add motion before function, layout, states, and responsiveness are stable.
