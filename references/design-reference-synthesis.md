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
