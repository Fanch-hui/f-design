# Open-Source Component Selection

Use this reference in Phase 5 and when a hard interaction primitive appears during implementation. Open-source code is leverage only when it reduces behavioral risk without importing a foreign visual system. Research project packages and repositories directly.

## Search Trigger

Search for a mature component when at least one is true:

- the interaction has substantial accessibility behavior, such as dialog, menu, combobox, date picker, tree, tabs, tooltip, drag-and-drop, or data grid;
- the feature requires difficult domain behavior, such as virtualization, charting, rich text, canvas editing, scheduling, maps, or gesture physics;
- the project already uses an ecosystem and the missing primitive belongs there;
- implementing and testing it locally would be materially riskier than adapting a proven package.

Do not add a dependency for simple layout, a basic button, a static card, a small list, or markup the current design system already covers.

## Existing-System Check

Before searching GitHub:

1. Inspect installed dependencies and lockfile.
2. Search the shared component directory and design-system docs.
3. Find comparable usage in the repository.
4. Identify the existing icon, form, overlay, table, chart, and motion choices.
5. Confirm whether the missing need is behavioral, visual, or both.

Prefer extending a compatible established system over mixing in a second one.

## Component Decision Register Is Mandatory

Create the register even when no package will be installed:

| Need/pattern | Existing project evidence | External search trigger | Candidates/current evidence | Decision: existing/external/local | Reason and adaptation | Accessibility/tests | Delivery evidence |
|---|---|---|---|---|---|---|---|

- Give every nontrivial primitive or domain behavior its own row.
- Group basic semantic HTML, links, buttons, and static layout into one local row when that is sufficient.
- Record decision `existing` or `local` and ledger status `evaluated-local` when the existing system or a small local implementation is the right choice. Explain why a dependency would add more cost than risk reduction.
- Do not leave provenance blank and imply the phase did not apply. The delivery report must state what was evaluated and why no dependency was added.
- When a need appears during implementation, add it to the register before choosing an API or writing custom behavior.

The register records the decision. The candidate table below supplies current evidence when external search is triggered. Follow `evidence-and-execution.md` for status and release rules.

## Live Evidence Required

Repository health changes. Use current GitHub/package sources at selection time. Record:

| Need | Candidate | GitHub/package URL | Popularity | Latest release/commit | License | Maintainers/issue health | A11y | Framework/SSR fit | Bundle/runtime cost | Styling fit | Decision |
|---|---|---|---|---|---|---|---|---|---|---|---|

Verify each field. Do not repeat stale popularity numbers from memory.

## Popularity Standard

The user does not want obscure repositories with only a handful of stars. Apply this policy:

- Reject single-digit and low-double-digit repositories by default.
- For general-purpose component libraries, prefer category leaders with hundreds to thousands of stars and broad real-world adoption; `1k+` is a strong default signal, not an absolute rule.
- For narrow specialized components, lower star counts can be acceptable only when maintenance, releases, documentation, tests, credible adopters, and technical fit are unusually strong and no mature alternative fits.
- Treat packages maintained by an established project or organization as stronger evidence than a star count alone.
- Document any exception instead of hiding it.

Stars indicate awareness, not quality. A popular abandoned or inaccessible library still fails.

## Health Checklist

### Ownership And Maintenance

- clear repository/package identity and release provenance;
- recent commits or releases appropriate to project maturity;
- more than one credible maintainer where possible;
- responsive issue/PR history;
- documented migration and versioning practices;
- no unaddressed security or abandonment signals.

### Legal And Supply Chain

- explicit license compatible with the project;
- package name and publisher match the repository;
- no suspicious install scripts or unexplained binary downloads;
- reasonable dependency tree and package integrity;
- changelog and release tags align with published versions.

### Technical Fit

- supports the repository's framework and version;
- supports SSR/RSC/hydration where relevant;
- TypeScript types and module format fit the build;
- acceptable browser support;
- tree-shaking/code-splitting behavior is understood;
- bundle, runtime, CSS, and network cost fit the feature;
- no duplicate React/runtime or conflicting style engine;
- API can express all required states and data ranges.

### Interaction And Accessibility

- keyboard model follows platform conventions;
- focus management, restoration, and escape behavior are correct;
- screen reader semantics and live-state announcements exist;
- touch and pointer paths are supported;
- reduced motion and high contrast can be respected;
- tests or documentation cover accessibility behavior.

### Styling Fit

- tokens, classes, slots, render props, or headless APIs permit adaptation;
- required markup is not locked to a foreign layout;
- default radii, shadows, colors, typography, and animation can be replaced cleanly;
- CSS/reset strategy will not leak across the product;
- the component can match desktop and independent mobile compositions.

## Selection Preference

Use this order:

1. Existing local component.
2. Existing primitive or library installed in the target project.
3. Headless/unstyled mature primitive that can consume project tokens.
4. Mature styled component whose behavior and visuals both fit.
5. Small local implementation when the behavior is simple.

Avoid mixing different menu, dialog, form, or focus-management systems on one surface. Avoid importing a full design system for one widget.

## Adaptation Contract

Never paste a demo component unchanged. Before installation, write the adaptation plan:

```text
Behavior retained:
Default styling removed:
Project tokens mapped:
Radius/surface/elevation changes:
Typography/icon changes:
Desktop layout integration:
Mobile composition changes:
Accessibility verification:
Wrapper/API boundary:
Bundle and lazy-loading plan:
Tests to add:
```

Integrate through a local wrapper when it stabilizes tokens, accessibility defaults, analytics, or API conventions. Do not wrap merely to rename every prop.

## Domain Guidance

Common categories worth researching rather than rebuilding:

- accessible overlays, menus, comboboxes, tabs, and tooltips;
- command palettes and keyboard navigation;
- toast/notification queues;
- date/time selection and calendars;
- sortable/virtualized tables and long lists;
- charts and data visualization;
- drag-and-drop and gesture recognition;
- rich text/code editing;
- carousels only when the product truly needs sequential media;
- advanced animation sequencing and layout transitions;
- 3D, maps, diagramming, parsing, physics, or game rules.

Evaluate current category leaders rather than hard-coding a permanent package list. Existing target-project dependencies may include a project's own primitives, React Aria, Radix, Base UI, Motion, GSAP, dnd-kit, TanStack tooling, Virtuoso, Recharts, or other mature options, but none is selected by name alone.

## Reject Conditions

Reject or replace a candidate when:

- its repository has token adoption and no stronger evidence;
- maintenance or license is unclear;
- keyboard or screen reader behavior is incomplete;
- visual adaptation requires brittle overrides;
- it introduces a second global CSS/reset or conflicting primitive system;
- it makes the mobile experience worse;
- it is larger or more complex than the feature;
- it forces card-heavy or dashboard-style composition unrelated to the task;
- its demo drives the design instead of the Product Brief and project design contract.

## Post-Integration Verification

Test the selected component in the actual page, not only Storybook or its demo:

- default, hover, focus-visible, active, disabled, loading, error, and success;
- keyboard and screen reader path;
- touch target and gesture behavior;
- long labels, localization, empty/large data, and constrained containers;
- portals/overlays near viewport edges and inside overflow contexts;
- SSR/hydration and route transitions;
- mobile first viewport and soft keyboard;
- reduced motion and high contrast;
- bundle/build output and console warnings.

Record the final repository URL, version, license, and adaptations in the delivery summary or project documentation.

## Phase Exit

This phase passes only when:

- every nontrivial behavior is represented in the Component Decision Register;
- each external candidate has current health, license, accessibility, compatibility, cost, and theming evidence;
- every selected external component is adapted to local tokens and verified in the real page;
- every existing/local decision states why it is lower risk and how its behavior was tested;
- the final delivery reports the decision even when no new dependency was installed.
