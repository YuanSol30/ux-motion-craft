---
name: ux-motion-craft
description: Design, refine, or review product interfaces using 20 UX and animation principles and 20 concrete fixes for generic AI design. Use for interface polish, purposeful motion, visual hierarchy, usability reviews, and removing unnecessary decoration.
---

# UX Motion Craft

Turn the user's 40 design principles into deliberate interface decisions. Improve task clarity, ease of use, and feedback while preserving the product's identity and existing design system. Apply the principles that fit the task; do not force every principle into every screen.

## Working approach

1. Identify the user's main task, audience, platform, primary action, and existing component conventions. Inspect the actual interface or source before proposing specific fixes. If only a screenshot is available, distinguish visible findings from interaction assumptions.
2. For visual refinement, use the 20 design cleanup principles below. For interaction, animation, or usability work, use the 20 UX and animation principles below. For a complete new screen or broad review, use both.
3. Prioritize broken or inaccessible interactions, then hierarchy and content, then decorative polish. Keep useful labels, status information, and established navigation even when simplifying.
4. For implementation requests, make the changes and verify relevant states. For review requests, report findings with concrete evidence and proposed fixes; a review does not authorize editing the product.
5. Validate the main task on relevant viewport sizes, with keyboard input, reduced motion, loading, success, error, and interruption states as applicable. Report what was actually checked and any unresolved limitations.

## Decision rules

- Treat the laws as decision aids, not universal formulas. Miller's law is not a seven-item menu limit; the Doherty threshold is not a license to delay feedback. Validate assumptions in the product's context.
- Let motion explain state, spatial relationships, progress, or feedback. A subtle interface can satisfy the animation principles without visible bouncing or a 3D scene.
- Preserve readable text, focus indicators, accessible names, and meaningful status. Removing a redundant visual label must not remove information required by assistive technology.
- Respect reduced-motion preferences. Use immediate state changes or restrained fades when spatial movement is unnecessary. Never make correctness depend on animation completion.
- Use the existing stack and design tokens. Introduce a dependency only when the task needs it and the project's conventions support it.
- Do not manufacture product screenshots, testimonials, performance numbers, or claims to make a design appear more credible.

## Useful output

For a review, give the most consequential findings first. Identify the affected element, the observed issue, the relevant principle, and the concrete correction. Mark unverified interactions as needing inspection. Avoid a numeric quality score without a defined rubric.

For implemented changes, describe the resulting behavior, summarize meaningful verification, and state any remaining limitations. Mention only the principles that actually shaped the work; do not recite all 40 points.

# 20 Principles of UX & Animation

Use principles 1-12 to improve motion and composition; use 13-20 to improve interaction. Preserve the user's numbering so findings can reference individual principles.

| # | Principle | Practical application | Boundary or verification |
|---|---|---|---|
| 1 | Squash & stretch | Use a restrained compression or expansion to communicate a press, elastic object, or successful completion when appropriate to the product. | Keep text and icons readable; do not distort hit areas or cause layout shifts. Omit elastic motion in restrained products. |
| 2 | Anticipation wind-up | Signal an upcoming consequential action with a preview, pressed state, drag affordance, or clear preparation. | Do not add a theatrical delay before routine actions. Consequential actions may need explicit confirmation rather than animation. |
| 3 | Staging the focus | Give the current task and its main action clear visual priority. Use dimming, spacing, and motion to direct attention. | Competing animations must not fight for focus. Maintain contrast and visible keyboard focus. |
| 4 | Pose to pose | Define initial, active, completed, cancelled, and failed states before interpolating between them. | Each final state must render correctly with animation disabled, skipped, or interrupted. |
| 5 | Follow through | Let a secondary visual settle briefly after a movement when this helps communicate material or continuity. | Do not delay input, navigation, or the final semantic state until a spring settles. |
| 6 | Slow in & slow out | Match acceleration and deceleration to entering, leaving, and changing state. Use shared easing tokens. | Constant progress may need linear motion. Avoid treating one easing curve as appropriate everywhere. |
| 7 | Moving in arcs | Use curved paths for expressive objects or gestures where the path clarifies their destination. | Direct movement is often clearer for menus, forms, and data. Avoid unnecessary spatial travel and respect reduced motion. |
| 8 | Secondary action | Support the primary action with a related cue, such as a count update after adding an item. | Do not steal attention or rely on motion alone to convey the result. |
| 9 | Snappy timing | Show immediate acknowledgment and use the shortest transition that communicates the change clearly. | Judge timing against travel distance, input speed, and context. Test rapid repeated input; never add delay to appear polished. |
| 10 | Exaggerated feedback | Increase the clarity of important feedback through hierarchy, wording, contrast, or restrained motion. | Scale emphasis to consequence. Routine success should not resemble an emergency; do not flash or shake aggressively. |
| 11 | Solid drawing in 3D | When using 3D, maintain coherent perspective, depth, lighting, occlusion, and believable volume. In 2D, maintain coherent layering and object boundaries. | Do not introduce 3D just to satisfy this principle. Check clipping, shadows, and transformed text. |
| 12 | Overall appeal | Build a coherent visual personality through proportion, typography, color, composition, and consistent behavior. | Appeal serves the product and audience; novelty and decoration are not evidence of usability. |
| 13 | Fitts's law | Make important targets easy to reach by considering their size and distance from the likely pointer or thumb position. | Do not reduce this to bigger buttons everywhere. Check placement, adjacent targets, and the actual task path. |
| 14 | Bigger hit areas | Expand the interactive region around small visible controls and make the complete intended row or label clickable. | Keep targets from overlapping. Use platform guidance and verify pointer, touch, and keyboard activation. |
| 15 | Hick's law | Reduce decision complexity with clear labels, meaningful groups, useful defaults, and progressive disclosure. | Do not hide essential choices or add extra steps solely to reduce visible item count. Search and expertise change the tradeoff. |
| 16 | Miller's law | Group related information, externalize state, and favor recognition over remembering details across steps. | Do not enforce seven plus or minus two items as a universal navigation rule. Chunk by meaning and test comprehension. |
| 17 | Doherty threshold | Keep acknowledgment fast enough to maintain a sense of direct interaction; provide meaningful progress for longer work. | Roughly 400 ms is a historical heuristic, not a universal pass/fail standard. Show input feedback immediately and measure actual latency. |
| 18 | Postel's law | Accept harmless formatting variations, normalize predictable input, and show specific recovery guidance. | Do not silently guess ambiguous dates, money, identities, or destructive intent. Validate strictly at trust boundaries and preserve user meaning. |
| 19 | Jakob's law | Use familiar controls, labels, navigation, and interaction patterns so existing knowledge transfers. | Adapt conventions to the platform and audience. Do not copy an unsuitable pattern or brand blindly. |
| 20 | Frequency of use | Give frequent tasks convenient placement and efficient paths; keep rare actions discoverable without crowding primary work. | Frequency is not importance. Rare critical or emergency actions may need prominent access, and destructive actions need safeguards. |

## Motion implementation checks

- Define animation intent in a sentence: what relationship or state becomes easier to understand?
- Prefer transforms and opacity when practical, and inspect actual rendering performance. Do not apply blanket transitions to every property.
- Keep visual feedback independent of network completion. Do not show success before the operation succeeds.
- Keep semantic state, focus, and accessible status synchronized with the operation. Avoid repeated live-region announcements during animation frames.
- Cancel or replace previous transitions on rapid input. Set the new target state explicitly; handle unmounts and navigation without orphaned timers or event handlers.
- Test reduced motion, repeated toggling, interrupted loading, and failed operations. A static screenshot cannot verify these behaviors.

# 20 Ways to Unslop AI Designs

Remove generic decoration and strengthen the actual product. Preserve useful information, accessibility, and the user's intended style. These are editorial criteria, not a requirement to make every product minimal.

| # | Principle | Apply it | Preserve or verify |
|---|---|---|---|
| 1 | Delete filler badges | Remove chips such as generic AI-powered or next-generation labels when they add no decision value. | Keep real status, availability, compliance information, or other badges that users need. |
| 2 | Drop redundant labels | Remove visible labels that repeat nearby context without improving comprehension. | Keep input labels, accessible names, units, and context needed after scrolling or on small screens. |
| 3 | Unitalicize random words | Use emphasis only when it communicates a deliberate hierarchy or editorial meaning. | Preserve intentional brand typography and meaningful italics. |
| 4 | Mono only where needed | Reserve monospace for code, identifiers, or data where fixed-width alignment helps. | Ordinary body text and navigation should use the product's readable text styles. Numbers can use tabular figures without monospace. |
| 5 | Use a design system | Reuse tokens and components for color, spacing, type, radii, elevation, and interaction states. | Extend the established system rather than creating an unrelated parallel theme. |
| 6 | Show the actual product | Give the real interface, service, result, or artifact a concrete place in the composition. | Use verified assets or clearly marked mockups. Do not invent screenshots, customer logos, or product capabilities. |
| 7 | Enlarge the main feature | Give the central task, useful preview, or defining product feature enough space to be understood. | Do not enlarge decoration or push the primary action out of reach. Check small viewports. |
| 8 | Group with spacing | Use proximity and whitespace to express relationships before adding borders or cards. | Keep related labels and controls together and maintain a sensible reading order. |
| 9 | Make headlines specific | Say what the product does, for whom, or what result it enables in concrete language. | Do not add unsupported claims or numbers. Keep essential meaning visible when headings wrap. |
| 10 | Emphasize the CTA | Make the primary next action visually clear and label it with a concrete verb and object. | Secondary actions remain discoverable. Repeated primary actions can be useful in long pages; avoid competing primary actions within one decision area. |
| 11 | Add an accent colour | Use a deliberate accent to establish identity and highlight key actions or selection. | Reuse the existing brand palette when present. Do not use accent color everywhere or make color the only signal. |
| 12 | Keep icons consistent | Use a coherent icon family, optical size, stroke, and placement. | Give icon-only buttons accessible names and tooltips where helpful. Do not replace clear labels with unexplained symbols. |
| 13 | Remove embellishments | Remove arbitrary gradients, blobs, sparkles, grids, or shadows that obscure hierarchy or slow rendering. | Keep decoration that deliberately serves the brand, story, or comprehension. |
| 14 | Inner radius = outer - padding | For uniformly inset rounded rectangles, start with inner radius = max(0, outer radius - inset). | Use the actual gap between boundaries, including borders as appropriate. This is a geometric starting point; optical adjustments and irregular shapes need judgment. |
| 15 | Improve text contrast | Check actual foreground/background pairs, including muted text, placeholders, disabled explanations, and overlays. | Use the applicable accessibility standard; for typical web AA, normal text needs 4.5:1 and large text 3:1. Verify rather than judging from hex values in isolation. |
| 16 | Wrap headlines properly | Let headings wrap naturally at useful widths; use balanced wrapping as a progressive enhancement when suitable. | Test narrow screens, localization, zoom, and long words. Avoid forced line breaks or nonbreaking spaces that only work at one width. |
| 17 | Align by eye, not pixels | Refine icon centering, text baselines, and perceived visual weight after structural alignment is correct. | Use systematic layout first. Optical corrections should be small and purposeful, not arbitrary offsets for every element. |
| 18 | Use tabular nums | Apply tabular figures to changing counters, prices in comparison columns, timers, and aligned numeric data. | Keep locale-aware formatting, units, and readable precision. Ordinary prose does not require tabular figures. |
| 19 | Add loading states | Show acknowledgment and appropriate progress while real work happens; reserve layout space and provide recovery on failure. | Do not show fake progress or add artificial wait time. Prevent accidental duplicate submissions and maintain accessible status. |
| 20 | Animate useful feedback | Animate changes that clarify cause and effect, such as selection, expansion, completion, or repositioning. | Respect reduced motion, preserve focus, and support interruption. Avoid autoplay motion that competes with the task. |

## Review method

Inspect the main task first, then ask:

- Can a new user identify what the product does and its next useful action?
- Is the actual product prominent enough to understand?
- Does each badge, icon, label, card, and effect earn its space?
- Do spacing, type, and color communicate a coherent hierarchy?
- Are key controls usable with touch, keyboard, zoom, and assistive technology?
- Do loading, error, empty, success, and reduced-motion states remain clear?

Choose changes based on user impact, not the number of checklist items satisfied. For example, removing a billing-status badge to reduce clutter is a regression when that badge prevents a mistaken payment.


