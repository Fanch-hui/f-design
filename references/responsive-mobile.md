# Responsive And Mobile Review

Use this reference while composing mobile in Phase 6 and during Phases 7 and 9. A responsive page is not finished when it merely avoids a CSS breakpoint error. It must become a clear, efficient experience in each context.

## Mobile Recomposition Rule

For every page, write a mobile decision record:

```text
Primary phone task:
Page Content Canon version:
Required content, asset, navigation, and action IDs preserved from desktop:
First-viewport content in order:
Primary action location:
Navigation transformation:
Content reordered:
Content condensed:
Content progressively disclosed:
Content omitted and why it is nonessential:
Approved responsive image crop/art direction:
Sidebar/table/chart/toolbar transformation:
Keyboard and safe-area behavior:
Interruption/resume behavior:
```

If this record only says "stack columns" or "reduce sizes," the mobile design is incomplete. If it invents a different user state, copy, image subject, navigation meaning, or action outcome, it is a different product rather than a responsive composition.

## First-Viewport Test

At each phone width, capture the page at initial load with no scroll. Ask:

1. What is the page for?
2. Can the user recognize that purpose within five seconds?
3. Is the first meaningful action visible or immediately reachable?
4. Does decorative media, navigation, a logo, an announcement, or whitespace consume more space than the task?
5. Is the next step explicit?

Treat a wrong first viewport as a blocking defect.

### Authentication Example

On sign-in or registration pages, the first viewport should prioritize:

- product identity at an appropriate scale;
- sign-in/register heading and account context;
- primary provider option or first fields;
- password recovery or account-switching when relevant;
- primary submit action or a clear continuation cue.

Supporting illustration or brand media must not push the form below the first viewport. When the keyboard opens, the active field, error, and submit path must remain usable. Do not show a large hero before the account task.

## Viewport Matrix

Test at least:

| Context | Width or device | What it exposes |
|---|---:|---|
| Small phone | 320 | longest-word overflow, cramped controls |
| Common phone | 375 | baseline iPhone composition |
| Common phone | 390 | modern phone baseline |
| Large phone | 430 | wasted space and over-wide text |
| Tablet portrait | around 768 | ambiguous one/two-column behavior |
| Tablet landscape | around 1024 | sidebar and hybrid input behavior |
| Desktop | 1280 | normal workstation layout |
| Wide desktop | 1440+ | max-width, excessive stretching, next-section signal |

Use exact project-supported viewports when known. Add landscape phone, foldable, kiosk, or ultrawide checks when the product context requires them.

## Layout And Overflow

Check every viewport for:

- `scrollWidth` greater than viewport width;
- fixed widths, min-content tracks, long words, code, chips, tables, and images causing overflow;
- flex/grid children missing `min-width: 0`;
- absolute/fixed elements escaping containers;
- negative positioning or transforms hiding controls;
- text clipped by fixed heights;
- toolbars wrapping into unusable shapes;
- dynamic content resizing boards, tiles, counters, or controls;
- bottom bars covering the last content or action;
- sticky headers consuming excessive vertical space.

Do not solve overflow by globally hiding it. Find and fix the owner.

## Content Priority

Mobile has less simultaneous space, not less-important users. Preserve core functionality while changing presentation:

- put the primary task before supporting explanation;
- move secondary context behind a well-labeled disclosure, sheet, tab, or details region;
- keep required decision information visible at the moment of action;
- shorten copy without removing necessary consequences or recovery guidance;
- avoid asking users to remember data from a closed panel or previous screen;
- preserve state when users switch apps, rotate, navigate back, or get interrupted.

Do not hide core actions solely because they are difficult to fit.

## Navigation

Choose by product structure and frequency:

- compact top navigation for small public sites;
- bottom navigation for a small set of frequent app destinations when it fits the platform;
- drawer or sheet for larger hierarchies;
- drill-down navigation for deep structures;
- persistent desktop side navigation transformed into a clear mobile entry point;
- breadcrumbs or visible back context for nested content.

Avoid a hamburger menu by reflex. Avoid showing desktop sidebar labels in a horizontal scroll strip unless that is genuinely the clearest model. Keep the active location visible.

## Primary Actions And Thumb Reach

- Place frequent phone actions in reachable regions when this does not conflict with reading or platform convention.
- Use sticky bottom actions only when they remain relevant while scrolling.
- Reserve bottom safe-area space and page padding equal to the sticky control's occupied height.
- Keep destructive and secondary actions visually distinct from the primary action.
- Avoid two fixed layers competing at top or bottom.
- Ensure action labels fit at 320px and with translation expansion.

## Touch And Input Method

- Touch targets should be at least 44 by 44 CSS pixels, including expanded invisible hit areas where appropriate.
- Keep adjacent targets sufficiently separated.
- Provide visible pressed feedback.
- Do not require hover for meaning or action.
- Use `pointer` and `hover` media features instead of assuming width equals input method.
- Preserve keyboard shortcuts and pointer density on tablets/laptops that support both touch and keyboard.
- Every gesture has a visible alternative and discoverable affordance.

## Soft Keyboard And Forms

Test with the virtual keyboard open:

- focused field is not covered;
- error text and next/submit action remain reachable;
- sticky footers do not stack above the keyboard incorrectly;
- viewport resize or visual viewport changes do not break fixed elements;
- form state and scroll position remain stable;
- input `type`, `inputmode`, `autocomplete`, and enter-key hints match the data;
- one-time codes support paste and platform autofill;
- password-manager overlays do not collide with custom controls.

Avoid unnecessary autofocus on mobile. It can open the keyboard before the user understands the page.

## Safe Areas And Browser Chrome

- Use `viewport-fit=cover` only with correct safe-area padding.
- Apply `env(safe-area-inset-*)` to fixed/sticky surfaces that touch device edges.
- Do not double-apply safe areas to body and nested bars.
- Test dynamic browser bars and standalone/PWA display when applicable.
- Verify notches, rounded corners, and home indicators do not cover controls.

## Tables And Dense Data

Do not automatically convert every row into a card. Choose by the user's comparison task:

- keep a table with local horizontal scroll, sticky key columns, or column prioritization when cross-row comparison matters;
- use a compact row list when only a few fields are needed at a glance;
- use list-to-detail navigation for complex records;
- use cards only when each record is an independent object with its own actions/status and the card decision test passes;
- provide sorting/filtering in a sheet or compact toolbar without hiding active filter state;
- keep bulk selection and batch actions usable where they are core.

Never force a dense desktop table into unreadably small text.

## Charts And Visualizations

- Decide whether mobile needs overview, exact values, comparison, or drill-down.
- Reduce simultaneous series and labels only when the user can still answer the core question.
- Provide accessible summaries and data tables where needed.
- Use responsive aspect ratios and stable plot dimensions.
- Make tooltips available through tap/focus, not hover only.
- Avoid turning every chart into a tiny card.

## Overlays, Sheets, And Modals

- Use full-height or bottom sheets for appropriate phone tasks, but preserve a clear close/back path.
- Keep the title and primary action visible when content scrolls.
- Prevent background scroll and restore it correctly.
- Trap and restore focus for modal contexts.
- Ensure the sheet remains above the keyboard without covering active content.
- Avoid dialogs inside dialogs and sheets inside nested cards.

## Typography And Content Fit

- Body text remains readable and respects user text settings.
- Use stable `rem` sizes with explicit breakpoint adjustments, not viewport-proportional type.
- Keep letter spacing at `0`.
- Let long labels wrap rather than shrink below legibility.
- Use dynamic sizing only when a fixed-format display has a truly unavoidable longest word, and keep it bounded.
- Test translation expansion, CJK, emoji, unbroken identifiers, and 200% zoom.
- Ensure text never occludes preceding or following content.

## Performance On Mobile

- Test on a mid-range device or realistic CPU/network throttling.
- Deliver appropriately sized responsive images.
- Lazy-load below-fold media and heavy modules.
- Avoid running animation or canvas work offscreen.
- Keep input response fast and break up long main-thread work.
- Measure layout shift, LCP, INP, memory, and frame stability where relevant.

## Browser Evidence

For each critical page:

1. Capture the initial viewport at 320, 390, and 430.
2. Capture a scrolled state with sticky/fixed controls.
3. Open navigation, overlays, filters, and long-content states.
4. Focus a lower form field with keyboard simulation or a real device.
5. Run a horizontal-overflow check.
6. Compare with the page's approved mobile reference.
7. Compare its content IDs, copy, data/state, asset identity, navigation, and actions against the desktop reference and Page Content Canon.
8. Inspect the screenshot visually; creating it is not enough.

Use DOM checks to support the visual review:

```javascript
document.documentElement.scrollWidth <= window.innerWidth
```

Also inspect bounding boxes for fixed/sticky elements and the primary action. Automated geometry cannot tell whether the wrong content dominates the first viewport, so always read the screenshot.

## Mobile Exit Gate

Mobile passes only when:

- the first viewport clearly serves the page's primary task;
- no core content or action is hidden by decoration, chrome, safe areas, keyboard, or sticky UI;
- no horizontal overflow or clipped text remains;
- navigation and overlays have clear entry/exit behavior;
- touch targets, labels, and focus are usable;
- tables, charts, filters, and toolbars use context-appropriate mobile patterns;
- interruption and resume do not lose critical progress;
- core content, user/data state, asset subjects, navigation meaning, and action outcomes remain consistent with desktop;
- the page matches the approved mobile reference or documents an accepted improvement.
