# Evidence And Execution Accountability

Use this reference across all F-design paths. It prevents a sound rule from being treated as optional merely because the implementation agent did not mention it.

## Evidence Authority

Keep product truth and external guidance distinct. Record only the evidence needed to explain a material decision.

| Tier | Evidence | Appropriate use |
|---|---|---|
| Project truth | Explicit user requirements, rendered behavior, repository code, product data, approved references | Defines this product unless it conflicts with safety, law, or an explicitly accepted change |
| S | Current ratified standards, laws, platform requirements, primary specifications | Compliance, accessibility, semantics, platform behavior, auditable thresholds |
| A | Official mature design systems and framework/library documentation | Proven patterns, component behavior, tokens, platform conventions |
| B | Professional research, usability studies, credible engineering guidance | Decision support and hypotheses that still require product validation |
| C | Community posts, galleries, tutorials, popularity, trend examples | Inspiration and search leads, never sole authority for a threshold or claim |

For a material claim, capture the source, authority tier, date or version when it can drift, what decision it controls, and confidence as `verified`, `inferred`, or `proposed`. Verify current library health and standards at execution time. High stars, likes, or repeated advice show awareness, not correctness.

When evidence conflicts, apply the Conflict Resolution Order in the main F-design contract. Do not average incompatible guidance or let a generic design system silently overwrite the existing product.

## Allowed Phase Statuses

Every applicable phase or required artifact ends with one of these exact statuses:

- `implemented`: present in the product and verified;
- `evaluated-local`: the need was assessed and existing or local semantic implementation was intentionally selected;
- `not applicable`: the trigger does not exist, with a concrete reason;
- `blocked`: implementation cannot proceed, with the blocker and impact reported;
- `accepted omission`: an applicable item was deliberately omitted with the user/product owner's acceptance, reason, risk, and revisit condition.

`Skipped`, `later`, silence, or a final report section that says only `none` is not an acceptable status. An agent may narrow a focused repair to applicable rows, but it may not erase the rows.

## Phase Accountability Ledger

Maintain this ledger for material builds, redesigns, and broad optimizations. A focused repair may use a shorter version.

| Phase/artifact | Trigger and scope | Status | Decision/reason | Source/code evidence | Verification | Remaining risk |
|---|---|---|---|---|---|---|

At minimum consider:

- discovery response record with free-form choices and a separate additional-requirements answer;
- Design Delivery Mode Record naming generated-reference, direct, hybrid, custom, or delegated mode; the user's verbatim selection/delegation; page/state boundaries; required artifacts; and explicit skips;
- Reference Intake Record covering upload, URL, local/current page, named inspiration, no-reference, custom, or delegated input, including inspection limits and asset rights;
- Architecture Decision Record covering experience and technical options, recommendation, consequences, and the user's selection, custom answer, or explicit delegation;
- Product Brief, Page and State Map, and success measures;
- Surface Strategy Record covering each material surface's dominant job, core objects/content, interaction topology, first-viewport priority, mobile task change, constraints, and structural-exploration decision;
- Structural Direction Matrix and selected Structural Direction Record when exploration is required, including meaningful structural axes, bounded-originality results, the user's wording, and rejected alternatives; otherwise concrete evidence for `not required` or an approved omission;
- project design contract, Color Role Table, Theme Matrix, and state coverage;
- Visual Calibration Record for expressive variance, information density, and motion energy, plus the subject-world inventory and selected signature;
- Design System Governance Record naming the master source, allowed surface overrides, component contracts, and compatibility/migration impact;
- Page Content Canon and desktop/mobile design parity in all modes;
- generated Reference Manifest, generated desktop/mobile pair audit, and reference-to-code comparison only for pages selected under generated-reference or hybrid mode;
- Component Decision Register;
- media contract when prominent imagery exists;
- Motion Coverage Matrix and, when cues exist, Motion Fidelity Manifest;
- Iteration Decision naming targeted edit, variant exploration, or full regeneration and the locked/changeable axes;
- responsive, accessibility, browser, state, performance, and build verification.

A phase is not complete because a file was edited. Its row needs observable product or test evidence. Update the ledger when implementation reveals a new component, state, breakpoint, asset, or motion requirement.

## Component Decision Register

Create this before Phase 6:

| Need/pattern | Existing project evidence | External search trigger | Candidates/current evidence | Decision: existing/external/local | Reason and visual adaptation | Accessibility/tests | Delivery evidence |
|---|---|---|---|---|---|---|---|

Rules:

- Give dialogs, menus, comboboxes, date pickers, data grids, virtualization, charts, drag-and-drop, rich text, carousels, gestures, and advanced sequencing individual rows when present.
- A simple page may group semantic HTML, basic buttons, links, and static layout into one `local` row.
- `No new dependency` is a valid outcome only after the existing system and search trigger were evaluated. Report `evaluated; existing/local implementation selected because ...`.
- Complex behavior implemented locally needs a reason why existing and mature external primitives were unsuitable, plus keyboard, focus, screen-reader, touch, state, and maintenance evidence.
- An external selection records repository/package URL, version, license, current health, local wrapper or token mapping, bundle impact, and verification.
- Adding a package without a register row fails the phase. Leaving the register empty because no package was added also fails it.

## Motion Coverage Matrix

Audit the whole affected surface before selecting a library:

| Surface/event | Coverage category | Purpose/reference cue | Implementation or reason | Reduced-motion result | Browser/frame evidence | Status |
|---|---|---|---|---|---|---|

Consider every category:

1. **Direct control feedback:** press, selection, focus, drag, disclosure.
2. **State and overlay continuity:** tabs, menus, dialogs, drawers, expanding regions, list/detail identity.
3. **Async feedback:** loading, progress, background work, success, error, undo, cancellation.
4. **Navigation and layout continuity:** route/view changes, reordering, filters, responsive transitions when continuity helps.
5. **Media and image transitions:** reveal, crop, mask, wipe, shared media, gallery, hero, or approved reference choreography.
6. **Brand or narrative motion:** one signature entrance or sequence when the approved brand direction calls for expressive motion.

Not every category needs animation. Every category needs a decision. Avoid motion that has no named purpose, but do not use restraint as a reason to omit approved choreography.

Minimum interpretation:

- A quiet product surface can pass with immediate state feedback, honest async status, appropriate overlay/view continuity, and a coherent reduced-motion path.
- An expressive brand, hybrid public, or image-led surface whose brief or references call for motion needs the approved signature or media sequence. A button scale and a single toast fade do not satisfy that contract.
- If reference motion exists, expand each cue into the Motion Fidelity Manifest and verify start, midpoint, end, interruption, mobile behavior, cleanup, and reduced motion.
- The selected primitive may be CSS, platform APIs, the existing library, or GSAP. Library installation is not the goal; complete, verified behavior is.

## Outcome Evidence

For material product work, define success beyond visual preference:

- effectiveness: can the primary task be completed correctly;
- efficiency: time, steps, and unnecessary decisions;
- errors and recovery: frequency, severity, preserved input, and undo/retry;
- confidence and satisfaction: whether users understand state, consequence, and completion;
- accessibility and context: keyboard, screen reader, zoom/reflow, touch, reduced motion, realistic mobile conditions.

Do not invent user-test results or turn a small qualitative sample into precise population statistics. If user testing was not run, report task walkthrough and browser evidence honestly.

## No-Silent-Skip Release Gate

Treat these as release failures:

- a material phase is declared complete without a ledger status and evidence;
- a material build starts visual analysis or scaffolding without a resolved delivery mode, reference-input path, and user-selected or explicitly delegated architecture;
- a material surface reaches visual-system work, image generation, scaffolding, or implementation without a Surface Strategy Record;
- required structural exploration is skipped, hidden inside a style/palette choice, or presented as several recolors of one skeleton;
- a structural direction is selected without user choice/delegation, or survives only because it is novel despite failing task clarity, familiar orientation, mobile, accessibility, state, feasibility, or content-evidence checks;
- a greenfield or material design task records direct mode without an explicit user selection or explicit delegation;
- generated page images are created before the Design Package is complete, or are created for direct-mode pages without the user changing the mode;
- direct-mode pages are failed for missing generated references, manifests, parity audits, or generated-reference comparison;
- a supplied website is described as inspected without browser/web evidence, or its proprietary copy, brand assets, or unlicensed media are reproduced without permission;
- a nontrivial primitive is absent from the Component Decision Register;
- the final report omits component evaluation merely because no dependency was added;
- the Motion Coverage Matrix is missing for a material build/redesign or requested motion work;
- approved/reference-derived motion is replaced by only generic hover, button, or toast transitions;
- a required matrix or manifest item remains pending without an accepted omission;
- browser, accessibility, performance, or user evidence is claimed without actually being run.

Before delivery, summarize the ledger, component decisions, motion coverage, verification performed, accepted omissions, and remaining risks. This summary is part of the feature, not administrative commentary.
