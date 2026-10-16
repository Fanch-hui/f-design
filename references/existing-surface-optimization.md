# Existing Surface Optimization

Use this route when a webpage, component, flow, or application already exists and the user asks to improve its quality. Preserve working behavior and identity while resolving verified defects in the affected scope.

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

| Mode | Trigger | Scope |
|---|---|---|
| **Tune-Up** | Direction is sound but execution is rough | Improve hierarchy, spacing, typography, consistency, responsiveness, states, accessibility, and polish within the existing architecture and identity. |
| **Structural Improvement** | Information architecture, workflow, content priority, or mobile composition blocks the task | Reorganize the affected surface while preserving product scope, data behavior, and recognizable identity. Resolve unclear material flow changes before implementing them. |
| **Visual Redesign** | The user requests a new direction or the existing system prevents the desired outcome | Identify what changes and what stays, resolve the delivery mode, and implement from the approved Design Package or generated references for selected pages. |
| **Standards Repair** | Accessibility, responsiveness, metadata, performance, state coverage, system drift, or code quality is the primary defect | Repair the relevant standard without unnecessary visual churn. |

Do not turn a polish request into a redesign or reduce an explicit redesign to cosmetic patches.

## Establish The Contract

Before editing, establish the target, primary task, audience, requested scope, existing identity, functional states, and shared system. Identify user-authored and in-progress changes so edits preserve their intent. Include supported contexts and explicit anti-goals.

Use repository evidence first: product/design documentation, neighboring surfaces, tokens, components, assets, screenshots, tests, and relevant history. Resolve contradictions using [evidence authority](evidence-and-execution.md#evidence-authority). Update project `DESIGN.md` only when a change establishes a durable rule.

For structural improvement or visual redesign, follow the [Discovery Gate](discovery-and-architecture.md#discovery-gate). Tune-ups and standards repairs need no interview when their contract is already evident.

Classify each affected surface using [surface strategy and structural exploration](surface-strategy-and-structure.md):

- tune-up and standards repair normally need no exploration; identify the suitable existing structure;
- structural improvement needs exploration when multiple viable task, information, or interaction topologies remain;
- visual redesign needs exploration unless an approved target or established structure resolves topology;
- mixed requests may explore named pages or axes while preserving the rest.

Confirm or use existing authorization for material changes to learned behavior. Preservation must not retain a structure proven to block the task.

Keep the contract compact:

```text
Target and primary task:
Optimization mode:
Surface strategy and exploration decision:
Identity, behavior, and user changes to preserve:
Evidence that defines the system:
Requested improvements and exclusions:
Viewports/states and permitted verification:
```

## Capture The Baseline

Use evidence available within the user's and host's permitted verification scope:

- inspected user-supplied screenshots, recordings, or approved references;
- source, design documentation, tokens, tests, and existing runtime evidence;
- rendered desktop/mobile states and interaction observations when browser inspection is authorized.

When permitted and useful, start the real development server and inspect the rendered surface. Do not require automated browsing for a task whose experience acceptance belongs to the user. Source evidence supports implementation findings; it does not prove rendered quality or successful interaction.

Choose representative viewports and states from the affected behavior: first viewport, long content, overlays, forms, loading/error/empty states, keyboard, or reduced motion as applicable. Expand only when the change or an unresolved concern justifies it. Follow [responsive review](responsive-mobile.md) for mobile composition.

Read every screenshot used as evidence. Use section-sized captures for long pages; a scaled full-page thumbnail can hide defects. Record each material symptom, intended behavior, responsible code, and whether it is verified, inferred, or proposed. Distinguish intentional design, implementation drift, and stale documentation before editing.

For a shared token or component, identify consumers and select representative neighboring surfaces within the allowed scope. If visual or interaction comparison remains manual, name it as unverified until results arrive.

## Diagnose Root Causes

Classify the defect before choosing a fix:

| Area | Typical symptoms | Likely cause |
|---|---|---|
| Product and information architecture | Wrong primary task, competing actions, unclear completion, disconnected decision context, excessive steps | Missing product decision or unsuitable structure |
| Layout and composition | Weak grouping, arbitrary spacing, unsuitable density/grid, nested containers, unstable dimensions | Design-system drift, local implementation, or unsuitable hierarchy |
| Typography and content | Weak role hierarchy, unreadable text, overflowing labels/translations, vague actions or errors | Content problem, missing tokens, or local implementation |
| Visual system and media | Ambiguous color meaning, inconsistent surfaces/icons, generic identity, imagery disconnected from its composition | Design-system drift or missing shared contract |
| Components and interaction | Duplicate primitives, missing feedback, inaccessible controls, clipped overlays, lost input | Missing shared component or incomplete state/accessibility behavior |
| Responsive and mobile | Compressed desktop layout, overflow, hidden actions, keyboard/sticky collisions | Responsive composition failure |
| Standards and engineering | Semantic failures, missing recovery, broken metadata, layout shift, rendering/build errors, orphaned code | Incomplete behavior or performance/engineering defect |

Fix the responsible decision, shared primitive, or composition rather than masking its visible symptom. Keep uncertain findings separate from confirmed defects.

## Prioritize Findings

Use [quality severity](quality-gates.md#severity):

- **P0:** blocked primary task, data loss, blank render, or dangerous behavior;
- **P1:** major confusion, accessibility failure, broken navigation/state, severe clipping, or mobile task failure;
- **P2:** material hierarchy, typography, system, content, or performance defect with a workaround;
- **P3:** minor optical polish with no task impact.

Resolve functional and mobile/accessibility blockers first, then structure and hierarchy, shared-system consistency, responsive/state completeness, visual craft, and purposeful motion.

An optimization request includes implementing verified in-scope findings. Return findings only when the user requests an audit or plan.

## Optimization Passes

Apply only relevant passes; each module owns its detailed rules and existing artifacts.

### Structure And Hierarchy

Make the purpose and primary action clear. Regroup secondary content, keep necessary decision context available, and preserve URLs, data ownership, and expected behavior unless change is authorized. Follow [structural selection](surface-strategy-and-structure.md#selection-gate) when topology changes.

For brand surfaces, trace the governing concept through affected content and composition using [Subject-World Identity](visual-system.md#subject-world-identity). Keep familiar task patterns where they already serve the work.

### Layout, Typography, And Copy

Repair grouping, alignment, density, reading order, and content fit. Select layout from content relationships rather than a preferred template. Use the existing role-based type/spacing system and improve labels, errors, and terminology with their containers.

Use [visual-system rules](visual-system.md) for layout grammar, card decisions, typography, and copy. Avoid unrelated styling changes when a narrower responsible fix resolves the defect.

### Visual System, Color, And Media

Repair shared tokens and components before adding one-off values. Preserve approved identity and reconcile durable changes with the [design-system source of truth](design-system-governance.md#source-of-truth).

Read only the affected specialist rules:

- [color roles, themes, and interaction states](color-system-and-states.md);
- [media composition, crops, layering, and transitions](media-and-image-transitions.md).

Fix an appended image's surrounding composition when necessary; a new border or wrapper alone does not establish its product role.

### Components And Implementation

Check existing primitives before selecting dependencies or extracting shared patterns. Use [open-source component selection](open-source-components.md) for nontrivial missing behavior and the existing [Component Decision Register](evidence-and-execution.md#component-decision-register) for its decision.

Follow [implementation](implementation.md) for semantic structure, state ownership, content, forms, overlays, accessibility, resilience, and technical cleanliness. Preserve user input and recovery while changing presentation.

### Responsive Composition And States

Define phone first-viewport priority before changing CSS. Transform dense navigation, data, and controls around the mobile task; do not merely shrink desktop. Use [responsive-mobile](responsive-mobile.md) for overflow ownership, keyboard, safe areas, and input behavior.

Complete the states affected by the change using [implementation](implementation.md) and [quality gates](quality-gates.md). Verify realistic content and interruptions where relevant to the defect.

### Motion And Performance

Refine motion after function, layout, states, and responsiveness are stable. Follow [motion-and-interaction](motion-and-interaction.md) and its existing coverage/fidelity contracts; approved choreography remains part of the requested outcome.

Keep frequent actions fast and state-led. Remove motion without a purpose and measure actual bottlenecks before changing rendering or bundles. Select relevant checks from [performance and resilience](quality-gates.md#gate-9-performance-and-resilience).

## Reference Image Decision

Existing evidence is normally sufficient for tune-ups and standards repair. Consider new references for an explicit redesign, unresolved major composition, a new shared visual system, a major page without design evidence, or image-led composition needing exploration.

Generate only for pages selected in generated-reference or hybrid mode. Follow [reference-images](reference-images.md) for Design Package prerequisites, desktop/mobile content parity, asset identity, and comparison. Direct pages implement from their approved Design Package.

Do not generate references merely for spacing, type, responsive behavior, component states, accessibility, metadata, or performance fixes.

## Before And After Verification

Within permitted scope, compare matching before/after viewports and states. Select comparisons that explain the intended improvement:

- task clarity, reading order, grouping, density, and content fit;
- system consistency, identity, and affected color/theme states;
- mobile priority, action visibility, overflow, overlays, and sticky behavior;
- affected interaction, focus, recovery, media crops/transitions, and desktop/mobile parity.

Use [quality-gates](quality-gates.md) to select checks in proportion to the change: applicable repository checks plus authorized visual, accessibility, interaction, responsive, or performance evidence. Keep required manual comparisons unverified until the user provides results; code diffs alone do not prove experience improvement.

For a further revision, name the highest-impact unresolved finding and change the smallest responsible area. Stop when scoped findings are resolved and applicable evidence is sufficient. A new change or unresolved concern can justify another check; preference alone does not justify repeating the full matrix or extending the redesign.

## Delivery Contract

Use the existing [Delivery Evidence](quality-gates.md#delivery-evidence) and [execution accountability](evidence-and-execution.md). Include:

- target, optimization mode, and root causes fixed by user impact;
- structural decision and preserved behavior/identity boundaries;
- important changes and relevant component/motion decisions;
- baseline and after evidence inspected, checks run, and their results;
- required manual acceptance, unresolved risks, or contexts not checked;
- an openable development URL or file when available.

Use existing artifacts instead of creating duplicate optimization records. Report applicable decisions and evidence even when existing/local implementation is selected and no dependency is added.

## Prohibited Behavior

- Do not replace the interface to express personal taste or erase identity during polish.
- Do not expand structural exploration to unrelated routes, flows, or shared patterns.
- Do not present recolors as structural alternatives or repair pixels while retaining a broken flow.
- Do not overwrite user-authored changes, add dependencies before checking primitives, or elevate accidental code into a new system.
- Do not leave mobile as a compressed desktop derivative or add motion before the underlying behavior is stable.
- Do not claim browser, device, accessibility, performance, or user verification that was not run.
