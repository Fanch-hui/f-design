# Surface Strategy And Structural Exploration

Use this reference for every material new build, page addition, redesign, or structural optimization. Its purpose is to prevent one familiar website or application skeleton from being recolored across unrelated products without turning novelty into a goal.

## Core Rule

Classify and design each meaningful surface by its primary job. A project may contain several surface strategies: a public acquisition page, an authenticated workspace, a checkout flow, and an account area do not need the same composition or pacing.

Product taxonomy is a diagnostic lens, not a template catalog. Do not select a layout merely because a page was labeled `marketing`, `dashboard`, `editor`, or `commerce`.

## Surface Strategy Record

Create one row per route or meaningfully distinct full-screen state before structural exploration:

| Surface | Product/surface class | Primary user and context | Primary job and success event | Core objects/content | Interaction topology | First-viewport priority | Mobile task change | Existing constraints | Exploration decision |
|---|---|---|---|---|---|---|---|---|---|

Classify the surface by the work it must support. Useful families include:

- brand, institutional, campaign, launch, portfolio, editorial, documentation, or public content;
- task workspace, CRUD/workflow, collaboration, operations, administration, or developer tooling;
- editor, canvas, timeline, builder, preview, or other direct-manipulation tool;
- catalog, discovery, product detail, configuration, cart, checkout, order, or account commerce;
- feed, community, publishing, media consumption, search, directory, or knowledge retrieval;
- monitoring, comparison, diagnosis, reporting, investigation, or decision support;
- authentication, onboarding, form, settings, permissions, recovery, or other bounded flow;
- hybrid surfaces that combine public communication and signed-in tasks.

When a surface fits several families, name the dominant job and the secondary role. Do not let the secondary role obscure the first action.

## Exploration Trigger

For every surface, record `required`, `not required`, or `accepted omission`.

Structural exploration is **required** when any of these is true:

- the project or surface is greenfield;
- a new page has more than one plausible information or interaction architecture;
- a redesign materially changes hierarchy, navigation, primary flow, or responsive composition;
- the current structure fails the primary task or is itself the problem;
- the user asks for alternatives, stronger differentiation, or a new product identity;
- visual direction is being chosen without an established structural contract.

It is normally **not required** when:

- the task is a focused repair with an established and suitable structure;
- an approved design system and page template already resolve the topology;
- the user requests faithful implementation of an explicit target and its structure is usable;
- only local spacing, typography, component state, accessibility, performance, or motion defects are changing;
- a new state or small feature clearly belongs inside an existing pattern.

`Not required` needs concrete evidence. Existing code alone does not prove that its structure is suitable. `Accepted omission` needs the user's acceptance, reason, risk, and revisit condition.

## Structural Axes

When exploration is required, derive two or three product-grounded directions. Compare only axes that materially affect the user's task:

1. information architecture and route/view topology;
2. navigation and orientation model;
3. primary task exposure and first-viewport composition;
4. grouping, sequence, hierarchy, and progressive disclosure;
5. relationship among list, detail, controls, evidence, data, media, and workspace;
6. interaction model: browse, search, compare, manipulate, configure, complete, monitor, or investigate;
7. density, scanning rhythm, and decision cadence;
8. desktop, tablet, and mobile re-composition;
9. continuity, feedback, and motion strategy;
10. technical and content consequences that materially constrain the design.

Do not count palette, typeface, radius, shadow, illustration style, or animation intensity as structural differences by themselves.

## Structural Direction Matrix

Use the same approved product facts, copy, content IDs, representative data, and asset identities across candidates. Record:

| Axis | Direction A | Direction B | Direction C |
|---|---|---|---|
| Governing idea | | | |
| Primary task path | | | |
| Information architecture | | | |
| Navigation/orientation | | | |
| First-viewport composition | | | |
| Content/object relationships | | | |
| Interaction and disclosure | | | |
| Desktop/tablet/mobile strategy | | | |
| Media/data role | | | |
| Motion/continuity role | | | |
| Familiar conventions retained | | | |
| Main benefit | | | |
| Cost and risk | | | |

Each pair must differ on at least three applicable structural axes, including the primary task path, information architecture, or object relationship. If the candidates share the same skeleton and only change styling, merge them into one visual direction and explore a real structural alternative.

Do not force three candidates when only two are credible. Do not invent a weak wildcard to fill a quota.

## Bounded Originality Gate

Every direction, including the conservative one, must pass before it is shown to the user:

- the primary task and next action are understandable without design commentary;
- the structure follows actual content, data, workflow, and user context;
- common conventions are retained unless changing one creates a named benefit;
- unconventional interaction is limited to what the product can teach, support, and make accessible;
- navigation, back/cancel/recovery, state visibility, and orientation remain predictable;
- the mobile composition preserves the job without merely stacking desktop regions;
- keyboard, touch, zoom, screen reader, and reduced-motion paths remain viable;
- realistic content ranges, loading/error/empty states, and localization fit;
- implementation, maintenance, performance, and asset requirements are proportionate;
- the direction does not rely on fake metrics, invented evidence, decorative complexity, or unsupported media.

Reject a direction when its main justification is novelty, premium appearance, visual drama, or being unlike other websites. At least one presented direction must be a low-risk fit. A bolder direction may introduce one governing unconventional move; additional deviations need separate product evidence.

## Surface-Specific Questions

Ask the questions that expose real structural choices for the classified surface:

- public communication: what must be understood, trusted, inspected, or acted on, and in what evidence order;
- task products: what object or workflow should open first, what repeats, and what needs persistent context;
- editors and workspaces: whether canvas, document, timeline, preview, layers, or output owns the primary area;
- commerce: whether users discover, compare, configure, validate trust, or purchase with known intent;
- content and knowledge: whether entry is feed, topic, search, author, chronology, or task-based retrieval;
- analytics and operations: whether the job is monitoring, triage, diagnosis, comparison, investigation, or reporting;
- forms and onboarding: what users know at entry, what can be deferred, how progress and recovery work, and what belongs in the first viewport.

These questions reveal topology; they do not prescribe a page type. Do not translate every answer into a hero, sidebar, card grid, dashboard, or wizard by reflex.

## Selection Gate

Present the viable directions before the final Design Package. For each direction, state its governing idea, task benefit, familiar conventions, main tradeoff, mobile consequence, and implementation risk. Let the user:

- select one direction;
- combine named parts without averaging incompatible structures;
- write a custom structure;
- reject the set and request another bounded exploration;
- explicitly delegate the selection.

The final selection question must visibly repeat all five paths: select, combine, custom, reject/regenerate, or delegate. Do not end with an A/B/C-only prompt, even when the direction cards themselves are labeled A/B/C. Record the user's wording and the selected structure. When delegated, choose the direction with the strongest product evidence and lowest unresolved task risk, not the most visually novel option.

After selection, freeze the chosen structure in the Page and State Map and Design Package. Visual-system work may refine presentation, but it may not silently revert to another candidate or a familiar generic skeleton.

## Structural Convergence Audit

Before implementation and during final review, compare the selected structure with common reflex patterns. Investigate when unrelated projects repeatedly receive:

- the same navigation, first-viewport split, centered headline, feature sequence, testimonial block, call to action, and footer order;
- the same sidebar, top bar, summary tiles, equal cards, chart row, and activity feed regardless of the actual task;
- the same list-detail arrangement when the work needs a canvas, queue, timeline, comparison, report, or focused flow;
- identical desktop regions merely stacked on mobile;
- one signature decoration added to an otherwise generic skeleton.

A familiar pattern is allowed when the Surface Strategy Record explains why it fits. Failure is unexamined reuse, not visual similarity by itself.

## Existing-Surface Rule

For existing products, preserve useful learned behavior and shared system contracts. Diagnose whether the defect is local presentation, component behavior, responsive composition, page hierarchy, or product structure. Trigger structural exploration only for the affected surfaces and axes. Do not redesign unrelated routes or convert a targeted optimization into a new product architecture.
