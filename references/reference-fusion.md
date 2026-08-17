# Single-canvas regional style fusion

Create one finished image by applying different visual references to different regions of the same canvas. Do not generate components separately.

## Assign three independent roles

Inspect all supplied images and record:

`SINGLE-CANVAS FUSION LOCK — pet content: [image] controls identity/anatomy/markings/expression/accessories; dog-style master: [image] controls only the dog's line hue, coat palette, ink density, carving grammar and facial contrast; background-system master: [image] controls only paper hue/value/texture, dog scale and placement, negative-space shape, environmental element placement, environmental palette and environmental line density; output: exactly one finished image.`

- Keep the pet photo authoritative for who the dog is. A style sample must not replace its face, markings, pose, or accessory.
- Apply the dog-style master only inside the dog's silhouette and immediate structural marks.
- Apply the background-system master only outside the dog's silhouette, including paper, environment, ground rhythm and spatial hierarchy.
- Never average the dog rendering with the background reference. Never recolor or fade the dog merely because the background master is pale.
- Never copy the dog shown in a background reference.

If no separate pet photo exists and the user explicitly says “use the dog in Image 1,” let Image 1 supply both pet content and dog-region style. Image 2 still controls only the background system.

## One-call, one-image rule

- Pass the pet content image, dog-style reference and background-system reference into one built-in image-generation call.
- Ask for exactly one complete vertical canvas containing the styled pet integrated into the styled background.
- Do not generate a dog-only image, background-only image, mask, contact sheet, comparison sheet, diptych, split screen, collage, before/after pair, or multiple variants.
- Do not compose two separately generated outputs in a later step. The model must resolve edges, paper cuts, color interaction and environment hierarchy within the single final image.
- A retry replaces the failed candidate; it does not become a second deliverable.

## Dog-region style lock

Extract from the dog-style master:

- contour hue and value;
- coat ink hues and saturation;
- light-cut color inside white or pale markings;
- eye/nose depth;
- line thickness, break frequency and density;
- direction and rhythm of fur carving;
- degree of misregistration and dry-gap texture.

Preserve those traits after scaling the pet. Keep the eyes and nose as localized deepest marks, medium-rich coat fields, readable markings, and balanced broken contours. Do not import the dog-style reference's background, subject size, environment, or paper color.

## Background-system lock

Extract from the background master:

- vertical format and exact subject coordinates;
- subject scale and ground contact;
- paper hue, value and fiber texture;
- coherent blank-field shape;
- environment object positions, sizes and spacing;
- environment ink colors, line density and contrast hierarchy.

Do not import the background reference's dog rendering, face, coat colors or line density into the pet. Keep environmental line density at one-third to one-half of the styled dog's medium-detail zone unless the reference is visibly lighter.

## Confirmed fused-companion background system

When the background master matches or the user requests the confirmed fusion layout:

- Use a vertical 3:5 canvas.
- Place the complete dog in the lower third, slightly left of center.
- Dog height: 34%–38% of page; dog area: 21%–26%.
- Keep the top of the dog below roughly 56%–60% and the paws near 88%–91% of page height.
- Preserve 60%–68% one-piece blank paper, especially through the center and upper-right.
- Place one or two faint structural fragments at the far upper-left, totaling 4%–7%.
- Keep the grounding patch compact, 4%–6%, and no wider than 1.25 times the dog.
- Place one low-contrast object whisper in the lower-right, about one-quarter to one-third of the dog's head size and 1%–2% of canvas.
- Keep a visible gap between dog and object. Never place environment behind the face.

## Four-paragraph prompt pattern

1. Start with the `SINGLE-CANVAS FUSION LOCK`, identity lock, and dog-region style lock.
2. Describe only the background master's layout, paper, environment colors and measurable placements.
3. Explain how dog-region inks meet the background paper while remaining visually distinct; keep environment marks subordinate.
4. Exclude role leakage and multiple outputs: no background colors replacing the dog's palette, no dog-style background, no copied background-reference dog, no split panel, collage, diptych, contact sheet, intermediate assets or second image.

## Compare and retry

Inspect the one output against each role separately:

1. pet content: face, markings, expression, anatomy and accessory;
2. dog-style master: line color, coat palette, facial contrast and carving density inside the dog;
3. background-system master: paper color, layout, dog scale, negative space, environment positions and environment colors;
4. output shape: one integrated canvas, not two images or visible panels.

Regenerate once if the dog adopts the background reference's pale line style, the background adopts the dog reference's colors/layout, the pet identity drifts, or the result contains multiple panels or outputs.
