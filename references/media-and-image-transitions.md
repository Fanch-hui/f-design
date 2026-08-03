# Media And Image Transitions

Use this reference whenever imagery materially defines the composition or an approved target contains a media reveal, crop change, wipe, crossfade, shared-element move, parallax, pinned sequence, or section-to-section image transition.

## Image Integration Contract

Treat the image as a layout participant from the start. Before implementation, record:

| Field | Decision |
|---|---|
| Asset ID and subject identity | The exact person, product, place, object, or scene that must remain consistent |
| Product role | Evidence, orientation, explanation, atmosphere, navigation, comparison, or decoration |
| Prominence | First-viewport priority and intended visual weight |
| Desktop/mobile source | Same asset identity with approved responsive source or crop |
| Geometry | Aspect ratio, focal point, `object-fit`, `object-position`, and crop boundaries |
| Material | Full bleed, unframed, bounded, mask, clip, radius, blend, scrim, texture, or background continuation |
| Layering | Z-order, overlap, negative space, text relationship, and pointer behavior |
| Loading/failure | Intrinsic dimensions, preload priority, decode, placeholder, error, and fallback |
| Accessibility | Informative alt, decorative empty alt, caption, or semantic figure relationship |
| Transition | Evidence, states, trigger, choreography, and reduced-motion result |

An image feels integrated when its crop, edge, negative space, and layer relationship support the page hierarchy. Do not finish a text layout and then drop an image into the nearest rounded rectangle. Do not add a card merely to make the image look contained.

## Match The Reference Material

Inventory what makes the reference treatment work:

- whether the image is full bleed, cropped by the viewport, clipped by a shape, or visually continuous with the page background;
- whether text occupies intentional negative space or overlays with a legibility scrim;
- whether edges are hard, masked, feathered, color-matched, or obscured by another layer;
- whether the subject crosses a grid line, section boundary, or foreground layer;
- whether multiple images share a stack, sequence, collage, or comparison relationship;
- whether the transition is spatial, temporal, or both.

Reproduce these relationships before adding decorative effects. A similar stock image in a generic frame is not a faithful replacement.

## Responsive Art Direction

Use `<picture>`, responsive image APIs, `srcset`, or the framework's image component when mobile needs a different source or crop. Preserve the same subject and content role unless the Page Content Canon explicitly permits substitution.

- Lock focal points per breakpoint instead of relying on a default center crop.
- Keep intrinsic dimensions or `aspect-ratio` to prevent layout shift.
- Let mobile recompose the media around its primary task; supporting imagery must not displace core actions from the first viewport.
- Test extreme aspect ratios, 200% zoom, long text, missing images, slow decode, and orientation changes.
- Never hide essential information in a crop or make hover the only way to reveal it.

## Transition Contract

For every approved media transition, specify:

```text
Reference evidence:
Asset IDs/layers:
Trigger:
State A:
Midpoint/keyframes:
State B:
Direction and distance:
Crop/object-position change:
Mask/clip/opacity/transform properties:
Duration and ease, or scroll start/end and scrub behavior:
Pin/sticky/stacking relationship:
Interruption, reverse, and re-entry behavior:
Desktop/tablet/mobile variants:
Reduced-motion static result:
Loading/failure fallback:
Verification frames:
```

Do not reduce every reference transition to a fade. Distinguish:

- **Crossfade:** stable stacked layers, incoming image decoded first, opacity/`autoAlpha` ownership explicit.
- **Wipe or reveal:** animate a bounded wrapper mask or `clip-path`; preserve the subject crop inside it.
- **Crop shift:** move or scale the image within a fixed overflow frame; avoid layout animation.
- **Shared image transition:** preserve object identity with View Transitions, FLIP, or an equivalent established primitive.
- **Section transition:** define which layer owns the seam, stacking, pin range, and handoff so no blank frame or jump appears.
- **Parallax:** use only when approved and keep distance small enough to preserve the intended crop; remove spatial movement under reduced motion.
- **Pinned or scroll-scrubbed sequence:** define start/end against real layout and test touch scrolling, short viewports, and reverse travel.

## Implementation Order

1. Build and verify State A and State B as stable, accessible, responsive compositions.
2. Reserve media geometry and load the required sources. Decode the incoming image before starting a transition.
3. Use stable layers or explicit shared-element ownership; do not swap an unresolved `src` in the middle of a sequence.
4. Implement the smallest animation primitive that can reproduce the approved behavior.
5. Add responsive and reduced-motion branches.
6. Add cleanup, interruption, and route-change behavior.
7. Verify keyframes and real interaction before polishing timing.

Prefer transforms and opacity. Animate a wrapper's mask or clip when the reference requires a reveal. Avoid animating width, height, top, left, margin, or padding when fixed geometry plus transforms can produce the result.

## Choosing CSS, Native APIs, Or GSAP

- Use CSS for a simple hover, focus, state crossfade, or one-step reveal.
- Reuse the project's capable motion library when it can faithfully implement the contract.
- Use View Transitions for supported route/layout continuity when progressive enhancement is acceptable.
- Use a GSAP timeline for coordinated image layers, masks, labels, reversals, and precise multi-step choreography.
- Use GSAP ScrollTrigger for approved scroll-linked, pinned, or scrubbed transitions; attach it to the top-level tween or timeline.
- Use GSAP Flip for measured before/after layout continuity.

GSAP is not required for every image. If admitted, register plugins once, scope targets, run after mount/client-side, use responsive `matchMedia`, and revert contexts and triggers during teardown.

## Reduced Motion

Provide a coherent composition, not an empty space or a half-initialized sequence.

- Show the correct final or contextually appropriate static image immediately.
- Replace camera travel, parallax, long wipes, and spatial zoom with an instant change or short safe crossfade.
- Preserve copy, focus, reading order, navigation, and status.
- Do not pin a section only to play a sequence that reduced-motion users no longer receive.

## Verification Gate

At every target viewport:

1. Compare State A, at least one midpoint, and State B to approved evidence.
2. Inspect normal speed, slow playback, frame-by-frame, reverse travel, and rapid repeated triggers.
3. Confirm no flash, blank layer, wrong crop, subject jump, layout shift, seam, stacking error, or stale image.
4. Test image decode delay, failed source, route unmount/remount, orientation change, breakpoint crossing, and reduced motion.
5. Inspect touch scrolling, focus, pointer interception, console output, and frame stability on realistic mobile hardware or emulation.

Static screenshots alone cannot prove a transition. Capture keyframes or a short recording and document any accepted deviation.
