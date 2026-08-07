# Design Reference Synthesis

Use this reference in Phase 4 for a material new build, redesign, or multi-page system. Its synthesis method is fully embedded here.

## Authority Order

Apply sources in this order:

1. explicit user requirements and anti-goals;
2. existing project `AGENTS.md`, product requirements, `DESIGN.md`, tokens, components, and brand assets;
3. accessibility, content clarity, mobile context, performance, and maintainability;
4. the approved project direction;
5. user-provided or directly inspected reference artifacts.

Never overwrite a project's identity with a recognizable branded style. Do not copy trademarks, logos, proprietary assets, product copy, or restricted fonts.

## Select References

Use references only from:

1. the current project's approved `DESIGN.md`, tokens, components, assets, and rendered surfaces;
2. files, images, videos, prototypes, or URLs explicitly supplied by the user;
3. directly inspected public product examples or primary platform/design-system documentation when research is necessary and allowed.

Shortlist one to three references that match the product class, audience, task density, emotional register, and media needs. Read the actual permitted artifact completely when possible; do not rely on a filename, screenshot thumbnail, or remembered brand reputation. Select complementary references for exact qualities, not an averaged mood. If no reference exists, proceed from the confirmed Product Brief and F-design visual contract.

## Borrow And Avoid Matrix

Before creating a project design contract, record:

| Source | Product-fit reason | Exact quality to borrow | Concrete rule or token implication | What to avoid | Conflict check |
|---|---|---|---|---|---|

Good borrow statements are specific:

- dense list rows with quiet separators for repeated operational work;
- editorial image crops that preserve a named focal point;
- one strong display/body contrast on public pages;
- a restrained overlay hierarchy with role-based elevation;
- mobile navigation that transforms into a task-first bottom or sheet pattern.

Reject vague statements such as "make it like Apple" or "use Linear style." Reject source rules that violate the current project's constraints, including inaccessible contrast, unsuitable tracking, excessive radius, card walls, motion that delays work, or a mobile layout that only stacks desktop.

## Direction Probe Protocol

Separate structural and visual uncertainty. First complete the Surface Strategy Record. When structural exploration is required, use `surface-strategy-and-structure.md`, present the Structural Direction Matrix, and record the user's selection or delegation before visual-system probes. Do not smuggle a layout decision into a palette or style choice.

When structure is already selected or evidenced but the visual direction remains unclear, present two or three compact visual-system proposals before implementation or any optional reference set. Use written composition plans, token/type/media samples, and structured wireframes. Do not use generated page images to discover the direction. This is progressive disclosure: resolve structure first, then visual direction, then expand only the selected system.

Each proposal or probe must:

- use the same approved product name, copy, content IDs, state, and representative assets;
- preserve the selected structural contract unless the proposal is explicitly part of a still-open structural exploration;
- vary meaningful typography, hierarchy, density, image treatment, material language, and motion intent rather than recoloring one template;
- state outside the image which subject-derived quality, tradeoff, and calibration-dial combination it represents;
- include a restrained fit, a bolder fit, and an evidence-backed wildcard only when all three are plausible;
- remain a real interface proposal, without internal labels such as `Option A`, prompt text, style names, or design commentary rendered inside it.

Ask the user to select, combine, reject, or write a custom direction. If direction is explicitly delegated, record the chosen proposal and rationale. Complete and approve the Design Package before generating any page reference. Do not generate a desktop/mobile page set from several unresolved structures or visual systems.

When revising a generated design, classify the next move:

- **targeted edit:** structure and identity are sound; change named regions, states, assets, or tokens;
- **variant exploration:** the product contract is sound but one or more axes need comparison, such as layout, palette, imagery, type, content density, or motion;
- **full regeneration:** the hierarchy, architecture, or governing visual idea is fundamentally wrong.

Prefer targeted edits over regeneration so approved content, assets, and system decisions do not drift. Every variant must state which axes may change and which remain locked.

## Synthesize The Project DESIGN.md

Write or update a project-specific `DESIGN.md` when the work introduces a new system or materially changes several surfaces. If one already exists, revise the smallest relevant sections instead of replacing it.

Use this structure unless the repository defines another maintained format:

```markdown
# Product Design System

## Overview
## Product Character And Surface Registers
## Colors And Contrast
## Typography
## Layout, Grid, Spacing, And Density
## Shape, Elevation, And Section Grammar
## Components And States
## Imagery And Media
## Motion And Interaction
## Responsive And Mobile Composition
## Do And Do Not
## Known Gaps And Approved Exceptions
```

The contract must contain implementable decisions rather than adjectives:

- primitive-to-semantic token ownership, Color Role Table, Theme Matrix, Component State Matrix, salience budget, data-color policy, and contrast requirements;
- type roles, loading, line length, and fixed responsive steps;
- container, grid, alignment, spacing, density, radius, border, and elevation rules;
- card admission policy and preferred alternatives;
- icon and control conventions;
- asset identity, crop, focal point, edge, layering, and transition language;
- motion purpose, energy, timing family, reduced-motion result, and library policy;
- desktop, tablet, and mobile transformation rules;
- known departures from existing identity and who approved them.

Also identify the master design-system source, permitted page/surface overrides, token-to-component mappings, and the compatibility policy for shared changes. Use `design-system-governance.md` for the maintained contract.

Mark uncertain reconstructed rules as `verified`, `inferred`, or `proposed`. Keep exact volatile values canonical in code token files; in `DESIGN.md`, document semantic roles, invariants, ownership paths, rationale, and durable exceptions rather than duplicating every number.

Keep the document concise enough to guide implementation. Link to existing token or component files instead of duplicating volatile code values.

## Governance Handoff

When the work changes shared tokens, primitives, or patterns across several surfaces, record:

- the owner and canonical design/code source;
- purpose, appropriate and inappropriate use, anatomy, content rules, responsive behavior, complete states, keyboard/touch/screen-reader behavior, token mapping, known limits, and examples for each shared component;
- compatibility impact, migration path, breaking changes, deprecation date, and affected consumers;
- visual regression, interaction, accessibility, and token/contrast checks that protect the rule in CI where the project supports them;
- adoption, repeated defects, delivery friction, and accessibility regressions as health signals rather than component count alone.

Do not promote a one-off page treatment into the design system without repeated intent. Do not change a shared token without identifying representative consumers and verifying them.

## Consistency Handoff

Make the confirmed project `DESIGN.md`, Page Content Canon, and Page and State Map inputs to every reference prompt and implementation pass. A reference image may explore composition inside this contract; it may not silently redefine tokens, content, assets, or product behavior.

When a generated page drifts, fix or regenerate the outlier. Do not update the project system to rationalize accidental generation drift.

## Existing Surface Use

For a tune-up or standards repair, use the existing live product as the primary design evidence. Consult external `DESIGN.md` references only to diagnose a specific gap, such as typography roles, media treatment, density, or responsive transformation. Do not broaden a focused optimization into a brand redesign.
