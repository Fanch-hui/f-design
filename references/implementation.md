# Implementation Contract

Use this reference in Phase 6. Translate the approved references into a production interface without losing product logic, mobile intent, accessibility, or the existing codebase's identity.

## Before Editing

- Confirm the target routes and shared shell.
- Read the files that own nearby behavior and styling.
- Recheck existing components, tokens, icons, utilities, and tests.
- Inventory approved reference ingredients, Page Content Canon IDs, media/transition contracts, the Component Decision Register, and the draft Motion Coverage Matrix.
- Start or update the Phase Accountability Ledger; give every applicable implementation pass an owner, status, and intended verification evidence.
- Identify user-authored changes in the worktree and preserve them.
- State the files and behavior you are about to change.

Edit source files, not generated output. Respect the existing build and formatting pipeline.

## Pass 1: Semantic Structure And Flow

Build the interaction skeleton first:

- correct routes, landmarks, heading hierarchy, regions, and reading order;
- real links for navigation and buttons for actions;
- primary action in the intended first viewport;
- forms with persistent labels and meaningful input types;
- lists, tables, figures, details, dialogs, and status regions with native semantics where possible;
- correct data ownership and event flow;
- cancellation, recovery, undo, and next-action paths.

Do not style around broken information architecture. If implementation reveals a page-map contradiction, resolve it before adding polish.

## Pass 2: Tokens And Visual System

Map the project `DESIGN.md` or confirmed design contract to project conventions:

- semantic color tokens;
- Color Role Table, Theme Matrix, and Component State Matrix mapped to the project's existing token architecture;
- typography roles and font loading;
- spacing/density scale;
- grid, containers, and layout constraints;
- radius, border, surface, and elevation roles;
- icon size/stroke and asset treatment;
- focus, selection, semantic status, and overlay layers;
- motion tokens reserved for Phase 8.

Avoid hard-coded one-offs when a semantic token exists. Add a token only when a value repeats with the same meaning. Do not create a token for every number.

Keep primitive values, semantic roles, and component mappings separate. Do not create dark mode with global inversion or filters. Preserve user theme preference, set an intentional `color-scheme`, and prevent a wrong-theme first-paint flash where the stack supports it. Follow `color-system-and-states.md`.

## Pass 3: Components And States

Implement components at the ownership boundary implied by the repository:

- reuse shared components first;
- adapt selected open-source primitives behind stable local styling and defaults;
- implement the recorded Component Decision Register; if a new nontrivial need appears, update the register before hand-rolling or installing it;
- extract a new shared component when the same intent repeats at least three times or when accessibility behavior must be centralized;
- keep one-off page compositions local;
- do not build abstractions that merely hide simple markup.

Every relevant interactive component needs:

- default;
- hover only when a hover-capable pointer exists;
- focus-visible;
- active/pressed;
- selected/expanded when relevant;
- disabled/read-only;
- loading/progress;
- validation/error;
- success/confirmation.

Keep dimensions stable across states. A spinner, error label, icon, or count must not resize the button, tile, board, or toolbar unexpectedly.

State changes must use a consistent combination of foreground, surface, border, outline, icon, text, elevation, or motion. Hue may reinforce meaning but may not be the only indication of availability, focus, selection, validation, success, warning, error, or destructive intent. Hover applies only to hover-capable input; focus-visible remains independently obvious.

### Component Responsibility And State Ownership

- Prefer small composable parts over one component controlled by many unrelated flags.
- Keep one-off page composition local; share behavior or structure only when the same intent repeats or a critical accessibility contract needs one owner.
- Separate data fetching, mutation, permissions, navigation, and workflow orchestration from presentation when combining them obscures responsibility or makes states hard to test.
- Place state at the narrowest durable owner: component-local, lifted to the nearest shared parent, shared context, URL, server cache/state, then global store only when the earlier levels cannot represent the ownership correctly.
- Follow repository conventions for colocating implementation, styles, hooks, types, tests, and stories/examples.
- Use optimistic updates only for low-risk reversible changes, provide rollback and error recovery, and keep the authoritative server result visible.

When a shared component or token changes, follow `design-system-governance.md` and verify representative consumers. Do not treat a page-specific generated style as a new global default.

## Generated And Reference-Led Iteration

Choose the smallest iteration mode that solves the verified problem:

- **targeted edit:** change named regions, assets, states, tokens, copy, or behavior while locking the approved architecture and identity;
- **variant exploration:** compare explicit approved axes such as local composition, palette, imagery, typography, content density, or motion while locking everything else; if primary task path, information architecture, navigation, or object relationships may change, reopen the structural-exploration gate instead;
- **full regeneration:** use only when the governing hierarchy, architecture, or visual thesis is wrong.

For every mode, restate the page purpose, platform, content canon, structure, locked system decisions, and exact allowed changes. Prefer targeted edits after the core direction is approved. Surface useful generation or inspection findings to the user; do not silently broaden the redesign.

## Pass 4: Real Content And Data

- Use actual product copy or credible domain-specific content.
- Use realistic minimum, typical, and maximum data.
- Preserve user input across errors and navigation where expected.
- Use `Intl` and the project's localization system for dates, time, numbers, currency, and pluralization.
- Use logical CSS properties where RTL may apply.
- Keep terminology consistent across routes.
- Never ship fake metrics, decorative charts, inert controls, dead links, or filler testimonials.

For large data:

- paginate, stream, or virtualize as appropriate;
- keep filters and sorting recoverable and shareable when valuable;
- use tabular numbers and stable columns;
- provide empty, loading, stale, and error behavior;
- preserve keyboard efficiency and bulk actions for frequent workflows.

## Pass 5: Assets And Media

- Use the approved reference inventory to source each asset.
- Preserve the asset subject identity, product role, focal point, crop intent, edge/mask, background relationship, layer order, overlap, and prominence recorded in the Page Content Canon and media contract.
- Verify remote assets and license before use.
- Store required project assets inside the project unless the architecture intentionally uses a trusted CDN.
- Set intrinsic dimensions or aspect ratio.
- Use `<picture>`, responsive image APIs, or framework image primitives for materially different mobile sources and crops while preserving the same approved subject.
- Preload/decode transition-critical incoming media before playback. Keep stable stacked layers or explicit shared-element ownership instead of changing an unresolved `src` mid-transition.
- Lazy-load below-fold media, not the LCP image.
- Use useful alt text for informative images and empty alt for decoration.
- Keep UI text, buttons, forms, data, and core diagrams semantic instead of baking them into images.

Implement and verify the static start and end compositions before animation. Do not place media in a generic rounded container merely because its compositional relationship is unresolved. Follow `media-and-image-transitions.md` for prominent media and approved transitions.

For a 3D experience, use Three.js or the established project renderer. Keep the primary scene full-bleed or unframed, not inside a decorative card. Verify rendered pixels on desktop and mobile, interaction, framing, movement, and fallback behavior.

## Pass 6: Responsive Composition

Implement the mobile reference as an explicit composition:

- reorder DOM where reading and focus order require it;
- collapse or replace navigation intentionally;
- transform sidebars into a suitable mobile pattern;
- shorten or defer secondary content without hiding core functionality;
- move primary actions into reachable locations when the workflow benefits;
- redesign tables, filters, charts, and toolbars for the task rather than stacking them blindly;
- support safe areas, browser chrome, orientation, and soft keyboard;
- reserve space for fixed/sticky elements so content is never covered.

Then implement tablet and desktop. Use content-driven breakpoints and container queries where component context matters. Do not use device detection for layout.

Read `responsive-mobile.md` for the complete audit.

## Card Audit During Implementation

For every bordered, elevated, rounded, or tinted container, ask:

1. Is this content an independent object or interaction context?
2. Does the boundary help the user scan, compare, select, move, or act?
3. Would spacing, alignment, a row, divider, band, table, or list communicate the relationship more directly?
4. Is this container nested inside another card?
5. Does this page now read as a grid of boxes rather than a coherent workflow?

Remove unearned containers immediately. Do not wait for final polish.

## Forms And High-Stakes Actions

- Keep labels visible; placeholders are examples, not labels.
- Use native autocomplete, input mode, and password-manager semantics.
- Validate at a useful moment, usually blur or submit rather than every keystroke.
- Connect errors to fields and place them nearby.
- Preserve entered values after failure.
- Focus the first invalid field after submit and summarize when many errors exist.
- Prevent duplicate submission.
- Prefer undo for reversible deletion. Confirm only irreversible, high-cost, or batch actions.
- Name destructive buttons specifically.
- Do not use optimistic UI for payments or irreversible operations.

## Overlays And Navigation

- Prefer native or mature accessible primitives.
- Trap focus only for modal contexts and restore it to the trigger on close.
- Support Escape and explicit close where expected.
- Use portals/top-layer behavior to avoid clipping in overflow containers.
- Reposition or flip overlays at viewport edges.
- Do not rely on gestures or hover as the only access path.
- Keep current location and back/cancel routes obvious.

## Accessibility Baseline

- Semantic HTML before ARIA.
- One accessible name per control; icon-only controls need meaningful labels.
- Logical headings and landmarks.
- Complete keyboard flow with visible focus.
- Correct tab/arrow-key model for composite widgets.
- Live announcements for async status, errors, and success where needed.
- Text contrast at least WCAG AA and non-text UI contrast where required.
- Color is never the only signal.
- Touch targets at least 44 by 44 CSS pixels where practical.
- Layout and content work at 200% zoom and with user font settings.
- No time limit without a mechanism to extend or disable it when required.
- Reduced-motion alternative retains meaning and function.
- Light/dark, high-contrast, forced-colors, grayscale, and color-vision checks preserve task, focus, status, and state clarity where relevant.

## Resilience Baseline

Test and implement:

- empty first use, empty search/filter, and no-permission;
- initial loading, background refresh, and partial component failure;
- network timeout/offline, 401/403/404/429/500 as relevant;
- minimum and maximum content, long unbroken strings, CJK, emoji, and translation expansion;
- very large collections and concurrent actions;
- refresh/back navigation mid-flow and draft restoration;
- missing/failed images and unsupported browser features;
- read-only and stale-data states.

Do not block the whole page because one independent region failed.

## Metadata And Document Quality

For public routes, include and verify:

- unique page title and description;
- canonical URL policy;
- Open Graph and social preview metadata;
- correct locale and language;
- icons and manifest where applicable;
- structured data only when it truthfully describes visible content;
- heading structure and link text suitable for search and assistive technology.

For authenticated routes, still set useful titles, language, theme color where appropriate, and safe robots behavior.

## Technical Cleanliness

- Build and typecheck with the repository's commands.
- No console errors, hydration warnings, broken source maps, or missing assets.
- No needless dependencies, debug logs, commented-out code, or orphaned styles.
- Avoid `any` and ignored errors unless the project already documents a justified boundary.
- Cancel subscriptions, observers, timers, and requests on teardown.
- Revert or kill animation contexts, timelines, ScrollTriggers, plugin instances, and related event handlers on route change or unmount.
- Avoid alternating layout reads/writes, unbounded DOM, and avoidable re-renders.
- Measure before optimizing; fix the real bottleneck.

## Definition Of Functionally Complete

The surface is ready for the pre-motion audit only when:

- primary and secondary flows work end to end;
- all relevant states are implemented;
- mobile, tablet, and desktop compositions exist;
- keyboard, touch, and focus behavior work;
- real content and assets are present;
- desktop and mobile implementations use the same Page Content Canon and approved asset identities;
- image crops, focal points, edge treatment, layering, and transition endpoints match the approved media contract;
- build/type/lint/tests pass or failures are understood;
- no blocking or material reference drift remains;
- no unearned or nested cards remain.
- the Component Decision Register covers all nontrivial primitives, including explicit existing/local decisions;
- the Motion Coverage Matrix has been drafted from the implemented interactions, async states, navigation/layout changes, media, and approved brand direction before Phase 8 begins.
