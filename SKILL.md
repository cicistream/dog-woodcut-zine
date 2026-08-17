---
name: dog-woodcut-zine
description: "Generate original illustrations of one or more dogs in a calm contemporary woodcut zine visual system: adaptive fibrous paper, selective carved lines, limited fresh inks, generous negative space, sparse source-environment accents, and quiet emotional storytelling. Use when the user wants a dog portrait from a theme, mood, breed description, or pet photo; wants recognizable pets redrawn as woodcut, linocut, indie-zine, or editorial art; wants environmental details abstracted from a source photo; wants one reference's dog rendering fused with another reference's background layout and color in one finished image; or wants a production-ready prompt or reusable visual recipe in this style."
---

# Dog Woodcut Zine

Create an original dog-centered raster illustration and expose the prompt and recipe used. Keep the work contemporary, airy, chromatic, and emotionally quiet rather than imitating a specific existing image.

## Route the request

- **Generate — default:** brief or theme → concept → recipe → prompt → image → inspection.
- **Photo transform:** one or more supplied pet photos → one identity lock per requested pet → redesigned composition → image → source comparison.
- **Single-canvas style fusion:** pet photo supplies identity; one reference supplies dog-region rendering; another supplies background layout/color → one prompt → one generation call → one finished image.
- **Prompt only:** return the compiled prompt and recipe without claiming an image was generated.
- **Analyze + generate:** when references are supplied, inspect them, extract general visual grammar, then make a new dog composition. Do not copy their text, subject, or layout.

If the user asks to “做一张” or “生成”, generate the image. Ask only when a missing choice would materially alter dog identity or intended output.

## Load references

- Read `references/style-system.md` for every request.
- Read `references/variation-recipes.md` before selecting a composition.
- Read `references/background-contrast.md` before choosing the paper field or ink palette.
- Read `references/environment-extraction.md` whenever a pet photo contains usable environmental cues or the user asks to retain atmosphere from the source.
- Read `references/reference-fusion.md` whenever separate images define the pet identity, dog drawing style, and background system, such as “按图 1 的线条颜色画小狗，按图 2 的布局颜色画背景”.
- Read `references/prompt-compiler.md` for Generate, Photo transform, and Prompt only.
- Read `references/photo-transform.md` whenever a user supplies a pet image or asks to preserve a specific pet.
- Read `references/quality-gate.md` before returning a generated image.

## Photo transform

Follow `references/photo-transform.md`. Inspect the real images, write a compact identity lock, extract a restrained environment lock with `references/environment-extraction.md`, pass the images into generation, and compare the result with the source. Default to high identity preservation. Do not rely on a prose description when an actual usable image is available.

## Reference fusion

Follow `references/reference-fusion.md`. Separate content identity from regional visual styling: keep the pet photo authoritative for who the dog is, apply the dog-style reference only inside the dog region, and apply the background reference only to the paper field and environment. Generate exactly one finished canvas in one image-generation call; never generate separate dog and background images.

## Generate workflow

1. Preserve the requested pet count. When a source photo clearly presents multiple primary dogs and the user says “根据这张照片画小狗” without selecting one, keep all primary dogs in one image. Reduce the brief to one emotional beat and one relationship or gesture per pet; do not add unrequested animals.
2. Analyze the dog's dominant coat hue, value, and saturation. Create a paper contrast lock with `references/background-contrast.md`.
3. For a photo transform, choose one primary environment anchor and up to two micro-accents from `references/environment-extraction.md`; omit them when the source offers no useful cue.
4. Choose one composition and one ink recipe from `references/variation-recipes.md`, then adapt its paper field to the contrast lock. Use `Paired orbit` for two pets or a compact asymmetric cluster for three; preserve each pet's relative size and separation. Vary visual grammar, not merely object position.
5. Compile a concrete four-paragraph prompt using `references/prompt-compiler.md`.
6. Generate one finished raster image with the built-in image-generation capability. For single-canvas fusion, pass every required reference into the same call and request exactly one composite canvas—no intermediate assets, split panels, or alternate outputs. Default to a vertical 3:5 image unless the user names another format.
7. Inspect the actual result against `references/quality-gate.md` at full size and thumbnail size. Regenerate once if a major failure is visible.
8. Return the generated image, the final prompt, the selected recipe, and one concise interpretation note. For photo transforms, also return preservation level, identity anchors, and retained environment anchors. For fusion, also return the reference role map.

## Source boundaries

- Learn visual grammar from references, not their exact composition, typography, wording, signature, watermark, characters, or recognizable subject.
- Do not claim visual observations about files that were not inspected.
- Keep user-supplied text short; image models may distort long text. Prefer adding only a title of one to four words and optional microtype.
- Do not name living artists or request a replica of a particular work. Translate the request into medium, composition, color, texture, and mood.

## Output contract

For generation, return:

1. one generated finished image;
2. final image-generation prompt;
3. recipe: composition / abstraction / ink palette / paper field / carving / typography / mood;
4. one-sentence interpretation;
5. photo role or multi-reference role map, preservation level, identity anchors for each pet, relationship lock for multi-pet images, and retained environment anchors when applicable.

For Prompt only, return items 2–4 and clearly state that no image was generated.

## Success condition

Every requested dog must remain individually recognizable and anatomically coherent, with correct relative scale and separation. Use selective structural carved marks, exposed paper, limited fresh ink, calm hierarchy, and an original editorial composition. The result must not read as generic cute mascots, a glossy advertisement, a photo with a texture filter, or a dense antique black-and-cream linocut.
