# Prompt compiler

Write the final image prompt in four short paragraphs, in this order. Use visible nouns and measurable relationships instead of vague style adjectives.

## Paragraph 1 — subject and emotional beat

Name the dog count, breed/type only when visually supported or user-supplied, pose, gaze, gesture, setting cue, emotional temperature, and abstraction level. For a photo transform, label the content image and state the compact identity lock from `photo-transform.md` before any stylistic instructions.

## Paragraph 2 — composition

Name the 3:5 paper canvas, composition recipe, subject location, approximate canvas share, negative-space range, visual hierarchy, crop behavior, and any allowed title or microtype. State the paper contrast lock: dominant coat family, selected paper hue/value, and the intended silhouette separation. For a photo transform, state the environment lock: one primary cue, up to two micro-accents, abstract treatment, placement, and coverage cap. Describe what may change from a source photo.

## Paragraph 3 — print construction and color

Specify softly light fibrous paper using the selected adaptive hue; the exact two-to-four-ink palette; one chromatic dark; flat relief-print fields; structural carved contours; form-following hatch direction; three mark-density zones; exposed-paper light; slight misregistration; incomplete dissolving edges. State that the paper must separate from the dominant coat without requiring a heavy perimeter. State that this is a contemporary selective relief-print illustration, not a uniform filter or historical full-page linocut.

## Paragraph 4 — exclusions

Include: anatomically coherent dog, correct limb count and joint placement, no humanized face, no generic mascot, no sticker border, no photographic rectangle, no glossy 3D shading, no full-page black engraving, no muddy sepia, no decorative paw/bone/heart icons unless requested, no copied text, signature, watermark, or exact reference layout.

## Photo-role language

Use this distinction when a source image exists:

- `CONTENT REFERENCE`: authoritative only for dog identity, anatomy, markings, pose or expression explicitly preserved.
- `VISUAL SYSTEM`: authoritative for composition, paper, palette, carving, negative space, typography scale, and emotional tempo.

Repeat the identity lock in the final prompt. State what must remain recognizable, what may change, which environment cues survive as sparse fragments, and which source-only objects must be omitted. Do not let the source photograph control the complete camera framing or background unless the user explicitly asks.

## Multi-reference role language

When separate images define pet content, dog-region style and background style, read `reference-fusion.md` and begin with a `SINGLE-CANVAS FUSION LOCK`. State separately: pet photo controls identity; dog-style master controls only the dog's line colors, coat inks and carving; background-system master controls only paper, layout, negative space and environment colors. Require exactly one finished canvas from one generation call. Repeat: `Do not average or leak styles across regions. Do not produce multiple images, panels or intermediate assets.`

## Prompt-only note

Return the prompt exactly as it would be sent to image generation, followed by the chosen recipe. Do not imply generation or inspection occurred.
