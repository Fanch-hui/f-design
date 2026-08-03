# Motion And Interaction

Use this reference only after the interface passes the functional and responsive audit. Motion clarifies behavior, preserves continuity, and reproduces approved choreography. It does not rescue weak hierarchy, missing states, generic design, or incorrect static media.

## Motion Coverage Before Choreography

Create a Motion Coverage Matrix for every material build, redesign, broad optimization, or explicit motion request:

| Surface/event | Category | Purpose/reference cue | Implementation or reason | Reduced-motion result | Browser/frame evidence | Status |
|---|---|---|---|---|---|---|

Audit direct-control feedback, state/overlay continuity, async feedback, navigation/layout continuity, media transitions, and brand/narrative motion. Not every category needs animation, but every category needs a recorded decision. A quiet task surface may use restrained state motion. An approved expressive, brand-led, or image-led surface needs its signature or reference-derived sequence; a button press plus one toast fade is not complete coverage.

Use `implemented`, `not applicable`, or `accepted omission` for each row. Do not choose a library until the coverage and purpose are known. See `evidence-and-execution.md` for the full accountability contract.

## Motion Gate

Create a Motion Fidelity Manifest. Inventory every explicit or implied cue in approved video, GIF, prototype, multi-frame reference, user direction, or existing behavior. For each proposed or required animation, record:

```text
Cue ID:
Reference evidence and confidence:
Target and owning component:
Trigger:
User frequency:
Purpose:
State A / midpoint / State B:
Property/material and asset readiness:
Duration/easing or spring:
Scroll start/end, pin, or scrub relationship:
Interruption behavior:
Desktop/tablet/mobile behavior:
Reduced-motion result:
Performance risk:
Why simpler primitives are insufficient:
Selected primitive/library/plugins:
Lifecycle owner and SSR/client boundary:
Verification method:
```

Map each referenced cue to `implemented`, `accepted omission`, or `not temporal evidence`. An approved visual that depends on a media reveal, wipe, crop transition, shared-element movement, pinned section, or scroll-linked sequence makes this phase mandatory. Do not silently label it optional.

Valid purposes:

- immediate feedback;
- state change and system status;
- spatial continuity between trigger and result;
- relationship between old and new layout;
- explanation or guidance;
- perceived progress during real waiting;
- a rare, context-appropriate moment of delight.

Remove invented motion whose only explanation is "polish," "premium," or "looks dynamic." Preserve reference-derived motion when it has been approved, unless accessibility, performance, or platform constraints require a documented alternative.

## Frequency Budget

Frequency determines restraint:

- **Continuous or keyboard-repeat actions:** no animation or near-instant feedback.
- **Many times per session:** short state feedback with minimal distance.
- **A few times per session:** transitions may clarify hierarchy or space.
- **First run or major milestone:** one richer moment may be justified.
- **Ambient/infinite:** reject by default; allow only when it conveys ongoing status or is central to an expressive brand experience, and pause it offscreen.

Power users should never wait for choreography.

## Product Versus Brand

### Product Motion

- State-led, fast, and consistent.
- No orchestrated page-load sequence for routine app routes.
- Prioritize press feedback, loading/progress, overlays, selection, reordering, undo, and view continuity.
- Keep standard behavior familiar. Do not invent a new affordance merely to animate it.

### Brand Motion

- One signature entrance or narrative transition can carry voice.
- Prefer a composed sequence over scroll-triggering every section.
- Motion may use masks, media, type, depth, or 3D when the subject earns it.
- Keep navigation, CTA, and content accessible before and during the sequence.

## Narrative Choreography For Web Pages

Presentation-style choreography can improve ordinary webpages when it is translated into web-native behavior rather than copied as a slide deck.

Create a short beat map for each expressive page:

| Beat | Content purpose | Visual focus | Entrance/transition | User control | Mobile/reduced result |
|---|---|---|---|---|---|

Transfer these principles:

- orchestrate one high-impact entrance or section sequence around the intended reading order;
- reveal text, media, and supporting evidence as coordinated beats instead of unrelated fades;
- use stagger only when it clarifies sequence or grouping, and cap it so visible content does not wait;
- match motion character to product tone: cinematic can use slower scale, mask, depth, or parallax; playful can use a restrained spring; professional should remain subtle and fast; calm should move gently; editorial pages can coordinate type and imagery;
- alternate high- and low-density moments so users can scan, read, and recover attention;
- restructure, split, or progressively disclose overflowing content instead of shrinking type or allowing overlap;
- preserve a meaningful static first frame and final composition so content is never trapped behind a failed trigger.

Do not transfer these presentation constraints into ordinary webpages:

- a fixed `16:9` stage or page-wide no-reflow layout;
- forced slide navigation, scroll hijacking, or mandatory snapping;
- making every section exactly one viewport tall;
- disabling normal document semantics, deep links, browser history, text selection, or accessibility navigation;
- desktop choreography reused unchanged on phone.

Normal responsive reflow, content-driven height, semantic reading order, user-controlled scrolling, and mobile task priority remain authoritative. On small screens, simplify or remove decorative movement before reducing legibility or interaction space.

## Timing Budget

Use duration as a function of distance and consequence:

| Interaction | Typical duration |
|---|---:|
| Press/tap feedback | 100-160ms |
| Tooltip/popover | 125-200ms |
| Dropdown/select | 150-250ms |
| Tab/selection indicator | 150-250ms |
| Modal/drawer | 200-400ms |
| Larger layout transition | 250-500ms |
| Brand entrance | 400-800ms only when it earns the wait |

Exit is usually shorter than entrance. Do not use feedback animations longer than 500ms.

Use a strong ease-out for entrances and exits, ease-in-out for movement between known positions, and linear motion only for constant progress. Avoid bounce and elastic easing. Springs are appropriate for direct manipulation when their response is interruptible and tuned to the gesture, not for every hover.

## Spatial Rules

- A popover, menu, or sheet should appear to originate from its trigger or edge.
- A centered modal should preserve visual center and focus hierarchy.
- Shared objects may morph between list/detail states when identity continuity helps.
- New elements enter with small, believable distance. Do not enter from `scale(0)`.
- Press feedback is subtle, commonly around `scale(0.97)` or a small depth/color change.
- Avoid routine hover scale above roughly `1.02`; large growth shifts layout perception and feels unstable.
- Cap list stagger so the last visible item does not wait noticeably. Do not stagger long datasets.

## Property Choice

Prefer:

- transform and opacity for movement and reveal;
- clip/mask for a justified brand or media reveal;
- bounded blur/filter/shadow/color shifts for small atmospheric effects;
- FLIP, View Transitions, or grid-based techniques for layout continuity;
- Web Animations API or the existing motion library for cancellation and sequencing.

Avoid:

- `transition: all`;
- casual animation of width, height, top, left, margins, or large layout regions;
- unbounded backdrop blur, filters, or giant shadows;
- scroll event loops when Intersection Observer or scroll-linked CSS fits;
- preemptive `will-change` across many elements;
- expensive effects continuing offscreen;
- motion that blocks input until completion.

Measure on target devices. Transform/opacity are good defaults, not permission to animate everything.

## Library Choice

Use this order:

1. Existing project motion primitives and tokens when they can reproduce the contract.
2. CSS transitions/keyframes for simple state changes.
3. Web Animations or View Transitions for cancellable/shared transitions.
4. The project's installed capable motion library.
5. GSAP or another mature library only for real runtime sequencing, precise scroll synchronization, FLIP continuity, gesture/inertia, high-frequency smoothing, or specialized SVG/text behavior.

Do not force GSAP, Motion, or any specific library onto every project. Evaluate current GitHub health, compatibility, bundle cost, accessibility, and project fit under the open-source selection policy.

## GSAP Implementation Contract

When GSAP is admitted:

- use a core tween for one transition and a timeline with labels/position parameters for coordinated steps; do not chain manual delays;
- register each plugin once before first use and include only the features required by the manifest;
- use Flip for measured before/after layout continuity and ScrollTrigger only for genuine scroll-linked, pinned, or scrubbed behavior;
- attach ScrollTrigger to the top-level tween or timeline, never to child tweens; choose `scrub` or `toggleActions`, not both;
- animate children of pinned elements, create triggers in page order, remove development markers, and refresh only after real image/font/content layout changes;
- use `gsap.matchMedia()` for breakpoint and `prefers-reduced-motion` branches, then revert it on teardown;
- scope selectors to the owning component and run after mount/client-side; do not execute GSAP during SSR;
- in React, prefer `useGSAP` with a scope, `contextSafe` for later callbacks, and `revertOnUpdate` when dependencies rebuild the sequence;
- in other frameworks, create inside mounted lifecycle, wrap in `gsap.context()`, and revert on destroy;
- kill or revert unmanaged tweens, timelines, ScrollTriggers, SplitText instances, listeners, and callbacks on route change or unmount;
- preload/decode required incoming media, reserve geometry, and keep stable layers so a transition never flashes blank content;
- favor transforms, opacity/`autoAlpha`, and bounded masks. Batch DOM reads before writes, limit `will-change` to active targets, use `quickTo` for frequent pointer updates, and never create hundreds of overlapping tweens without device testing;
- measure uncommon plugin and runtime bundle cost; never ship markers, GSDevTools, or development helpers.

GSAP capability does not authorize elastic/bounce motion, text scrambling, mouse followers, smooth-scroll replacement, horizontal scroll, pinning, or parallax. These require explicit product and reference justification.

For image choreography, also follow `media-and-image-transitions.md`.

## Interaction Feedback

### Buttons And Commands

- Acknowledge press immediately.
- Preserve label and dimensions while loading.
- Disable duplicate submission without removing focus unexpectedly.
- Announce completion or error when visual feedback alone is insufficient.
- Do not celebrate routine saves with a long sequence.

### Forms

- Transition focus and validation states without shaking the entire field or page.
- Keep errors stable and readable.
- Use optimistic success only for low-risk reversible actions.
- Preserve cursor and focus during async updates.

### Overlays

- Animate surface and backdrop as one relationship.
- Focus is correct before the user can interact.
- Close on Escape/light dismiss when appropriate.
- Restore focus to the trigger.
- Allow rapid close/reopen without stale animation state.

### Drag And Gestures

- Direct manipulation follows the pointer/finger without lag.
- Motion can be interrupted at any frame.
- Release uses velocity and distance to settle.
- Drop targets and invalid states are visible.
- Reordering preserves spatial continuity.
- A keyboard-accessible alternative exists.

### Loading And Progress

- Use a skeleton when content structure is known.
- Use determinate progress when actual progress is measurable.
- Use a concise status message for longer waits.
- Avoid artificial delays intended to make work feel valuable.
- Never let loading motion replace recovery or cancel behavior.

## Delight Gate

Delight is allowed at a completion, first value, milestone, discovery, or brand-defining moment when:

- the moment is infrequent;
- the tone fits the domain and user's emotional state;
- it starts after success rather than delaying it;
- it remains understandable without motion or sound;
- it stays pleasant after repeated use;
- it has a small performance footprint.

Do not use playful error copy, confetti for routine actions, random variation in operational UI, custom cursors, particles, sound, or seasonal effects by default. Sound requires explicit user initiation and a mute path.

## Reduced Motion

Design a deliberate reduced-motion variant:

- remove large translation, parallax, camera movement, looping, and spatial zoom;
- replace with instant state change or a short opacity/color transition when safe;
- preserve focus, status, reading order, and completion feedback;
- do not simply set every duration to an imperceptible nonzero value if that causes broken sequencing;
- test with the operating system preference enabled.

Reduced motion is a first-class experience, not an emergency override.

## Verification

For every significant sequence:

1. Interact at normal speed.
2. Inspect at slowed playback or frame-by-frame.
3. Trigger repeatedly and interrupt midway.
4. Test keyboard and touch.
5. Test reduced motion.
6. Monitor frame time and main-thread work on a realistic mobile device.
7. Check that layout, focus, and hit targets remain stable.
8. Confirm the animation still serves its recorded purpose.
9. Compare captured State A, at least one midpoint, and State B against the approved evidence.
10. Test image decode delay, blank-frame risk, breakpoint crossing, route unmount/remount, and duplicate trigger creation.
11. Check the production bundle for debug tools, markers, accidental duplicate runtimes, and unexpected plugin cost.

Reject motion when it produces frame drops, delays task completion, loses state, creates overlap, or draws more attention than the user's goal.

## Phase Exit

Motion delivery is complete only when:

- every Motion Coverage Matrix category has a reasoned status and reduced-motion result;
- every approved/reference cue has a Motion Fidelity Manifest item;
- applicable rows are implemented, or the omission is explicitly accepted with risk recorded;
- significant sequences have start, midpoint, and end evidence plus interruption and repeat testing;
- desktop and mobile preserve the same content and asset identity while using suitable choreography;
- lifecycle cleanup, frame stability, focus, touch, keyboard, and reduced motion are verified;
- the final report names what was implemented and does not reduce the phase to a generic claim that motion was unnecessary.
