# Quality Gates

Use the applicable sections before motion and delivery, within the user's and host's permitted verification scope. Automated output is evidence of defects, never proof of design quality. Browser checks and task walkthroughs provide visual evidence when allowed; when acceptance is manual, keep those results unverified and provide the relevant checks to the user. Repeat checks only for new changes or unresolved findings.

## Severity

- **P0 Blocking:** primary task cannot be completed, data/security risk, blank/failed render, or content/action is completely inaccessible.
- **P1 Major:** serious confusion, WCAG AA failure, broken mobile first viewport, clipping/overlap, data loss, or material reference drift.
- **P2 Minor:** friction with a workaround, inconsistent state, moderate visual drift, or localized responsive/performance issue.
- **P3 Polish:** optical or microcopy detail with no meaningful task impact.

Fix P0 and P1 before release. Fix P2 unless explicitly deferred. Avoid manufacturing P3 findings to make a report look thorough.

## Gate 0: Evidence And Execution Accountability

Inspect the Phase Accountability Ledger before evaluating visual quality:

- every applicable phase is `implemented`, `evaluated-local`, `not applicable`, `blocked`, or `accepted omission`;
- the Design Delivery Mode Record identifies which pages use generated references and which proceed directly, and quotes the user wording that selected or delegated the mode;
- every material decision distinguishes project truth, current standards, official system guidance, professional research, and community inspiration at the authority needed for the claim;
- the Component Decision Register covers every nontrivial primitive, including explicit existing/local decisions when no dependency was added;
- the Motion Coverage Matrix audits direct controls, state/overlays, async feedback, navigation/layout, media, and brand/narrative motion;
- every approved/reference-derived cue has a Motion Fidelity Manifest item;
- the Visual Calibration Record and subject-world inventory explain the chosen level of distinctiveness, density, motion, and signature;
- the Surface Strategy Record covers every material surface, and required Structural Direction Matrices record meaningful differences, bounded-originality results, and user selection or delegation;
- shared token/component changes identify their canonical source, overrides, affected consumers, and compatibility or migration impact;
- every claimed implementation or verification links to code, rendered evidence, or an actual test result;
- accepted omissions state approval, risk, and revisit condition.

Treat a silently skipped component or motion phase as P1 when it materially changes the approved product. A rule written in documentation without implementation evidence does not pass this gate. Follow `evidence-and-execution.md`.

## Gate 1: Scope And Product Fit

- Every implemented route appears in the Page and State Map.
- Every planned route either exists or is explicitly deferred.
- Material discovery gave every suggested-choice question a visible free-form response path and separately captured additional requirements, `none`, or explicit delegation before analysis.
- Material discovery presented delivery mode as the first visible standalone choice and captured generated-reference, direct, hybrid, custom, or delegated mode before design work; reference input was treated as a separate choice.
- Greenfield direct mode has explicit user selection or delegation evidence; it was not inferred from an empty repository, absent reference, urgency, limited scope, or unavailable image tooling.
- Material discovery visibly offered reference upload, website URL, current/local page, no-reference, and custom paths; the Reference Intake Record states what may be emulated, what must not be copied, and any access or asset-rights limits.
- Greenfield or materially changed work presented viable experience and technical architecture options with consequences and a recommendation; the Architecture Decision Record contains the user's selection, custom answer, or explicit delegation before scaffolding.
- Existing projects preserve their detected architecture unless a material migration was explicitly selected; focused repairs are not blocked by irrelevant architecture ceremony.
- The primary job and success event are clear.
- Material product work defines effectiveness, efficiency, errors/recovery, and user confidence measures; clicks alone are not treated as success.
- Navigation labels and information architecture match the user's mental model.
- Every material route or full-screen state has a dominant product job and structural-exploration decision; hybrid projects do not force public, workspace, commerce, content, analytics, editor, and bounded-flow surfaces into one layout grammar.
- The page is not called or designed as a dashboard without a monitoring/comparison job.
- The first action is evident without reading explanatory prose.
- No dead controls, placeholder routes, or invented product claims remain.

## Gate 1A: Structural Fit And Bounded Originality

Apply this gate before visual-system approval and repeat it against the rendered product.

- Every surface marked `required` has two or three credible structural directions, or fewer only when the record explains why additional candidates would be artificial.
- Each pair differs on at least three applicable structural axes, including primary task path, information architecture, or object relationship; recoloring, typography, radius, imagery style, and motion intensity alone do not qualify.
- Candidate directions use the same approved product facts, content IDs, representative data, and asset identities.
- At least one candidate is a low-risk fit. A bolder candidate has one governing unconventional move and names the task benefit, teaching/orientation cost, mobile consequence, accessibility path, implementation cost, and risk.
- No candidate survives only because it appears novel, premium, dramatic, or unlike other products.
- The selected direction records the user's selection, compatible combination, custom structure, rejection/retry, or explicit delegation before the Design Package is locked.
- The final structural-selection prompt visibly offers select, combine, custom, reject/regenerate, and delegate paths rather than requiring an A/B/C-only answer.
- When delegated, the selected direction has the strongest product evidence and lowest unresolved task risk rather than the greatest visual novelty.
- Surfaces marked `not required` cite an established suitable structure, approved target, or narrow repair boundary. Existing code alone is insufficient evidence.
- Existing-product work explores only the affected surfaces and structural axes; unrelated routes, learned behavior, and shared contracts remain intact.
- The rendered interface does not silently revert to a generic marketing sequence, dashboard tile wall, universal list-detail shell, or desktop stack on mobile.
- Familiar structures remain allowed when the Surface Strategy Record explains their fit. Similarity by itself is not a defect; unexamined reuse is.

Treat a missing required exploration or a style-only candidate set as P1 before implementation. Treat an unjustified experimental interaction that obscures the primary task or blocks access as P1 in the rendered product.

## Gate 2: Reference Fidelity

Apply this gate only to generated-reference pages and to user-supplied visual targets whose requested fidelity requires comparison. Mark it `not applicable: direct implementation selected` for direct pages without an explicit target. Never require a generated reference retroactively.

At matching viewports, compare implementation screenshots against every applicable approved desktop and mobile reference:

- silhouette and first-viewport composition;
- primary and secondary hierarchy;
- density, grouping, and section sequence;
- type roles and line length;
- palette, surfaces, radius, icon, and image treatment;
- major imagery and signature motif;
- image identity, crop, focal point, edge/mask, overlap, layer order, and transition endpoints;
- navigation and CTA placement;
- mobile reordering and disclosure;
- intended state and real content.

Classify differences as blocking, material, or polish. Keep semantic/accessibility improvements even when a generated reference drew an impossible detail, but document the deviation.

Audit every desktop/mobile pair against its Page Content Canon. Treat changed user/data state, missing required content, rewritten core copy, substituted asset subject, changed navigation meaning, or changed action outcome as P1 unless explicitly approved. Responsive reordering, disclosure, and art-directed cropping are allowed only when recorded in the canon.

For a supplied reference website, verify that claimed desktop/mobile states and motion were actually inspected or clearly marked as inferred. Fail the gate if the result copies proprietary copy, trademarks, unique brand assets, source code, or unlicensed media instead of adapting approved design principles to the target product.

For approved image transitions, compare State A, at least one midpoint, and State B. A final static screenshot does not prove motion fidelity.

## Gate 3: Card Restraint

Inventory all card-like containers. For each, record the independent object or interaction context it represents. Fail the gate when:

- cards are used only to create page layout;
- cards are nested;
- an app page becomes many equal boxes with no dominant task;
- section bands or simple rows have unnecessary rounded backgrounds;
- every metric, chart, filter, table, and empty state has a separate framed container;
- the same icon-heading-copy card repeats as generic scaffolding;
- mobile conversion turns every table row or section into a card by reflex.

Replace failed cards with spacing, dividers, lists, rows, tables, direct grid, bands, or progressive detail views.

## Gate 4: Responsive And Mobile

Run the complete `responsive-mobile.md` exit gate. Treat these as P1 by default:

- wrong content dominates the phone first viewport;
- sign-in/register task is pushed below decoration;
- any core action is covered by keyboard, safe area, sticky bar, or browser chrome;
- horizontal page overflow;
- clipped or overlapping text/controls;
- desktop navigation/table/toolbar is merely scaled down;
- touch target or hover-only interaction blocks use;
- supporting media consumes excessive phone space;
- state is lost on interruption or orientation change in a critical flow.

Inspect screenshots at 320, 375, 390, 430, tablet, 1280, and 1440+ unless project constraints define a better matrix.

## Gate 5: Interaction And Usability

Walk the primary flow as:

- a first-time user looking for the next action;
- an experienced user seeking the shortest path;
- a keyboard/screen-reader-dependent user;
- a mobile user with one hand and intermittent attention;
- a stress case using empty, maximum, malformed, and interrupted input.

Check:

- timely system status and feedback;
- familiar terminology and standard control behavior;
- cancel, back, undo, and escape paths;
- prevention of irreversible errors;
- recognition rather than memorization;
- accelerators for frequent expert work where appropriate;
- focused hierarchy without irrelevant content;
- specific error recovery;
- contextual help only where the task genuinely needs it.

Record task completion, unnecessary steps or time, errors and recovery, and observable confidence issues from the walkthrough. Do not claim user validation unless representative users actually performed the tasks.

Count visible choices at decision points. Group or progressively disclose when the user must process more than a manageable set at once.

## Gate 6: Accessibility

Verify manually and with available tooling:

- unique page title, language, landmarks, and heading hierarchy;
- native semantic elements and accessible names;
- keyboard completion of every primary flow;
- visible focus and logical focus order;
- focus trap/restoration for modal contexts;
- correct arrow-key behavior for composite widgets;
- form labels, descriptions, required state, and linked errors;
- live announcements for asynchronous status and errors;
- meaningful alt text and empty alt for decoration;
- contrast for text, icons, controls, focus, and states;
- meaning not carried by color, motion, hover, or sound alone;
- 200% zoom/reflow and user text settings;
- target sizes and spacing for touch;
- reduced-motion behavior;
- high-contrast/forced-colors support when relevant.

Automated scans do not verify comprehension, focus logic, or correct announcements. Test those manually.

## Gate 7: Content And States

- Real product copy, data, and imagery are present.
- Terminology is consistent.
- Buttons describe outcomes.
- Error messages explain recovery without blame or humor.
- Empty states explain what belongs there and provide the appropriate next action.
- Loading states identify what is happening and do not erase existing context unnecessarily.
- Long content, zero content, maximum content, translation expansion, CJK, RTL, and unbroken identifiers fit.
- Permission/read-only/offline/stale states are clear where relevant.
- Success confirms what changed and what happens next.

## Gate 8: Visual Craft

- Spacing follows a scale and communicates grouping.
- Alignment is consistent and optically balanced.
- Typography roles are coherent, readable, and stable.
- Letter spacing is `0`; no negative or tracked-label styling is used as decoration.
- The palette has clear semantic roles and sufficient contrast.
- The interface is not dominated by one prohibited hue family or generic AI gradient.
- Radius, border, shadow, and elevation language is coherent.
- Icons come from one family and align with text.
- Controls retain stable dimensions across states.
- No card-within-card, decorative blob/orb, fake screenshot, or generic filler remains.
- Brand and product surfaces use the right register.
- The visual identity is traceable to the product's real subject, content, materials, language, or workflows rather than a generic template.
- For a new brand direction, the governing concept uses distinguishing subject facts and informs supporting sections, not only the first viewport.
- The approved content remains substantive after decorative elements are removed, and the initial and reduced-motion compositions retain a clear hierarchy and primary task.
- One justified signature element or sequence is legible; decorative effects do not compete with it.
- Structural devices such as numbering, timelines, rulers, or annotations carry real information.
- Generated page images were created only after the Design Package was approved and do not contain option labels, prompt notes, or internal design metadata.

## Gate 8A: Color System And Themes

- Primitive palette values, semantic roles, and component mappings are separated and use the project's token architecture.
- Base, supporting, and accent visual weight is intentional. `60-30-10` is used only as a diagnostic heuristic, not a literal quota.
- The strongest salience supports the current primary task; repeated, secondary, and decorative elements do not compete with it.
- Brand accent, primary action, focus, selection, information, success, warning, error, and destructive roles remain semantically clear.
- Status and availability never depend on hue alone; text, icon, shape, border, or other persistent evidence carries the meaning.
- Default, hover, pressed, focus-visible, selected, disabled, loading, validation/error, and success states are distinguishable where relevant without layout shift.
- Hover styling is not required for touch use, focus remains visible independently, and disabled labels remain understandable.
- Dark mode uses deliberate semantic mappings rather than inversion, preserves hierarchy and brand recognition, and does not flash the wrong theme on initial render.
- Light, dark, grayscale, high-contrast, forced-colors, and common color-vision simulations preserve task clarity at representative viewports.
- Text, icons, control boundaries, focus indicators, statuses, charts, and overlays meet the project's contrast target on their actual rendered backgrounds.
- Data category colors stay consistent across views and themes and use labels, patterns, markers, or line styles when hue is insufficient.
- Automated contrast output is confirmed manually in the real state; screenshots show no color noise, accidental competition, or unreadable muted text.

Treat hidden focus, indistinguishable states, inaccessible status, wrong-theme flash, or low-contrast essential content as P1 by default.

## Gate 8B: Design System Governance

- The canonical source for primitive tokens, semantic tokens, component mappings, shared components, and usage documentation is identified.
- Master-system rules and page/surface overrides are separate; one generated page does not silently redefine the master.
- Shared components have documented purpose, anatomy, variants, full states, responsive behavior, accessibility behavior, token mapping, and test expectations.
- Components remain focused and composable; data/workflow orchestration is separated from presentation when responsibilities diverge.
- State lives at the narrowest durable owner and is not promoted to shared/global storage without a cross-surface need.
- Shared changes include affected-consumer browser evidence. Breaking changes include migration and deprecation handling.
- Generated references when selected, implementation, and maintained documentation agree on the same master system plus approved overrides. Direct pages are checked against the Design Package without inventing generated-reference evidence.

## Gate 9: Performance And Resilience

Measure where relevant:

- LCP and above-fold media delivery;
- INP and long main-thread tasks;
- CLS and reserved dimensions;
- route and initial JavaScript/CSS size;
- image and font payload;
- list/table rendering and memory;
- animation frame stability;
- network request waterfall and caching.

Check:

- responsive images and modern formats;
- lazy loading below fold, not above fold;
- code splitting for genuinely heavy features;
- no unnecessary dependency or duplicate runtime;
- bounded blur/filter/canvas/3D work;
- cleanup of listeners, observers, timers, workers, and requests;
- slow network, offline, timeout, partial failure, and retry;
- no avoidable layout reads/writes or unbounded DOM.

Measure before and after material optimization. Do not chase a score while breaking semantics or visual fidelity.

## Gate 10: Metadata And Assets

For public pages:

- unique title and description;
- canonical policy;
- Open Graph/social preview image and metadata;
- language/locale;
- icons/manifest where applicable;
- correct robots behavior;
- structured data only when truthful;
- no broken external asset or guessed URL.

For all pages:

- asset paths resolve in production build;
- intrinsic sizes prevent layout shift;
- licenses and provenance are recorded when needed;
- no local required asset remains outside the project;
- no UI text is rasterized.

## Gate 11: Engineering Verification

Run the repository's available commands:

- format check;
- lint;
- typecheck;
- unit/integration tests;
- focused end-to-end tests for primary flows;
- production build;
- accessibility and visual regression checks when configured.

Start the development server and keep it available for review. Verify:

- no console errors or hydration warnings;
- no failed network requests or broken source paths;
- primary routes load directly and after navigation;
- refresh/back/forward behavior;
- authentication and permission boundaries;
- overlays and portals near edge/overflow contexts;
- output is not blank and all key assets render.

## Motion Re-Entry Gate

After Phase 8, repeat responsive, accessibility, interaction, performance, and screenshot checks. Specifically test:

- every Motion Coverage Matrix category is implemented, concretely not applicable, or explicitly accepted as an omission;
- animation interruption and rapid repeated actions;
- focus during and after transitions;
- reduced motion;
- touch gestures and keyboard alternatives;
- offscreen pause/cleanup;
- overlap, layout shift, and hit-target stability;
- frame time on a realistic mobile device.
- every Motion Fidelity Manifest cue is implemented, classified as non-temporal evidence, or has an accepted omission;
- start/middle/end frames preserve approved image crop, stacking, edge treatment, and timing intent;
- delayed/failed image decode causes no blank frame or stale layer;
- rapid repeat, reverse, route unmount/remount, orientation change, and breakpoint rebuild create no duplicate animation or trigger;
- selectors remain component-scoped and all contexts, listeners, timelines, plugin instances, and ScrollTriggers clean up;
- ScrollTrigger markers, GSDevTools, debug controls, and accidental duplicate runtimes are absent from production;
- animation/plugin bundle cost and low-end device behavior are acceptable;
- reduced motion produces a complete static composition rather than a broken or half-initialized sequence.
- narrative webpages use a purposeful beat map when expressive motion is approved, while preserving normal reflow, semantic reading order, user-controlled scrolling, deep links, and mobile composition;
- no fixed-ratio presentation stage, forced slide navigation, scroll hijacking, or full-screen-section requirement was transferred without an explicit product reason.

## Delivery Evidence

The final report should state:

```markdown
## Delivered
- Routes/features:
- Development URL or openable file:

## Verified
- Build/type/lint/tests:
- Browsers/viewports:
- Keyboard/accessibility:
- Mobile first-viewport checks:
- States exercised:
- Color themes/states checked:
- Performance checks:

## Delivery mode
- Selected mode:
- Generated-reference pages/states:
- Direct pages/states:
- Optional artifacts explicitly skipped:

## Surface and structural strategy
- Surface Strategy Record coverage:
- Exploration required/not required/accepted omission:
- Structural directions compared and meaningful axes:
- User selection/delegation evidence:
- Bounded-originality and convergence result:

## Open-source provenance
- Package/repository, version, license, and local adaptations:
- If none added: needs evaluated, existing/local decision, and reason:

## Component Decision Register
- Nontrivial primitives covered:
- Decisions and verification:

## Motion coverage
- Matrix categories and statuses:
- Fidelity Manifest cues:
- Reduced-motion result:

## Reference fidelity
- Status: verified / not applicable for direct pages / limited to explicit user-supplied target
- References matched:
- Desktop/mobile content parity:
- Image and transition keyframes:
- Accepted deviations:

## Design contract
- DESIGN.md status: updated / verified current / not needed
- Master design-system source and approved surface overrides:
- Shared token/component compatibility or migration impact:
- Evidence and reason:

## Remaining risks
- Honest limitations or unverified device/browser behavior:
```

Do not claim verification that was not run. If real-device testing was unavailable, say so and identify the emulation/browser evidence used instead.
