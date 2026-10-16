---
name: f-design
description: Design, implement, redesign, or improve frontend products with product-grounded structure, visual systems, responsive behavior, and purposeful motion. Use for websites, app interfaces, workspaces, editors, commerce, and reference-to-code tasks. Resolve delivery mode before material design work, preserve the existing project and user scope, and load only the references needed for the current step.
---

# F-design

A self-contained frontend design and delivery workflow. Use the host's available tools and the project's existing stack. Read the relevant reference sections as the task reaches them; do not load every module or invoke upstream skills by default.

## Working Contract

1. **Project truth first.** Read applicable `AGENTS.md`, design documentation, code, components, assets, and routes. Reuse the existing stack and system; obtain authorization before a material migration or parallel architecture.
2. **Task before style.** Classify each surface by its primary job and brand, product, or hybrid role. Derive identity from real subject facts; preserve familiar task behavior when it serves the work.
3. **Content determines structure.** Use representative copy, data, and available evidence before choosing geometry. Desktop and mobile share one approved Page Content Canon, with deliberate differences in composition.
4. **Direction before implementation.** Resolve material choices and confirm the Design Package, or record explicit delegation, before generating references or coding. Preserve approved structure and content through refinement.
5. **Real functionality and media.** Keep interactions within scope, use meaningful states and semantic controls, and distinguish actual business evidence from illustrative or demonstration material. Verify asset sources and licensing.
6. **Purposeful motion.** Establish legible static compositions first, then implement approved motion and reduced-motion behavior. Choose libraries by need and respect component lifecycle and cleanup.
7. **Evidence within scope.** Perform only applicable checks allowed by the user and host. When visual or interaction acceptance is manual, report it as awaiting user verification; source checks do not prove that acceptance.
8. **Focused completion.** Fix verified causes, preserve user-authored changes, and stop when scoped findings are resolved and evidence is sufficient. Repeat checks only for new changes or unresolved concerns.

## Choose The Work Path

| Request | Path |
|---|---|
| New product or substantial redesign | Run the material workflow below, beginning with factual discovery and the delivery-mode gate. |
| New page in an established product | Reuse the foundation; resolve page-specific choices, scope, design, and applicable implementation steps. |
| Supplied reference to code | Inspect the supplied target and requested fidelity; preserve the foundation. Use [reference-images.md](references/reference-images.md) and resolve any material choices still open. |
| Improve an existing surface | Follow [existing-surface-optimization.md](references/existing-surface-optimization.md): baseline, root cause, targeted change, permitted verification. Reopen design choices only for material redesign or structural change. |
| Focused audit or repair | Read the affected module and applicable quality gates. Repair verified defects when requested; do not force a full discovery or design package. |
| Motion only | Confirm stable content, layout, and behavior; follow the motion and relevant verification steps. |

For material builds, redesigns, and broad optimizations, keep a compact Phase Accountability Ledger using [evidence-and-execution.md](references/evidence-and-execution.md). A small repair needs only scoped findings, decisions, and checks.

## Delivery Mode Gate

For greenfield or material design work, perform only a factual project scan, then make **delivery mode the first visible standalone choice** before visual analysis, new architecture selection, scaffolding, image generation, or implementation:

1. **Design -> Generate References -> Implement**
2. **Design -> Direct Implementation**
3. **Hybrid:** generated references only for named pages or states
4. **Custom**, or explicit delegation such as `你定 / decide for me`

Stop for the answer unless the user already selected or explicitly delegated the mode. An empty project, absent reference, urgency, limited scope, or unavailable image tooling does not select direct mode. A focused repair of an established surface can use its existing direction.

Treat **reference input as a separate choice**: uploads, a website URL, the current/local page, no reference, or a custom combination. When architecture is unresolved, present viable experience and technical choices with tradeoffs. Offer free-form answers and a separate open-ended additional-requirements question; do not re-ask resolved choices. Follow the Discovery Gate in [discovery-and-architecture.md](references/discovery-and-architecture.md).

The chosen mode controls reference-image artifacts, not design quality. All material modes share the Design Package and content canon. Use [reference-images.md](references/reference-images.md) only for supplied targets or selected generated-reference/hybrid pages; direct pages do not need generated-image manifests or comparisons.

## Material Workflow And Reference Routes

Use the applicable parts of these phases. The linked module owns its detailed rules; read only what the current step needs.

| Phase | Decision or outcome | Main reference |
|---|---|---|
| 1. Foundation | Project facts, existing system, constraints, and genuine unknowns | [Discovery and architecture](references/discovery-and-architecture.md#repository-first-scan) |
| 2. Discovery | Resolved delivery mode, reference intake, architecture, Product Brief, and success criteria | [Discovery Gate](references/discovery-and-architecture.md#discovery-gate) |
| 3. Scope and structure | Flows, surface strategy, selected structure, pages/states, and shared content canon | [Surface strategy](references/surface-strategy-and-structure.md), [page and content definitions](references/discovery-and-architecture.md#page-and-state-map) |
| 4. Design | Product-grounded concept, visual system, responsive composition, and confirmed or delegated Design Package | [Visual system and Design Package](references/visual-system.md), [responsive composition](references/responsive-mobile.md) |
| 5. Components | Existing, local, or external implementation selected for the actual need | [Component selection](references/open-source-components.md) |
| 6. Implementation | Semantic structure with representative content, complete behavior/states, and project-aligned code | [Implementation](references/implementation.md) |
| 7. Pre-motion review | Applicable task, static composition, accessibility, and responsive findings resolved or reported | [Quality gates](references/quality-gates.md) |
| 8. Motion | Approved feedback/choreography, appropriate coverage, interruption, lifecycle, and reduced-motion behavior | [Motion and interaction](references/motion-and-interaction.md) |
| 9. Delivery | Verified outcome, remaining manual acceptance, and sufficient evidence | [Delivery evidence](references/quality-gates.md#delivery-evidence), [accountability](references/evidence-and-execution.md) |

When structure needs exploration, compare two or three credible directions grounded in the same facts and content. Apply the bounded-originality gate and retain a low-risk fit. The selection must allow **select, combine compatible parts, custom, reject/regenerate, or delegate** before the Design Package; follow [structural selection](references/surface-strategy-and-structure.md#selection-gate).

Load these supporting modules only when their trigger exists:

- **New or materially changed design contract:** [design-reference-synthesis.md](references/design-reference-synthesis.md), including project identity and any permitted references.
- **Color roles, themes, or interaction-state colors:** [color-system-and-states.md](references/color-system-and-states.md).
- **Shared tokens/components, page overrides, or compatibility changes:** [design-system-governance.md](references/design-system-governance.md).
- **Prominent imagery or media transitions:** [media-and-image-transitions.md](references/media-and-image-transitions.md).
- **Supplied visual targets or selected reference generation:** [reference-images.md](references/reference-images.md), after the shared Design Package is settled.

## Completion Evidence

Report the usable URL or artifact, what changed and why, applicable checks actually run, and unresolved acceptance or blockers. For material work, summarize component decisions, motion coverage, and relevant structural/reference fidelity from the existing records. Do not claim a phase or visual check completed from written rules, installation, or source changes alone.

## Conflict Resolution Order

User requirements and scope -> existing product/system -> task completion, accessibility, and safety -> mobile context -> performance and maintainability -> approved references -> visual novelty. Resolve conflicts for this product rather than averaging incompatible styles.
