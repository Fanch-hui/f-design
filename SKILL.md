---
name: f-design
description: "End-to-end frontend product design, implementation, and existing-interface optimization. Use when an AI coding agent must plan, design, redesign, prototype, implement, audit, or polish websites, web apps, workspaces, editors, commerce, content, analytics, forms, responsive mobile surfaces, design systems, reference-to-code builds, color/themes, interaction states, imagery, or motion. Also use for hierarchy, layout, structural differentiation, card restraint, accessibility, media transitions, motion fidelity, performance, and standards compliance. For greenfield or material design work, after a factual scan, MUST stop and ask delivery mode as the first standalone choice; never infer direct mode. Classify each surface by its primary job, explore genuinely different structures only when needed, reject novelty without task value, design before optional image generation, keep desktop/mobile on one content canon, and verify in a real browser."
---

# F-design

Design and deliver frontend products through one self-contained process. The synthesized design, component, accessibility, responsive, media, color, motion, and quality guidance needed for this workflow is included here. Use the native tools available in the current harness and own the work from discovery through browser verification.

## Hard Stop: Greenfield Delivery Mode Gate

When the repository has no established UI and the request will create a website, page, or application, perform only a factual repository scan, then make **Design Delivery Mode** the first visible standalone choice before visual analysis, architecture selection, scaffolding, image generation, or implementation:

1. **Design -> Generate References -> Implement**
2. **Design -> Direct Implementation**
3. **Hybrid:** generate references only for named pages/states
4. **Custom / 自定义** or explicit `你定 / decide for me`

Stop and wait for the answer. Greenfield has no default mode. An empty repository, no external reference, a short prompt, urgency, unavailable image tooling, or phrases such as `start now`, `build it`, `make the homepage first`, or `let me see the result` do not select direct implementation and do not delegate this choice. Bypass this gate only when the user explicitly named a mode or explicitly delegated the mode decision; record the user's wording.

## Operating Contract

Apply these rules before any stylistic preference:

1. **Reconcile existing project truth.** Read the nearest `AGENTS.md`, `DESIGN.md`, product requirements, design system, components, assets, routes, rendered UI, and conventions before proposing technology or visuals. Distinguish functional truth, documented intent, and accidental implementation drift instead of trusting any one source silently.
2. **Ask before material analysis.** After a factual repository scan, ask a short guided round about the delivery mode, unresolved product, optional reference source, experience/technical architecture, style, palette, imagery, and motion choices. For material design work, delivery mode must be the first visible standalone question, not an inferred default or a detail hidden inside a visual-style question. It must let the user choose `design -> generated references -> implementation`, `design -> direct implementation`, a page-scoped hybrid, a custom mode, or explicit delegation. It must also visibly let the user upload reference screenshots or recordings, provide a website URL or local page, proceed without any reference, or write a custom combination. Reference input and generated output are separate choices. Every choice question must include a visible free-form answer path, and the round must end with a separate open-ended question for additional requirements. Do not publish a Product Brief, analyze visual directions, generate references, choose a new architecture, or code until the user answers, already supplied equivalent detail, explicitly says there are no additional requirements, or delegates the choices.
3. **User task wins over visual fashion.** Classify the product and identify the primary job before choosing a layout.
4. **Distinctiveness comes from the subject.** Derive materials, imagery, language, structure, and one signature move from the product's real world. Do not manufacture identity from generic gradients, decorative effects, or fashionable component demos.
5. **No surface without a strategy.** Classify each meaningful page or full-screen state by its primary job, not its appearance. Record whether structural exploration is required before locking routes or composition.
6. **Bound originality with product evidence.** When structure is unresolved, compare two or three genuinely different, product-grounded directions. Reject style-only variants and novelty without task value; preserve at least one low-risk fit.
7. **No page without purpose.** Define routes, states, first-viewport priority, and success criteria before generating references.
8. **One content canon across viewports.** Desktop and mobile designs are different compositions of the same approved copy, content IDs, asset identities, data, user state, navigation, and actions. Generated references, when selected, must visualize this canon rather than redefine it. Mobile may reorder, condense, or progressively disclose; it may not silently invent or replace the product.
9. **No code before direction.** For material new builds or redesigns, confirm the Product Brief, Surface Strategy Record, selected structural direction, Page and State Map, project design contract, and visual direction before implementation. If the user explicitly delegates decisions, record assumptions and proceed.
10. **Generated references are optional delivery artifacts.** Create them only for pages/states selected by the user under generated-reference or hybrid mode, and only after the design package is approved. Direct implementation mode skips generated page references, their manifests, parity audits, and reference-to-code comparison. User-supplied targets remain evidence only to the fidelity level the user explicitly requested.
11. **Media belongs to the composition.** Preserve image identity, crop intent, focal point, layering, edge treatment, and reference transition behavior. Do not insert imagery as an unrelated rectangle after layout is finished.
12. **Color is role-based communication.** Use semantic tokens, controlled salience, complete component states, and deliberate theme mappings. Treat `60-30-10` as a diagnostic heuristic, never a quota; never rely on hue alone for meaning; never create dark mode by inversion.
13. **Open source is evidence-based.** Prefer mature, maintained GitHub projects, but adapt them to the current product. Never paste a library's demo styling into the project unchanged.
14. **Cards must be earned.** Do not use dashboard-card composition as the default grammar. Never nest cards. Use spacing, dividers, lists, tables, bands, or direct layout when content does not need an independent container.
15. **Mobile is a separate composition, not a separate product.** Re-prioritize, reorder, collapse, and reposition for phone use while preserving the content canon.
16. **Function before motion does not mean motion is optional.** Stabilize content, states, responsiveness, accessibility, and interaction behavior first; then implement every approved or reference-derived motion cue, or document an accepted omission.
17. **Browser evidence is required.** Builds, linters, and detectors support the review; screenshots, captured keyframes, and real interaction paths decide whether the UI is ready.
18. **No silent phase completion.** Keep a Phase Accountability Ledger. Every applicable phase must end as `implemented`, `evaluated-local`, `not applicable`, `blocked`, or `accepted omission`, with its decision and verification evidence. A written rule is not a delivered feature until the rendered product proves it.

## Choose The Work Path

- **New product or substantial redesign:** run all nine phases.
- **New page inside an established product:** inspect the foundation, run focused discovery and page/state definition, then follow the selected delivery mode. Create desktop/mobile generated references only when that page is assigned to generated-reference or hybrid mode.
- **Reference image or motion target to code:** preserve the repository foundation, inventory the static composition, media treatment, transition choreography, missing states, and mobile behavior, then continue from implementation.
- **Optimize an already-written webpage or product surface:** capture the live baseline, diagnose whether defects are local presentation, component behavior, responsive composition, page hierarchy, or product structure, then improve only the affected scope and compare before and after. Trigger structural exploration only when structure is materially changing. Read [existing-surface-optimization.md](references/existing-surface-optimization.md) and follow the loop below.
- **Focused audit or repair:** inspect the product context, run the applicable quality gates, repair verified defects, and repeat browser checks. Do not stop at a report when the user asked to improve the code. Do not force unnecessary discovery artifacts.
- **Motion-only request:** first confirm that the surface works and has stable layout. Then run the motion phase and final review.

For substantial work, keep a live checklist and the Phase Accountability Ledger described in [evidence-and-execution.md](references/evidence-and-execution.md). Do not quietly skip a phase; state the reason and evidence when a phase is inapplicable.

## Choose The Delivery Mode

For every material new build, redesign, or page addition, obtain and record one user-selected or explicitly delegated mode before visual analysis. Do not choose direct implementation from silence or convenience:

1. **Design -> Generate References -> Implement:** complete and approve the design package, generate approved desktop/mobile page references, then implement and compare against them.
2. **Design -> Direct Implementation:** complete and approve the same design package, skip generated page references, and implement directly. Browser screenshots prove quality but are not compared to nonexistent generated references.
3. **Hybrid:** name the pages or states that use generated references; all others use direct implementation.
4. **Custom or delegated:** record the exact boundary and consequences.

The mode controls artifacts, not design quality. All modes still require product definition, page/state scope, visual and responsive decisions, implementation, accessibility, and browser QA. Only a focused repair of an established surface may default to direct implementation; an empty project, new page, redesign, or material structural change may not.

## Existing Surface Optimization Loop

Use this loop for a webpage, component, flow, or application that already renders:

1. **Preserve the contract.** Identify the page's purpose, primary task, existing identity, shared design system, functional behavior, user-authored changes, and out-of-scope areas.
2. **Capture the baseline.** Start the real app and inspect desktop, tablet, and phone. Save and read before screenshots; exercise the primary flow and important states.
3. **Diagnose causes, not symptoms.** Separate local presentation, component behavior, responsive composition, page hierarchy, product structure, typography, color/surface, accessibility, content, state, motion, performance, and metadata problems. Cite concrete source locations and browser evidence.
4. **Prioritize.** Fix task blockers and mobile/accessibility defects first, then structural and system drift, then visual polish. Avoid broad restyling when a smaller change solves the cause.
5. **Improve in passes.** Correct structure and hierarchy, layout and rhythm, typography and copy, design-system alignment, responsive/mobile composition, interaction states and accessibility, then implement approved reference motion and add any other motion only when useful.
6. **Verify the delta.** Re-run build/tests, repeat the browser matrix, compare before and after at identical viewports, and check that function and identity were preserved.

For a normal optimization request, implement verified improvements instead of only proposing them. When the user requests a redesign, the current direction is fundamentally wrong, or several pages need a new system, confirm the delivery mode before proceeding. Generate new reference images only for generated-reference or hybrid pages. Do not generate references merely to adjust spacing, typography, responsiveness, or standards compliance.

## Phase 1: Establish The Foundation

Run a factual scan before asking questions:

- Read `package.json`, lockfiles, framework config, routes, global styles, design documentation, token files, shared components, icon dependencies, assets, tests, and build scripts.
- Identify the current framework, rendering model, styling approach, component primitives, state/data layer, test tooling, browser support, and deployment constraints.
- Reuse an existing stack, component system, and icon family. Do not start a parallel app or add a second primitive system.
- For a greenfield project, derive two or three viable experience and technical architecture options from product needs rather than fashion. Explain the tradeoffs, mark one recommendation, and ask the user to choose, customize, or delegate before scaffolding. For an existing project, preserve the current architecture by default but obtain explicit approval before a material migration or parallel stack.
- Record what is known, directly evidenced, and unresolved. Do not turn the scan into a visual-direction decision before the discovery gate.
- Classify external guidance by authority and freshness. Current standards and platform documentation outrank design-system examples, professional research, and community inspiration; none silently overrides explicit product evidence.

Read [discovery-and-architecture.md](references/discovery-and-architecture.md) for the product taxonomy, interview cadence, technology decision rules, and page-map contract. Read [surface-strategy-and-structure.md](references/surface-strategy-and-structure.md) before locking any material page structure.

## Phase 2: Discover And Classify The Product

For material new work, visual redesign, or ambiguous image-led work, stop at a **Discovery Gate** after the factual scan. Ask one guided round of up to four high-leverage questions plus one separate open-ended additional-requirements question, then wait for the answer before analyzing directions. The first visible question must be a **Design Delivery Mode Choice**; when unresolved, the round must also include an optional **Reference Input Choice** with a first-class `no reference` path and an **Architecture Choice**. Do not bury these inside the additional-requirements prompt. Every direction question must offer a `Custom / 自定义：请填写` response in addition to suggested options. Ask a second round only when the answer exposes a material branch. Skip the delivery-mode question only when the user explicitly named a mode or explicitly delegated it. Skip the broader gate only when the prompt and repository already answer the remaining questions and additional requirements, the user explicitly delegates the remaining decisions, or the task is a small repair whose direction is established.

Resolve at least:

- design delivery mode: generated-reference, direct implementation, page/state-scoped hybrid, custom, or explicitly delegated;
- audience, context, mental state, and primary job;
- success event and business outcome;
- product class and per-surface register: brand, product, or hybrid;
- per-surface primary job, interaction topology, first-viewport priority, and structural-exploration decision;
- content/data shape, roles, authentication, permissions, and realistic ranges;
- target platforms, accessibility level, localization, performance, SEO, and browser constraints;
- reference input mode: uploaded screenshot/video, public website URL, local/current page, named inspiration, no reference, or a custom combination; plus exactly what may be imitated and what must not be copied;
- experience architecture and, when greenfield or materially changing, technical architecture selected by the user or explicitly delegated after tradeoffs are shown;
- fidelity, breadth, timing, references, and anti-references;
- success measures for effectiveness, efficiency, errors/recovery, and user confidence, rather than click-through alone;
- preferred visual lane and rejected visual lane;
- palette strategy or hue families, light/dark preference, imagery/material treatment, and the three calibration dials: expressive variance, information density, and motion energy;
- user-authored custom directions, extra functionality or content, naming/copy, must-preserve details, prohibited elements, technical constraints, and any other requirements not covered by the suggested options.

Offer concrete choices grounded in the product instead of asking only "what style do you like?" Explain each option in one sentence, include a visible free-form option for each question, and allow the user to combine traits or ignore the suggestions and write their own direction. A reference choice must accept attachments and URLs, not only named style options. An architecture choice must distinguish experience topology from implementation stack when both are unresolved. The final additional-requirements question must remain open-ended rather than another fixed choice list. Produce a compact **Design Delivery Mode Record**, **Product Brief**, **Reference Intake Record**, and **Architecture Decision Record** only after this gate. Then create the **Surface Strategy Record** before structural or visual exploration. For a material build, present the resolved records for confirmation. If the user asks for autonomous execution, state the assumptions instead of blocking.

Never call something a dashboard merely because it contains data. A dashboard is justified only when monitoring, comparison, or triage across multiple signals is the primary recurring job.

## Phase 3: Define Functions, Pages, Flows, And States

Turn the brief into an implementation-sized scope:

1. Map the primary and secondary user flows.
2. Create a **Surface Strategy Record** for every route or meaningfully distinct full-screen state. Classify its dominant product job, core objects/content, interaction topology, first-viewport priority, mobile task change, existing constraints, and whether structural exploration is `required`, `not required`, or an `accepted omission`.
3. When exploration is required, create two or three product-grounded structural directions and a **Structural Direction Matrix**. Each pair must differ on at least three applicable structural axes, including the primary task path, information architecture, or object relationship. Palette, typeface, radius, illustration style, and motion intensity alone do not count.
4. Run the bounded-originality gate: reject directions whose value is only novelty, that obscure the primary task, break familiar orientation without benefit, fail mobile/accessibility/state needs, or demand disproportionate implementation and assets. Keep at least one low-risk fit; do not invent a weak wildcard to fill a quota.
5. Present viable directions and end with a visible choice to select, combine named compatible parts, write a custom structure, reject/regenerate the set, or explicitly delegate. Do not reduce this to an A/B/C-only prompt. Record the wording and rationale before locking routes or composition.
6. Separate routes from tabs, overlays, drawers, dialogs, and data states. List every page with purpose, audience, entry, primary action, key content, selected desktop composition, mobile first-viewport priority, and completion condition.
7. Add loading, empty, error, offline, success, disabled, permission, first-run, overflow, and long-content states where relevant.
8. Identify shared shells and templates without erasing page-specific needs. Do not force public, workspace, commerce, content, analytics, editor, and bounded-flow surfaces into one project-wide layout grammar.
9. Defer low-value features explicitly instead of leaving vague placeholders.

The result is the **Surface Strategy Record**, selected **Structural Direction Record**, and **Page and State Map**. Do not generate references or code until every planned page has an accountable role and every required structural exploration has a recorded selection or explicit delegation. Follow [surface-strategy-and-structure.md](references/surface-strategy-and-structure.md).

## Phase 4: Complete The Design, Then Optionally Generate References

First define one visual system for the entire product:

- audience and emotional register;
- a subject-world inventory of real materials, instruments, artifacts, environments, language, and interaction metaphors that can ground the identity;
- named references and named anti-references;
- approved levels for expressive variance, information density, and motion energy;
- palette roles, visual-weight budget, and contrast strategy;
- semantic feedback roles, component state colors, light/dark mappings, and data-color policy;
- typography roles and loading strategy;
- density, spacing, grid, shape, elevation, icon, image, and motion language;
- card policy and page-section grammar;
- desktop and mobile composition rules.

Existing identity wins unless the user explicitly requests departure. Brand surfaces may be expressive; task-focused product surfaces should feel quiet, familiar, and efficient. Hybrid products may use both registers, but shared tokens and identity must connect them.

Choose one justified signature element or sequence and make the rest of the system support it. For a material system, identify the canonical design/token source, page or surface overrides, component contracts, and compatibility policy before implementation. Do not overwrite an existing master system to rationalize one generated page. Read [design-system-governance.md](references/design-system-governance.md).

Define a **Color Role Table**, **Theme Matrix**, and **Component State Matrix** before generating references. Use `60-30-10` only to diagnose visual balance; reserve salience for real hierarchy; keep brand, action, focus, and status meanings distinct. Read [color-system-and-states.md](references/color-system-and-states.md).

For a material new build, redesign, or multi-page system, synthesize a project-specific `DESIGN.md` from the Product Brief, existing project identity, user-provided references, and [design-reference-synthesis.md](references/design-reference-synthesis.md). Existing project design documentation remains authoritative.

Before generating any reference or implementing the interface, complete a **Design Package** containing the confirmed Product Brief, Surface Strategy Record, selected Structural Direction Record, Page and State Map, project design contract, desktop/mobile composition rules, Color Role Table, Theme Matrix, Component State Matrix, media/motion intent, and a **Page Content Canon** for every page. The canon freezes stable content IDs, approved copy, data/state, asset IDs, navigation, actions, and what mobile may reorder, condense, or defer. Present the package for confirmation or record explicit delegation. Visual refinement may not silently replace the selected structure with a familiar generic skeleton.

Then follow the selected mode.

### Generated-Reference Or Hybrid Pages

1. Use image generation only after the Design Package exists; generated images visualize approved design decisions and may not invent the design system or scope.
2. If direction is still ambiguous, return to structured design alternatives and finish the Design Package. Do not use generated page images to discover or choose an undefined design direction.
3. Generate a named high-fidelity desktop reference for each selected page/state, then derive its mobile prompt from the same locked canon and asset manifest.
4. Keep shell, tokens, copy, state, asset identities, type, and component language consistent across the selected reference set.
5. Run desktop/mobile parity and reference-manifest checks only for selected pages/states. Regenerate any image that contradicts the approved Design Package.

### Direct-Implementation Pages

- Do not generate direction probes or page references unless the user changes the mode.
- Do not create a generated-reference manifest, generated desktop/mobile pair audit, or generated-reference fidelity gate.
- Implement from the approved Design Package and Page Content Canon.
- Use browser screenshots for responsive, accessibility, visual, and before/after QA. Do not describe those screenshots as pre-implementation design references.

Never rasterize core interface text or treat generated copy as approved product copy. Read [visual-system.md](references/visual-system.md) in every mode. Read [reference-images.md](references/reference-images.md) only for user-supplied reference work, generated-reference mode, or the selected pages in hybrid mode.

## Phase 5: Research Components And Plan Implementation

Inventory what the project already provides before searching. Search GitHub only for nontrivial primitives or domain behavior where a mature implementation meaningfully lowers risk.

Perform current package research directly against project dependencies, package repositories, and primary documentation. In this phase, `installed` means present in the target project's dependency graph.

Create a **Component Decision Register** before implementation. Give every nontrivial interaction or domain primitive its own row; simple native controls and local semantic layout may share one grouped row. Record the existing-system check, whether external research was triggered, candidates considered, the decision (`existing`, `external`, or `local`), reasoning, adaptation boundary, and verification. A valid decision to add no dependency must still be explicit; an empty provenance section is not evidence that the phase ran.

For each candidate, verify current evidence: repository and package identity, popularity appropriate to its category, recent maintenance and releases, license, issue health, documentation, tests, accessibility, framework and SSR compatibility, bundle impact, theming flexibility, and community adoption. Reject repositories with only token adoption or unclear maintenance. Stars are a filter, not proof.

Prefer:

- the project's existing primitive system;
- headless or unstyled primitives when visual fit matters;
- category leaders with stable APIs for dialogs, menus, comboboxes, tables, virtualization, charts, dates, drag-and-drop, and complex motion;
- small local markup for simple UI rather than a dependency.

Record the selected source and exactly how it will be restyled, wrapped, or constrained. Do not mix competing primitive systems on one surface. Read [open-source-components.md](references/open-source-components.md) and [evidence-and-execution.md](references/evidence-and-execution.md).

## Phase 6: Recreate And Implement

Implement in deliberate passes:

1. **Structure:** semantic routes, landmarks, information hierarchy, flow, and canonical content.
2. **System:** project `DESIGN.md`, semantic color and theme tokens, typography, spacing, grid, surfaces, icons, and assets.
3. **Components:** behavior, data, forms, and complete visual/semantic interaction states.
4. **Media integration:** implement approved asset identity, responsive crop, focal point, masks/edges, layering, loading, and static start/end compositions before animating them.
5. **Responsive composition:** implement mobile decisions explicitly from the same content canon, then tablet and desktop refinements.
6. **Resilience:** realistic loading, empty, error, permission, long-text, large-data, localization, and offline states.
7. **Accessibility:** names, semantics, keyboard behavior, focus, announcements, contrast, touch targets, and reduced motion.

Preserve the approved Design Package in every mode. For pages with an approved visual target, also preserve its major ingredients: silhouette, hierarchy, density, imagery, crops, layering, motifs, navigation, CTA treatment, and evidenced motion cues. Translate the design into semantic, maintainable code rather than tracing pixels blindly. Use real assets and real copy at presentation time. Do not ship dead controls, fake metrics, guessed image URLs, placeholder rectangles, or a second design language.

Keep components focused and composable. Separate data/state orchestration from presentation when their responsibilities diverge, and place state at the narrowest durable owner: local, lifted, shared context, URL, server, then global only when the previous levels cannot own it correctly. For generated or reference-led iteration, choose explicitly between targeted edit, variant exploration, and full regeneration; prefer targeted edits when the structure is sound.

Read [implementation.md](references/implementation.md) for the implementation contract and card decision test. Read [design-system-governance.md](references/design-system-governance.md) when shared tokens or components change. Read [media-and-image-transitions.md](references/media-and-image-transitions.md) whenever images or reference transitions matter.

## Phase 7: Audit Before Motion

Start the real development server and inspect the product in a browser. Run the repository's build, typecheck, lint, tests, accessibility checks, and relevant performance measurements, but do not treat passing automation as proof.

Verify at minimum:

- phone widths `320`, `375`, `390`, and `430`;
- a tablet portrait and landscape composition;
- desktop at `1280` and `1440`, plus the project's largest supported layout;
- keyboard-only flow, focus order, 200% zoom, reduced motion, long text, empty/error/loading states, and a throttled network when relevant;
- light/dark themes, component-state distinction, grayscale, high-contrast or forced-colors behavior, and color meaning without hue when relevant;
- console errors, broken assets, layout shift, horizontal overflow, overlays, sticky elements, and soft-keyboard behavior.

For generated-reference and selected hybrid pages, compare implementation screenshots to each approved reference. For direct pages, compare the rendered result to the Design Package, Page Content Canon, responsive rules, and any explicit user-supplied target only when fidelity was requested. In all modes, confirm desktop/mobile content parity and static media start/end compositions, run a dedicated card audit and mobile first-viewport audit, and fix verified defects before adding motion.

Also run the structural-convergence audit from [surface-strategy-and-structure.md](references/surface-strategy-and-structure.md). Familiar patterns pass when the Surface Strategy Record explains their task fit; unexplained reuse of the same marketing, dashboard, list-detail, or mobile-stacking skeleton across unrelated products does not.

Read [responsive-mobile.md](references/responsive-mobile.md) and [quality-gates.md](references/quality-gates.md).

## Phase 8: Add Motion And Microinteractions

Create a **Motion Coverage Matrix** before writing animation code. Audit direct-control feedback, state/overlay continuity, async status, navigation/layout continuity, media transitions, and brand/narrative motion; mark each category `implemented`, `not applicable`, or `accepted omission` with evidence and a reduced-motion result. Then create a **Motion Fidelity Manifest** for every explicit or implied cue in approved references, user-provided video/GIF/prototypes, and current product. For each cue, record the target, trigger, start/end frame, property, timing/ease, scroll relationship, responsive variant, reduced-motion result, and verification method. Map every cue to an implementation, `not temporal evidence`, or an explicitly accepted omission. A static still may define transition geometry or a visual state, but it does not authorize invented timing or choreography.

This phase is mandatory when the approved direction contains image reveals, wipes, masks, crop changes, parallax, shared-element movement, pinned sections, scroll-linked sequences, or other visible motion. Do not claim that motion is unnecessary when a reference depends on it.

A button press plus one toast fade is not complete motion delivery for an approved expressive, brand-led, or image-led surface. Such a surface needs its approved signature sequence or reference transition. A quiet task surface may legitimately use only restrained state motion, but the matrix must show that every applicable category was evaluated and verified.

- Product motion is fast and state-led. Frequent and keyboard-driven actions get no choreography.
- Brand motion may carry voice, but use one signature sequence instead of repeated fade-and-rise sections.
- For narrative public pages, borrow presentation-style choreography only as page beats: orchestrate reading order, media reveals, and section continuity around the page's real content. Preserve normal web reflow, scrolling, semantics, responsive composition, and user control; do not impose a fixed-ratio stage, forced slide navigation, or full-screen sections by default.
- Prefer CSS or the project's existing capable motion library for simple transitions. Use GSAP timelines for coordinated multi-step or image choreography, ScrollTrigger for genuine scroll-linked/pinned/scrubbed sequences, and Flip for shared layout transitions when the project lacks an equivalent. Do not add GSAP merely for a hover fade.
- Use transform and opacity as defaults. Bound paint-heavy effects, avoid casual layout animation, and never use `transition: all`.
- Make gesture motion interruptible and velocity-aware.
- Respect reduced motion with an equally usable static result.
- Scope targets, register plugins once, and clean up timelines, contexts, callbacks, and ScrollTriggers on unmount or route change. Use `useGSAP`, scoped refs, and `contextSafe` in React when available; keep GSAP client-only under SSR.
- Verify on touch hardware and at slowed playback or frame-by-frame. Compare captured start, middle, and end frames to the approved transition, not only the final screenshot.

Read [motion-and-interaction.md](references/motion-and-interaction.md) before implementing motion.

## Phase 9: Final Standards Review

Repeat the browser matrix after motion. Release only when:

- the primary task is immediately clear on every page and viewport;
- every material surface has a Surface Strategy Record and every required exploration has a selected or explicitly delegated structural direction;
- the selected structure is justified by product evidence rather than copied from a familiar website, dashboard, editor, commerce, or content skeleton;
- structural alternatives were meaningfully different where required, while rejected novelty did not enter the final interface;
- mobile first viewports prioritize the page's actual job;
- no content is hidden, clipped, overlapped, or needlessly oversized;
- every interactive element has complete states and works with keyboard and touch;
- all planned states exist and recover cleanly;
- the implementation matches the approved Design Package and, where applicable, approved visual targets, or documents accepted deviations;
- the selected delivery mode was respected: direct pages have no invented generated-reference obligations, while generated-reference pages completed their selected manifest, parity, and fidelity checks;
- desktop and mobile preserve one content canon while using intentional viewport-specific composition;
- images retain approved identity, crop intent, focal point, layering, edge treatment, and fallback behavior;
- color hierarchy supports the primary task, semantic feedback never relies on hue alone, component states remain distinct, and light/dark themes preserve role and contrast;
- any selected open-source components are licensed, maintained, accessible, and visually integrated;
- the Component Decision Register covers every nontrivial primitive and explicitly records why existing/local implementation was chosen when no dependency was added;
- cards are used only where earned and never nested;
- every applicable Motion Coverage Matrix row is implemented or explicitly accepted as an omission;
- every Motion Fidelity Manifest item is implemented, classified as non-temporal evidence, or explicitly accepted as an omission;
- motion and image transitions match approved start/middle/end behavior, remain smooth and interruptible where needed, and have a coherent reduced-motion result;
- accessibility, metadata, assets, performance, build, tests, and console checks pass;
- durable shared token or component changes have ownership, usage guidance, affected-consumer verification, and migration/deprecation notes when compatibility changes;
- source files are maintainable and the development server is available for user review.

Present the result with the local URL or directly openable file, viewports checked, important post-inspection fixes, the Phase Accountability Ledger summary, component decisions including a justified no-dependency decision, motion coverage, accepted deviations, and honest remaining risks.

## Conflict Resolution Order

When guidance competes, decide in this order:

1. User's explicit requirements and constraints.
2. Existing product identity, stack, and design system.
3. Task completion, accessibility, safety, and content clarity.
4. Mobile context and input method.
5. Performance and maintainability.
6. Approved reference direction.
7. Visual novelty, effects, and delight.

Never average conflicting aesthetics. Choose the rule that serves this product and document the tradeoff.
