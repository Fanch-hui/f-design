# Visual System

Use this reference in Phase 4 and whenever implementation drifts. Build a product-specific design language, not a collection of fashionable effects.

## Start With The Register

### Brand Surface

The interface communicates identity, offer, evidence, or story. It may use stronger imagery, composition, scale contrast, pacing, and a signature visual move. The brand, product, place, or offer must be a first-viewport signal. The next section should remain visibly hinted below the hero on common desktop and mobile viewports.

### Product Surface

The interface serves a repeated task. Prioritize orientation, clear hierarchy, familiar controls, consistent states, and efficient scanning. The surface should disappear into the job. Density is allowed when the task needs it; decoration is not a substitute for structure.

### Hybrid Surface

Switch register by surface, not randomly by section. A public homepage can be expressive while the authenticated app is restrained. Connect them through identity, type family, palette roles, icon language, and voice.

## Project Design Contract

Lock these decisions before generating the full reference set. For material or multi-page work, write them into the project's existing design documentation or a project-specific `DESIGN.md`; do not leave the system only inside a chat message.

```markdown
# Product DESIGN.md

## Product character
- Audience and context:
- Three concrete voice words:
- Physical scene sentence:
- Named references and the exact quality borrowed from each:
- Named anti-references:

## Visual system
- Color role table and salience budget:
- Light/dark theme matrix:
- Semantic feedback, focus, selection, disabled, and component-state mapping:
- Data-color policy:
- Type family and role map:
- Spacing and density:
- Grid and alignment:
- Shape and radius:
- Surface and elevation:
- Icons:
- Imagery/media roles:
- Asset identity, crop, edge, layering, and transition language:
- Signature motif:
- Card policy:
- Motion energy:
- Motion primitives and reduced-motion policy:

## Responsive composition
- Desktop hierarchy:
- Tablet changes:
- Mobile first-viewport rule:
- Mobile navigation/action placement:
- Content removed, deferred, or transformed on mobile:
```

If a repository already has `DESIGN.md`, tokens, or a documented system, treat them as the starting contract. Change them only when the user approved a redesign. For a new direction, use `design-reference-synthesis.md` to extract concrete qualities from selected references without cloning a brand.

## Hierarchy Before Decoration

Establish hierarchy through:

1. position and reading order;
2. spacing and grouping;
3. type size and weight;
4. contrast and color;
5. elevation or motion only when needed.

Use the squint test: the primary element, secondary group, and next action should remain evident without reading details. Do not make every heading, metric, button, and image loud.

## Layout Grammar

- Use full-width page bands or unframed constrained layouts for major sections.
- Use flex for one-dimensional relationships and grid for coordinated rows and columns.
- Create rhythm with tight related groups and larger separations between distinct ideas.
- Keep a stable spacing scale. Do not scatter arbitrary values.
- Use asymmetry only when it clarifies emphasis or brand voice.
- Give fixed-format elements stable dimensions through grid tracks, aspect ratios, min/max constraints, and reserved space.
- Never place a tool or primary experience inside a decorative preview card.
- Never put cards inside cards.

## Card Decision Test

A card is earned when the content is meaningfully independent and at least two of these are true:

- it has its own action, selection, status, or lifecycle;
- it can be moved, reordered, compared, saved, or shared as one object;
- it repeats as a peer in a collection;
- a boundary is necessary to separate it from a different interaction context;
- elevation communicates a real overlay or draggable relationship.

If not, use whitespace, alignment, a divider, a row, a section band, a table, a list, or direct placement.

For dashboard-like products:

- reserve summary tiles for a small number of genuinely top-level signals;
- use tables, charts, lists, timelines, and full-width analysis areas for the rest;
- vary information topology by task instead of wrapping every section in an identical box;
- remove borders and backgrounds that do not communicate grouping or interactivity.

Cards use a radius of 8px or less unless the existing system explicitly defines otherwise.

## Typography

- Use one family for product UI unless a second family solves a real brand need.
- Select brand type from specific voice and references, not a category reflex.
- Use a small role-based scale with clear contrast. Product UI typically needs tighter steps; brand pages can use a larger display jump.
- Keep body copy at a readable equivalent of at least 16px and roughly 45-75 characters per line.
- Use fixed `rem` sizes with explicit breakpoint adjustments. Do not scale font size continuously with viewport width.
- Keep letter spacing at `0`. Do not use negative tracking or tracked all-caps as a shortcut to sophistication.
- Use tabular numbers where numeric alignment matters.
- Load only needed weights and provide metric-compatible fallbacks where practical.
- Never use a display face in dense labels, controls, tables, or body copy.
- Never disable browser zoom.

## Color

Define semantic roles rather than a pile of swatches:

- background and elevated surfaces;
- primary and secondary text;
- borders and dividers;
- primary action and selected state;
- focus;
- success, warning, error, and information;
- data categories only when needed.

Separate primitive palette values, semantic roles, and component-state mappings. Keep brand accent, primary action, focus, selection, information, success, warning, error, and destructive meanings distinct even when some share a hue.

Use `60-30-10` only as a starting heuristic for visual weight: a low-salience base, a supporting field, and a restrained accent. Do not enforce literal pixel percentages or override a valid existing product, editorial, data, photography, or dark-theme system. Diagnose whether too many saturated regions compete and whether the accent remains meaningful.

Product surfaces default to restrained use of accent color. Brand surfaces may commit to a larger color field when it fits the identity. In either case:

- every color has a role;
- color never carries meaning alone;
- text and controls meet WCAG contrast;
- the strongest salience supports the current primary task rather than decorating every section;
- default, hover, pressed, focus-visible, selected, disabled, loading, error, and success states are intentionally related and distinguishable where relevant;
- dark mode is designed, not mechanically inverted;
- the palette does not become a one-note field of purple, beige, dark blue/slate, brown/orange, or any other single hue family;
- avoid generic purple-blue gradients, gradient text, mesh gradients, and stock AI color combinations;
- avoid decorative blobs, orbs, and bokeh fields;
- do not place low-contrast gray text on saturated surfaces.

Use project tokens. If creating new tokens, keep a primitive layer and a semantic layer, then map components and states to semantic roles. Verify light/dark, grayscale, high-contrast, forced-colors, and common color-vision conditions where relevant. Read `color-system-and-states.md` for the complete contract and exit gate.

## Shape, Surface, And Elevation

- Choose one coherent radius language; do not mix sharp, pill, and large rounded shapes without semantic reason.
- Reserve pills for tags, segmented selections, statuses, and compact controls that benefit from the form.
- Use familiar icon buttons for undo, redo, close, save, download, zoom, formatting, and other conventional tool actions.
- Keep shadows subtle and role-based. Product surfaces usually need tonal separation or hairline borders more than floating panels.
- Use blur or translucency only when the material and stacking relationship require it. Keep paint areas bounded and preserve legibility.
- Do not use side accent stripes, stacked decorative bezels, or nested framed surfaces as default styling.

## Icons And Controls

- Reuse the project's existing icon set. Otherwise choose one mature set, preferably Lucide where compatible.
- Do not hand-draw SVG icons when the established library already has the symbol.
- Give unfamiliar icon-only buttons accessible names and tooltips.
- Use the control that matches the decision: icon buttons for tools, swatches for color, segmented controls for modes, toggles or checkboxes for binary settings, sliders/steppers/inputs for numeric values, menus for option sets, and tabs for views.
- Keep all target dimensions stable so hover, focus, loading, labels, and dynamic content do not shift the layout.

## Imagery And Media

Use visual assets when the product, place, person, object, state, or gameplay needs to be seen. Primary media should reveal the actual subject, not function as dark, blurred atmosphere.

Choose the production source explicitly:

- existing project asset;
- verified licensed/open-source asset;
- generated raster;
- semantic SVG/CSS for diagrams and simple marks;
- canvas/WebGL/Three.js for genuinely interactive or 3D content;
- icon library;
- intentional omission.

Do not replace a real screenshot, product view, place, photograph, or object with a fake CSS panel. Do not guess remote image URLs. Preserve intrinsic dimensions or aspect ratio to prevent layout shift. Write useful alt text based on the information the image carries.

Define how media joins the composition: asset identity, focal point, approved desktop/mobile crop, edge or mask, overlap, negative space, background relationship, and transition states. An image is not integrated merely because it shares the page's radius and shadow. Read `media-and-image-transitions.md` when imagery is prominent or animated.

For a hero, use a real or generated bitmap image or an immersive interactive scene when the subject calls for it. Overlay text directly in the composition, not in a split card layout. Ensure the hero leaves a visible hint of the following content.

## Copy And Voice

- Use product-specific nouns and verbs.
- Button labels state the outcome, such as `Create account`, `Save changes`, or `Delete project`.
- Explain what happened, why when known, and how to recover in error messages.
- Keep labels, headings, and terminology consistent.
- Do not blame the user or use humor during errors and high-stakes moments.
- Do not write visible meta-copy that explains the interface's design, feature list, keyboard shortcuts, or how polished it is. The UI should communicate through structure and appropriate contextual help.
- Use real content at review time. Generic startup names, fake metrics, filler testimonials, and decorative status badges invalidate the design review.

## Anti-Template Test

Reject a direction if several of these appear without product-specific reason:

- a centered generic headline above three equal cards;
- a hero made from gradient text, fake metrics, and a floating dashboard preview;
- repeated small uppercase eyebrows above every section;
- identical icon-heading-copy boxes across the page;
- nested rounded containers and excessive pills;
- stock blur, glass, neon, or one-color dark themes;
- alternating zigzag sections with no narrative reason;
- decoration where real imagery or evidence should be;
- every section using the same spacing and topology;
- invented copy that could belong to any product.

Replace the pattern with real content structure, one specific visual idea, and the page's actual primary task.
