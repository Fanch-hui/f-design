# Discovery And Architecture

Use this reference during Phases 1 through 3. Convert a vague frontend request into a product brief, technical foundation, page map, and state inventory without turning discovery into ceremony. For material design work, ask before interpreting: repository inspection establishes facts, while the user's answers establish direction.

## Repository-First Scan

Inspect the smallest set of files that can establish the foundation:

- project docs and existing product/design briefs;
- package manifest, lockfile, framework and build config;
- route tree and application entrypoints;
- global CSS, tokens, theme, fonts, icon packages, and shared components;
- data clients, auth, state management, API types, and content sources;
- test, lint, formatting, browser, and deployment configuration;
- existing screenshots, brand assets, photos, illustrations, and generated media.

Write a short foundation record:

```text
Stack:
Rendering/deployment:
Styling and tokens:
Component primitives and icons:
Data/auth/state:
Tests and browser tooling:
Existing visual identity:
Existing reference inputs:
Known constraints:
Unknowns that change the design:
```

Do not replace an established stack because another framework is more familiar. Do not install a second icon family, form library, animation library, or component primitive system until the existing option has been evaluated.

## Evidence Hierarchy

Label material evidence as project truth, current standard/primary specification, official mature system, professional research, or community inspiration. Record confidence as `verified`, `inferred`, or `proposed`. Community popularity can reveal demand or a useful lead, but it cannot establish compliance thresholds or platform behavior. Verify drift-prone standards, package health, and library claims at execution time. Follow `evidence-and-execution.md` for the complete hierarchy and phase ledger.

## Product Taxonomy

Classify the product by the user's job, not by its visual appearance.

### Brand And Communication Surfaces

- **Official or company site:** identity, credibility, product explanation, careers, contact.
- **Campaign or landing page:** one audience, one offer, one conversion path.
- **Portfolio or editorial surface:** work, authorship, narrative, reading, cultural voice.
- **Documentation or content site:** findability, hierarchy, reading, search, SEO.
- **Storefront or product presentation:** inspection, comparison, trust, purchase entry.

Design is part of the delivered value on these surfaces. Imagery, typography, composition, and pacing may be expressive, but the offer and next action still lead.

### Product And Task Surfaces

- **CRUD/workflow tool:** create, organize, edit, approve, and track work.
- **Collaboration product:** shared objects, presence, comments, permissions, history.
- **Content or media product:** browse, consume, create, curate, publish.
- **Commerce/account product:** discover, configure, buy, manage, support.
- **Analytics/monitoring product:** compare, diagnose, alert, decide.
- **Operations/admin product:** high-density repeated work, exceptions, permissions, auditability.
- **Developer or technical tool:** configuration, logs, code/data inspection, automation.
- **Creative tool:** direct manipulation, canvas, timeline, layers, previews, export.
- **Onboarding/form workflow:** collect decisions, reduce uncertainty, reach first value.

Design serves task speed, correctness, confidence, and learnability on these surfaces. Familiarity can be a virtue.

### Hybrid Products

A hybrid has a public brand or acquisition shell plus an authenticated product. Classify each surface separately, then connect them through shared identity, palette roles, type family, icon language, and tone. Do not force marketing pacing inside the app or make the public site look like an admin console.

### Dashboard Test

Use the dashboard label only when the recurring primary job is to monitor, compare, triage, or diagnose several signals at once. A dashboard is not justified by:

- the presence of numbers;
- a signed-in homepage;
- a desire to look professional;
- a convenient grid of cards;
- an app with many features.

If the primary job is to complete one workflow, open that workflow. If it is to browse records, use a strong list/table and details. If it is to create, lead with the creation context. If it is to understand one report, build a report, not a wall of widgets.

## Discovery Gate

Run the repository-first scan, summarize only directly evidenced facts and unresolved choices, then stop. For a material new build, redesign, multi-page addition, or ambiguous image-led request, ask up to four guided direction questions plus one separate open-ended additional-requirements question and wait for the answer before producing a Product Brief, comparing visual directions, generating references, choosing a new architecture, or implementing UI. The first round must include reference intake and architecture selection when either remains unresolved.

The gate is already satisfied only when:

- the user's prompt already supplies equivalent product, visual, palette, imagery, motion, and additional-requirement decisions;
- an established project design system resolves those decisions and the user asked to preserve it;
- the user explicitly delegates the unresolved choices; or
- the task is a focused repair whose visual and behavioral contract is already clear.

Do not interpret silence as approval. If the user delegates, record the selected defaults and the evidence behind them.

## Optional Reference Input Choice

Give the user a visible choice before visual analysis. Reference use is optional and owned by the user. Adapt the labels to the host, but preserve all paths:

1. **Upload a reference:** screenshots, mockups, design files, GIFs, or screen recordings.
2. **Provide a website URL:** one or more public pages to inspect in their current desktop and mobile states.
3. **Use the current or local page:** the existing project, localhost URL, or supplied files become the baseline.
4. **Named inspiration without direct imitation:** products, studios, design systems, or qualities the user wants to borrow.
5. **No reference:** derive a direction from the product brief and project identity; accept this immediately without persuasion or requiring substitute inspiration.
6. **Custom / 自定义:** combine sources or explain another reference workflow.

The question must allow file attachment and free-form URLs. Do not frame an upload or URL as required, recommended by default, or necessary for quality. Do not force users to describe an available website from memory. If an attachment or URL is already present, acknowledge it and ask only what qualities should be matched: information architecture, layout, hierarchy, typography, palette, imagery, interaction, motion, density, or another specific trait.

For a website URL:

- inspect the actual page with the available browser or web tools before claiming visual facts;
- capture or inspect representative desktop and mobile states, key routes, overlays, and motion when accessible;
- record page URL, observation date, accessible states, viewport, relevant qualities, anti-reference details, and confidence;
- distinguish observed behavior from inference when login, geo, paywall, robots, network, or animation timing limits access;
- never request credentials, bypass access controls, scrape private content, or claim inspection when the page was inaccessible;
- imitate the approved design principles and behavior, not trademarks, proprietary copy, unique brand assets, or unlicensed media;
- do not hotlink or copy remote assets unless the user has rights and the implementation has an explicit asset plan.

Create a compact **Reference Intake Record**:

```text
Reference mode and source:
What to emulate:
What to avoid or preserve:
Pages/states/viewports inspected:
Motion/media evidence:
Asset and rights constraints:
Access limitations and confidence:
User selection or delegation:
```

## Architecture Choice Gate

Architecture has two layers. Ask only the unresolved layer, but never collapse them silently:

1. **Experience architecture:** single narrative page, multi-page content/marketing site, task-focused app shell, workspace/editor, commerce flow, or hybrid public site plus signed-in product.
2. **Technical architecture:** existing stack, static/semantic site, client application, server-rendered/full-stack application, content-managed site, or a domain-specific canvas/3D architecture.

For a greenfield build, show two or three viable options with one recommended first. Explain each option's consequences for hosting, SEO, content ownership, authentication/data, interactivity, accessibility, performance, maintenance, and future scope. Add `Custom / 自定义：请填写` and allow `你定 / decide for me` as explicit delegation. Do not scaffold until the user selects, customizes, or delegates.

For an existing project, present the detected architecture and recommend preserving it. Offer an architecture question only when the requested scope creates a real choice:

- keep and extend the current architecture;
- keep the architecture but add a justified compatible capability;
- migrate or replace it, with cost, risk, and affected scope stated;
- custom direction or explicit delegation.

Do not make a small visual repair wait for an irrelevant framework choice. Conversely, do not treat a material migration as implementation detail. Record the user's decision in an **Architecture Decision Record**:

```text
Experience architecture selected:
Technical architecture selected:
Options presented and recommendation:
User selection, custom answer, or delegation:
Why it fits the product and constraints:
Migration/hosting/maintenance consequences:
Rejected alternatives:
```

## Guided Question Cadence

Ask up to four direction questions and one additional-requirements question in the discovery round. Reserve visible questions for reference input and architecture whenever they are unresolved; combine already-known purpose, visual, palette, imagery, and motion details efficiently. Ask a second round only if the answers reveal a new material branch. Keep suggested options short, mutually distinct, and grounded in the product rather than fashion labels.

For every direction question:

- offer two or three plausible suggested options with a one-sentence consequence;
- add a visible final option such as `Custom / 自定义：请填写你的方向`;
- state that the user may combine options or answer entirely in their own words;
- never require an A/B/C-only reply or treat an unlisted preference as invalid;
- when the interface already supplies a visible free-form `Other` field, use it; otherwise write the custom option explicitly.

After the direction questions, always ask a separate open-ended question:

```text
Additional requirements / 额外要求：
还有哪些没有覆盖的要求？可以补充产品名称与文案、必须包含的功能或内容、必须保留或禁止出现的元素、指定素材、技术兼容、时间范围，或任何其他偏好。没有可回答“无”，希望代为决定可回答“你定”。
```

Do not bury this prompt inside another question or replace it with fixed choices. If a structured-question interface limits the number of fields, reserve a field for additional requirements or ask it as a short follow-up before analysis.

Cover questions in this order, skipping only what direct evidence or an explicit user answer already resolves:

1. Who uses this, in what context, and what are they trying to finish?
2. What is the observable success event for the user and the business?
3. Which reference-input path will be used, and exactly what qualities may be imitated or must be avoided?
4. Which experience architecture and, when applicable, technical architecture does the user select after seeing viable tradeoffs?
5. What product class and scope are intended?
6. What real content/data enters the interface, and at what minimum, typical, and maximum ranges?
7. Which roles, permissions, authentication, payments, or high-stakes actions exist?
8. Which platforms, browsers, languages, accessibility level, and performance constraints matter?
9. Which palette strategy fits: neutral-led with one accent, brand-color field, editorial monochrome, or another named approach? Ask about light/dark preference and hue families to favor or reject when unresolved.
10. What should imagery feel like and do: product evidence, photography, illustration, texture/material, 3D, or deliberate restraint?
11. What motion energy is appropriate: nearly static, functional state motion, one signature sequence, or reference-faithful expressive choreography?

In the first round, combine one purpose question with one or two direction questions when the repository already establishes the basics. For example:

```text
1. Reference input / 参考来源？
   A. Upload screenshots, mockups, GIFs, or recordings / 上传文件。
   B. Provide a website URL for desktop/mobile inspection / 提供网站链接。
   C. Use the current or local page as the baseline / 使用当前页面。
   D. No direct reference; derive from the brief / 不使用直接参考。
   E. Custom / 自定义：请填写或组合，并说明想模仿与不想复制的部分。
2. Experience architecture / 产品与页面架构？
   A. One focused narrative or conversion page — smallest scope and clearest path.
   B. Multi-page site — separates content, search, SEO, and navigation responsibilities.
   C. Task-focused app/workspace — prioritizes repeated actions, states, and signed-in navigation.
   D. Hybrid — public brand pages plus a restrained signed-in product.
   E. Custom / 自定义，或回复“你定”授权代理选择。
3. Technical architecture / 技术架构？
   A. Recommended option grounded in hosting, content, data, and maintenance — explain the consequence.
   B. Second viable option — explain its distinct tradeoff.
   C. Third option only when genuinely competitive — explain its distinct tradeoff.
   D. Custom / 自定义，或回复“你定”授权代理选择。
4. Visual, color, imagery, and motion direction / 视觉方向？
   A-C. Offer product-specific, structurally distinct choices with consequences.
   D. Custom / 自定义：请填写，或组合以上方向。
5. Additional requirements / 额外要求：还有哪些名称、文案、功能、内容、素材、必须保留、禁止出现或技术限制需要补充？没有可回答“无”，希望代为决定可回答“你定”。
```

Ask about visual taste after enough purpose and content are known to make the options meaningful. Replace vague adjectives with named anchors or physical-context sentences. "Modern" is not direction; "a quiet clinical workspace used by a support lead under time pressure" is.

If the repository and prompt already answer a direction question, do not ask it again. Still ask for additional requirements unless the user already supplied them, explicitly said there are none, or delegated all remaining decisions. Record custom answers verbatim before interpreting them. If the user delegates decisions, record a reasonable default and proceed.

## Product Brief Contract

For material work, produce this compact brief:

```markdown
## Product Brief

**Product class:**
**Primary audience and context:**
**Primary job:**
**Success event:**
**Success measures:** Effectiveness, efficiency, errors/recovery, and confidence
**Business outcome:**
**Surface register:** Brand / Product / Hybrid, with per-surface overrides
**Core content/data:**
**Scope and fidelity:**
**Platforms and inputs:**
**Reference intake:** Source, inspected states, qualities to emulate, prohibitions, access/rights limits
**Experience architecture:** Selected topology and user decision/delegation
**Technical architecture:** Selected stack and user decision/delegation
**Constraints:**
**References:**
**Anti-references:**
**Custom directions and combinations:**
**Additional requirements:**
**Must preserve / must avoid:**
**Assumptions and unresolved risks:**
```

Create this only after the Discovery Gate. Confirm it before visual exploration unless the user explicitly asks for autonomous execution or the task is a small addition to an established product.

## Technology Decision

### Existing Project

Recommend keeping its framework and pipeline. State the detected architecture and obtain user approval before a material migration. Select additions by compatibility with:

- current rendering model and server/client boundaries;
- current TypeScript and framework versions;
- existing CSS and token strategy;
- deployment platform and browser support;
- accessibility and performance budgets;
- current testing and maintenance practices.

### Greenfield Project

Present viable choices after enough discovery context exists, then let the user select, customize, or explicitly delegate. Use these decision families rather than treating them as automatic answers:

- **Content-led brand/docs site:** favor a server-rendered or static content framework with strong image, metadata, and content support.
- **Interactive application:** favor an app framework that matches hosting, data loading, authentication, and team experience.
- **One-off prototype:** use the lightest environment that still allows accurate interaction and responsive testing.
- **Complex canvas, editor, or 3D product:** choose proven domain libraries for rendering, parsing, physics, or collaboration instead of rebuilding core engines.

State why the recommended choice fits the product and how the alternatives differ. Record the user's selection or delegation before scaffolding. Do not introduce a framework merely to use a preferred component library.

## Flow Mapping

Map the shortest successful path first:

```text
Entry -> orientation -> primary decision/action -> feedback -> completion -> next useful action
```

Then add:

- cancellation and back paths;
- retry and recovery;
- undo for reversible destructive actions;
- permission and authentication interruptions;
- first-run and returning-user paths;
- expert accelerators such as keyboard and batch actions when appropriate;
- interruption and resume, especially on mobile.

Keep the user's context visible. Avoid forcing them to remember data across pages or modal hops.

## Page And State Map

Use one row per route or meaningfully distinct full-screen state:

| Page | Purpose | Entry | Primary action | Key content/data | Shared shell | Desktop composition | Mobile first viewport | Required states | Completion |
|---|---|---|---|---|---|---|---|---|---|

Distinguish:

- **Route:** has a shareable/navigable location or a durable task context.
- **Tab/panel:** switches related views without changing the task object.
- **Dialog/drawer/popover:** handles a bounded decision or supporting action.
- **State:** loading, empty, error, success, permission, or data variation of the same page.

Do not create a route for every modal, or a modal for every secondary task. Exhaust inline and route-based options before defaulting to a dialog.

## State Inventory

For each page and component, decide whether these are relevant:

- default and populated;
- initial loading, background refresh, and optimistic update;
- empty-first-use, empty-by-filter, and empty-after-deletion;
- validation, network, server, rate-limit, and permission error;
- success and next action;
- disabled and read-only;
- offline or stale data;
- minimum, typical, maximum, and overflow content;
- long translation, CJK, RTL, large text, and 200% zoom;
- interrupted flow and restored draft;
- keyboard, touch, pointer, and reduced-motion behavior.

Only include states that can occur, but never design just the perfect populated case.

## Scope Control

Classify features as:

- **Required for primary success**
- **Required for trust/safety/accessibility**
- **Supporting**
- **Deferred**

Defer explicitly. Do not leave fake controls, empty nav links, or placeholder cards to imply future scope.
