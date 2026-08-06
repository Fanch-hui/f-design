# Design System Governance

Use this reference when a build creates or changes shared tokens, components, patterns, or documentation. It keeps generated pages and one-off visual experiments from becoming accidental system truth.

## Source Of Truth

Identify the canonical owner before editing:

| Concern | Canonical source | Generated outputs or consumers | Owner | Verification |
|---|---|---|---|---|
| Primitive tokens |  |  |  |  |
| Semantic tokens |  |  |  |  |
| Component tokens |  |  |  |  |
| Shared components |  |  |  |  |
| Usage documentation |  |  |  |  |

Existing project code and maintained design documentation win. A generated image, temporary page override, or copied library theme is evidence to reconcile, not a new master source.

Use a layered token model:

1. **Primitive:** raw color, size, font, duration, radius, and elevation values.
2. **Semantic:** roles such as surface, text, action, focus, success, warning, error, spacing intent, and motion intent.
3. **Component:** mappings for a component part and state, such as button background on pressed or field border on invalid.

Name tokens by stable meaning, not the page where they first appeared. Keep the dependency direction primitive to semantic to component. Components do not reach around semantic roles to consume arbitrary primitive values without a documented exception.

## Master And Surface Overrides

Maintain one master system for shared identity and behavior. A page or surface override is allowed only when:

- the surface has a documented register, context, density, or accessibility need;
- the override uses a named semantic purpose;
- affected states and themes remain complete;
- the override does not redefine global identity accidentally;
- its owner and removal or promotion condition are recorded.

Do not overwrite the master system to make one generated page look internally consistent. If an override repeats with the same intent, evaluate promotion through the change process below.

## Component Contract

For every shared interactive component, document:

- purpose and when not to use it;
- anatomy, slots, content limits, and composition rules;
- properties, variants, defaults, and controlled/uncontrolled behavior;
- default, hover, focus-visible, active, selected/expanded, disabled/read-only, loading, error, success, empty, and overflow states as applicable;
- responsive, touch, keyboard, focus, screen-reader, localization, and reduced-motion behavior;
- semantic and component tokens consumed;
- data/state owner and events emitted;
- tests, examples, known limits, and migration notes.

Prefer composition over a component with dozens of unrelated configuration flags. Keep data fetching and workflow orchestration outside presentational components when that separation makes responsibilities and tests clearer. Colocate implementation, styles, tests, stories/examples, hooks, and types according to repository conventions.

## Change Classification

Classify a shared change before implementation:

- **Patch:** fixes behavior or documentation without changing the public contract.
- **Compatible feature:** adds a token, state, variant, or capability without breaking existing consumers.
- **Breaking change:** removes, renames, reinterprets, or materially changes a token, component contract, DOM/focus behavior, or visual role.

A breaking change requires affected-consumer inventory, migration instructions, a deprecation window when practical, and before/after verification. Changing a shared token value can be materially breaking even when its name remains stable; inspect representative consumers instead of assuming compatibility.

## Handoff And Verification

Record:

- implementation path and exported API;
- design-to-code token mapping;
- representative examples and anti-examples;
- accessibility expectations and interaction model;
- responsive and theme behavior;
- visual regression, unit, interaction, accessibility, and contrast checks;
- changelog entry and migration/deprecation notes when required.

Evaluate system health through adoption, repeated defects, divergence, delivery friction, accessibility regressions, and upgrade cost. Component count is not a success metric. Do not promote a one-off treatment merely to make the system appear comprehensive.

## Exit Gate

- One canonical source is named for each shared concern.
- Primitive, semantic, and component layers remain separable.
- Surface overrides are explicit and bounded.
- Shared component contracts cover behavior, states, accessibility, responsiveness, and tokens.
- Affected consumers were identified and rendered after shared changes.
- Breaking changes include migration and deprecation handling.
- Generated references when selected and all implementation use the same master system plus approved overrides.
