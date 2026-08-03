---
name: f-design
description: End-to-end frontend product design, implementation, and existing-interface optimization workflow. Use when Codex must plan, design, redesign, prototype, implement, audit, refine, or polish a website, web app, dashboard, marketing site, hybrid product, responsive mobile experience, design system, reference-image-to-code build, color system, dark mode, interaction states, imagery, or motion. Also use when an existing interface needs better hierarchy, layout, typography, palette, feedback, card restraint, mobile composition, accessibility, media integration, image transitions, motion fidelity, performance, or standards compliance. Run guided discovery before material design analysis, synthesize a project-specific DESIGN.md, keep desktop and mobile references on one content canon, record component and motion decisions, adapt mature GitHub components to the project, implement role-based color, imagery, and motion faithfully, and verify the result in a real browser without silently skipping phases.
---

# F-design

Design and deliver frontend products through one self-contained process. The synthesized design, component, accessibility, responsive, media, color, motion, and quality guidance needed for this workflow is included here. Use the native tools available in the current harness and own the work from discovery through browser verification.

## Operating Contract

Apply these rules before any stylistic preference:

1. **Reconcile existing project truth.** Read the nearest `AGENTS.md`, `DESIGN.md`, product requirements, design system, components, assets, routes, rendered UI, and conventions before proposing technology or visuals. Distinguish functional truth, documented intent, and accidental implementation drift instead of trusting any one source silently.
2. **Ask before material analysis.** After a factual repository scan, ask a short guided round about unresolved product, style, palette, imagery, and motion choices. Every choice question must include a visible free-form answer path, and the round must end with a separate open-ended question for additional requirements. Do not publish a Product Brief, analyze visual directions, generate references, or code until the user answers, already supplied equivalent detail, explicitly says there are no additional requirements, or delegates the choices.
3. **User task wins over visual fashion.** Classify the product and identify the primary job before choosing a layout.
4. **No page without purpose.** Define routes, states, first-viewport priority, and success criteria before generating references.
5. **One content canon across viewports.** Desktop and mobile references are different compositions of the same approved copy, content IDs, asset identities, data, user state, navigation, and actions. Mobile may reorder, condense, or progressively disclose; it may not silently invent or replace the product.
6. **No code before direction.** For material new builds or redesigns, confirm the Product Brief, Page and State Map, project design contract, and visual direction before implementation. If the user explicitly delegates decisions, record assumptions and proceed.
7. **Reference images are contracts when direction changes.** For new builds and substantial redesigns, produce a named desktop and mobile reference for every planned page. For focused optimization, use the live page and before screenshots as the baseline unless a new direction is required.
8. **Media belongs to the composition.** Preserve image identity, crop intent, focal point, layering, edge treatment, and reference transition behavior. Do not insert imagery as an unrelated rectangle after layout is finished.
9. **Color is role-based communication.** Use semantic tokens, controlled salience, complete component states, and deliberate theme mappings. Treat `60-30-10` as a diagnostic heuristic, never a quota; never rely on hue alone for meaning; never create dark mode by inversion.
10. **Open source is evidence-based.** Prefer mature, maintained GitHub projects, but adapt them to the current product. Never paste a library's demo styling into the project unchanged.
11. **Cards must be earned.** Do not use dashboard-card composition as the default grammar. Never nest cards. Use spacing, dividers, lists, tables, bands, or direct layout when content does not need an independent container.
12. **Mobile is a separate composition, not a separate product.** Re-prioritize, reorder, collapse, and reposition for phone use while preserving the content canon.
13. **Function before motion does not mean motion is optional.** Stabilize content, states, responsiveness, accessibility, and interaction behavior first; then implement every approved or reference-derived motion cue, or document an accepted omission.
14. **Browser evidence is required.** Builds, linters, and detectors support the review; screenshots, captured keyframes, and real interaction paths decide whether the UI is ready.
15. **No silent phase completion.** Keep a Phase Accountability Ledger. Every applicable phase must end as `implemented`, `evaluated-local`, `not applicable`, `blocked`, or `accepted omission`, with its decision and verification evidence. A written rule is not a delivered feature until the rendered product proves it.

## Choose The Work Path

- **New product or substantial redesign:** run all nine phases.
- **New page inside an established product:** inspect the foundation, run focused discovery and page/state definition, create references for that page on desktop and mobile, then continue from implementation.
- **Reference image or motion target to code:** preserve the repository foundation, inventory the static composition, media treatment, transition choreography, missing states, and mobile behavior, then continue from implementation.
- **Optimize an already-written webpage or product surface:** capture the live baseline, diagnose evidence, make prioritized improvements to structure, layout, typography, visual system, responsive composition, accessibility, and states, then compare before and after. Read [existing-surface-optimization.md](references/existing-surface-optimization.md) and follow the loop below.
- **Focused audit or repair:** inspect the product context, run the applicable quality gates, repair verified defects, and repeat browser checks. Do not stop at a report when the user asked to improve the code. Do not force unnecessary discovery artifacts.
- **Motion-only request:** first confirm that the surface works and has stable layout. Then run the motion phase and final review.

For substantial work, keep a live checklist and the Phase Accountability Ledger described in [evidence-and-execution.md](references/evidence-and-execution.md). Do not quietly skip a phase; state the reason and evidence when a phase is inapplicable.

## Existing Surface Optimization Loop

Use this loop for a webpage, component, flow, or application that already renders:

1. **Preserve the contract.** Identify the page's purpose, primary task, existing identity, shared design system, functional behavior, user-authored changes, and out-of-scope areas.
2. **Capture the baseline.** Start the real app and inspect desktop, tablet, and phone. Save and read before screenshots; exercise the primary flow and important states.
3. **Diagnose causes, not symptoms.** Separate information-architecture, hierarchy, layout, spacing, typography, color/surface, component, responsive, mobile, accessibility, content, state, motion, performance, and metadata problems. Cite concrete source locations and browser evidence.
4. **Prioritize.** Fix task blockers and mobile/accessibility defects first, then structural and system drift, then visual polish. Avoid broad restyling when a smaller change solves the cause.
5. **Improve in passes.** Correct structure and hierarchy, layout and rhythm, typography and copy, design-system alignment, responsive/mobile composition, interaction states and accessibility, then implement approved reference motion and add any other motion only when useful.
6. **Verify the delta.** Re-run build/tests, repeat the browser matrix, compare before and after at identical viewports, and check that function and identity were preserved.

For a normal optimization request, implement verified improvements instead of only proposing them. Generate new reference images when the user requests a redesign, the current direction is fundamentally wrong, or several pages need a newly approved system. Do not generate references merely to adjust spacing, typography, responsiveness, or standards compliance.

## Phase 1: Establish The Foundation

Run a factual scan before asking questions:

- Read `package.json`, lockfiles, framework config, routes, global styles, design documentation, token files, shared components, icon dependencies, assets, tests, and build scripts.
- Identify the current framework, rendering model, styling approach, component primitives, state/data layer, test tooling, browser support, and deployment constraints.
- Reuse an existing stack, component system, and icon family. Do not start a parallel app or add a second primitive system.
- For a greenfield project, choose technology from product needs rather than fashion. Explain the recommendation and ask only when the choice materially affects ownership, hosting, or maintainability.
- Record what is known, directly evidenced, and unresolved. Do not turn the scan into a visual-direction decision before the discovery gate.
- Classify external guidance by authority and freshness. Current standards and platform documentation outrank design-system examples, professional research, and community inspiration; none silently overrides explicit product evidence.

Read [discovery-and-architecture.md](references/discovery-and-architecture.md) for the product taxonomy, interview cadence, technology decision rules, and page-map contract.

## Phase 2: Discover And Classify The Product

For material new work, visual redesign, or ambiguous image-led work, stop at a **Discovery Gate** after the factual scan. Ask one guided round of two or three high-leverage direction questions plus one separate open-ended additional-requirements question, then wait for the answer before analyzing directions. Every direction question must offer a `Custom / 自定义：请填写` response in addition to suggested options. Ask a second round only when the answer exposes a material branch. Skip the gate only when the prompt and repository already answer the same questions and additional requirements, the user explicitly delegates the decisions, or the task is a small repair whose direction is established.

Resolve at least:

- audience, context, mental state, and primary job;
- success event and business outcome;
- product class and per-surface register: brand, product, or hybrid;
- content/data shape, roles, authentication, permissions, and realistic ranges;
- target platforms, accessibility level, localization, performance, SEO, and browser constraints;
- fidelity, breadth, timing, references, and anti-references;
- success measures for effectiveness, efficiency, errors/recovery, and user confidence, rather than click-through alone;
- preferred visual lane and rejected visual lane;
- palette strategy or hue families, light/dark preference, imagery/material treatment, and motion energy.
- user-authored custom directions, extra functionality or content, naming/copy, must-preserve details, prohibited elements, technical constraints, and any other requirements not covered by the suggested options.

Offer concrete choices grounded in the product instead of asking only "what style do you like?" Explain each option in one sentence, include a visible free-form option for each question, and allow the user to combine traits or ignore the suggestions and write their own direction. The final additional-requirements question must remain open-ended rather than another fixed choice list. Produce a compact **Product Brief only after this gate**. For a material build, present it for confirmation before visual exploration. If the user asks for autonomous execution, state the assumptions instead of blocking.

Never call something a dashboard merely because it contains data. A dashboard is justified only when monitoring, comparison, or triage across multiple signals is the primary recurring job.

## Phase 3: Define Functions, Pages, Flows, And States

Turn the brief into an implementation-sized scope:

1. Map the primary and secondary user flows.
2. Separate routes from tabs, overlays, drawers, dialogs, and data states.
3. List every page with purpose, audience, entry, primary action, key content, desktop composition, mobile first-viewport priority, and completion condition.
4. Add loading, empty, error, offline, success, disabled, permission, first-run, overflow, and long-content states where relevant.
5. Identify shared shells and templates without erasing page-specific needs.
6. Defer low-value features explicitly instead of leaving vague placeholders.

The result is the **Page and State Map**. Do not generate references or code until every planned page has an accountable role.

## Phase 4: Set The Visual System And Generate References

First define one visual system for the entire product:

- audience and emotional register;
- named references and named anti-references;
- palette roles, visual-weight budget, and contrast strategy;
- semantic feedback roles, component state colors, light/dark mappings, and data-color policy;
- typography roles and loading strategy;
- density, spacing, grid, shape, elevation, icon, image, and motion language;
- card policy and page-section grammar;
- desktop and mobile composition rules.

Existing identity wins unless the user explicitly requests departure. Brand surfaces may be expressive; task-focused product surfaces should feel quiet, familiar, and efficient. Hybrid products may use both registers, but shared tokens and identity must connect them.

Define a **Color Role Table**, **Theme Matrix**, and **Component State Matrix** before generating references. Use `60-30-10` only to diagnose visual balance; reserve salience for real hierarchy; keep brand, action, focus, and status meanings distinct. Read [color-system-and-states.md](references/color-system-and-states.md).

For a material new build, redesign, or multi-page system, synthesize a project-specific `DESIGN.md` from the Product Brief, existing project identity, user-provided references, and [design-reference-synthesis.md](references/design-reference-synthesis.md). Existing project design documentation remains authoritative.

Before generating any reference, freeze a **Page Content Canon** for every page: stable content IDs, approved copy, data/state, asset IDs, navigation, actions, and what mobile may reorder, condense, or defer. Both viewport prompts must consume this same canon.

Use native image generation when available:

1. Generate two or three structurally different direction probes when the direction is ambiguous.
2. Confirm one direction or proceed under explicit delegation.
3. Lock the project design contract before generating the full set.
4. Generate a named high-fidelity desktop reference for **every page**, then derive its mobile prompt from the locked page canon and desktop asset manifest. The mobile result is an intentional recomposition, not an independent invention.
5. Include critical alternative states when they materially change composition.
6. Keep shared shell, tokens, copy, state, asset identities, type, and component language consistent across all references.
7. Run a desktop/mobile parity audit after each pair. Regenerate any pair that changes core content, copy, asset identity, user state, navigation, or actions without an approved reason.
8. Maintain a reference manifest that links each image to its page, viewport, state, required assets, motion cues, and implementation notes.

Never rasterize core interface text or treat generated copy as approved product copy. Read [visual-system.md](references/visual-system.md) and [reference-images.md](references/reference-images.md) before this phase.

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

Preserve the approved reference's major ingredients: silhouette, hierarchy, density, imagery, crops, layering, motifs, navigation, CTA treatment, and motion cues. Translate it into semantic, maintainable code rather than tracing pixels blindly. Use real assets and real copy at presentation time. Do not ship dead controls, fake metrics, guessed image URLs, placeholder rectangles, or a second design language.

Read [implementation.md](references/implementation.md) for the implementation contract and card decision test. Read [media-and-image-transitions.md](references/media-and-image-transitions.md) whenever images or reference transitions matter.

## Phase 7: Audit Before Motion

Start the real development server and inspect the product in a browser. Run the repository's build, typecheck, lint, tests, accessibility checks, and relevant performance measurements, but do not treat passing automation as proof.

Verify at minimum:

- phone widths `320`, `375`, `390`, and `430`;
- a tablet portrait and landscape composition;
- desktop at `1280` and `1440`, plus the project's largest supported layout;
- keyboard-only flow, focus order, 200% zoom, reduced motion, long text, empty/error/loading states, and a throttled network when relevant;
- light/dark themes, component-state distinction, grayscale, high-contrast or forced-colors behavior, and color meaning without hue when relevant;
- console errors, broken assets, layout shift, horizontal overflow, overlays, sticky elements, and soft-keyboard behavior.

Compare screenshots to every approved reference. Confirm desktop/mobile content parity and static media start/end compositions. Run a dedicated card audit and a dedicated mobile first-viewport audit. Fix verified defects before adding motion.

Read [responsive-mobile.md](references/responsive-mobile.md) and [quality-gates.md](references/quality-gates.md).

## Phase 8: Add Motion And Microinteractions

Create a **Motion Coverage Matrix** before writing animation code. Audit direct-control feedback, state/overlay continuity, async status, navigation/layout continuity, media transitions, and brand/narrative motion; mark each category `implemented`, `not applicable`, or `accepted omission` with evidence and a reduced-motion result. Then create a **Motion Fidelity Manifest** for every explicit or implied cue in approved references, user-provided video/GIF/prototypes, and current product. For each cue, record the target, trigger, start/end frame, property, timing/ease, scroll relationship, responsive variant, reduced-motion result, and verification method. Map every cue to an implementation, `not temporal evidence`, or an explicitly accepted omission. A static still may define transition geometry or a visual state, but it does not authorize invented timing or choreography.

This phase is mandatory when the approved direction contains image reveals, wipes, masks, crop changes, parallax, shared-element movement, pinned sections, scroll-linked sequences, or other visible motion. Do not claim that motion is unnecessary when a reference depends on it.

A button press plus one toast fade is not complete motion delivery for an approved expressive, brand-led, or image-led surface. Such a surface needs its approved signature sequence or reference transition. A quiet task surface may legitimately use only restrained state motion, but the matrix must show that every applicable category was evaluated and verified.

- Product motion is fast and state-led. Frequent and keyboard-driven actions get no choreography.
- Brand motion may carry voice, but use one signature sequence instead of repeated fade-and-rise sections.
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
- mobile first viewports prioritize the page's actual job;
- no content is hidden, clipped, overlapped, or needlessly oversized;
- every interactive element has complete states and works with keyboard and touch;
- all planned states exist and recover cleanly;
- the implementation matches the approved references or documents accepted deviations;
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
