# Pet photo transform

Use this protocol whenever a supplied image must determine which pet appears in the result.

## 1. Assign image roles

- Treat “把这只宠物画成……”, “根据照片画”, “保留它的样子”, or an attached photo plus “做一张” as an **edit target / content reference**.
- Treat “只参考这张图的风格” as a **style reference**; do not preserve that animal's identity.
- Ask only if edit-target and style-reference interpretations remain equally plausible.

When several photos show the same pet, use at most three complementary views: the clearest face, one body/profile view, and one view showing distinctive markings. Ignore blurred or redundant images. When photos show different pets, preserve the requested count and map anchors to each pet separately.

When one source photo clearly contains multiple primary pets and the user does not select one, preserve all primary pets. Do not treat singular colloquial wording such as “画小狗” as an instruction to delete the other clearly posed pet. Ignore only background reflections, printed animals, screens, toys, or accidental partial animals that are not part of the requested subject.

## 2. Inspect and write the identity lock

Inspect actual pixels before writing the prompt. Record only visible or user-supplied facts. Do not guess breed, age, sex, or temperament.

Select five to nine high-value anchors across these groups:

- **Face geometry:** head shape, eye size and spacing, gaze, muzzle length and width, nose size, mouth line.
- **Ear and hair silhouette:** upright, folded, dropped, cropped, feathered; curls, top tuft, fringe, whiskers, or smooth coat.
- **Color map:** base coat, facial blaze, muzzle/chest/paw patches, gradients, spots, and asymmetry.
- **Body and pose:** compact or long proportions, chest width, leg length, tail form, sitting/standing angle, head tilt.
- **Expression:** alert, gentle, solemn, sleepy, playful; describe visible cues rather than human emotions alone.
- **Accessories:** collar, harness, clothing, tag, or bow. Preserve only when visible and visually important or requested.

Write a compact lock such as:

```text
IDENTITY LOCK — preserve: small companion dog; warm apricot curly coat; white blaze through forehead and muzzle; large dark round eyes with wide spacing; black rounded nose; dropped feathered ears; tousled crown curls; slight upward head tilt; pink-and-pale-blue striped knit garment. Do not genericize the face, straighten the curls, change the markings, or invent accessories.
```

The example demonstrates field structure only. Derive every real lock from the current user's images.

For multiple pets, write one labeled identity lock per pet plus a relationship lock:

```text
PET A IDENTITY LOCK — [five to nine visible anchors].
PET B IDENTITY LOCK — [five to nine visible anchors].
RELATIONSHIP LOCK — preserve: left/right or front/back order; relative seated height; visible gap or overlap; shared gaze/gesture; distinct bodies and limbs. Do not merge coats, faces, accessories, or paws.
```

## 3. Decide preservation scope

- Default to **High** for a recognizable pet: preserve identity lock, anatomy, coat map, expression, and important accessories.
- Use **Medium** only when the user requests a looser reinterpretation: preserve the main silhouette and defining markings while allowing pose or crop to change.
- Keep the source pose and head angle when they contribute strongly to identity. Otherwise allow a modest pose redesign that remains anatomically plausible.
- Treat the original room, furniture, toys, people, text, and incidental objects as removable unless the user asks to retain them.

After locking identity, read `background-contrast.md` and choose the paper from the pet's dominant coat color and value. Let coat color outrank clothing, collar, and source-room colors unless an accessory covers more visible area than the coat. Record the choice as a paper contrast lock.

Then read `environment-extraction.md`. Inspect the source setting separately from the pet and build an environment lock with one primary anchor and up to two micro-accents. Default to retaining a sparse environmental memory rather than deleting every source cue. Omit all environment cues when they are misleading, unsafe, illegible, or visually empty.

## 4. Pass the real image into generation

- If every edit target has a readable local path, use `referenced_image_paths` with only the selected pet images.
- If any target exists only in the conversation, use `num_last_images_to_include` set to the smallest number that includes every selected target, up to five.
- Never use both mechanisms in one call.
- If neither mechanism can include every required target, ask the user to attach the missing images again.
- Label the input as `CONTENT REFERENCE`, authoritative for identity. Keep the skill's visual system authoritative for paper, carving, palette, hierarchy, and layout.

## 5. Compile the edit prompt

Put the identity lock before style language. Then state:

1. **Must remain:** the selected identity anchors and requested accessory/pose.
2. **May change:** crop, background, color separation, print texture, and layout; pose only within the selected preservation scope.
3. **Environment lock:** name the retained source cues, their abstract treatment, placement, and maximum coverage.
4. **Must disappear:** unselected source-room objects, photographic rectangle, camera blur, logos, text, and clutter.

Avoid breed-only descriptions when individual anchors are available. “A cute poodle” is not an identity-preserving instruction.

## 6. Compare and retry

Inspect the generated result beside the source at full size and thumbnail size. For multiple pets, compare each labeled pet separately, then check count, relative scale, placement, body separation, and relationship. For every pet, check face geometry first, then ear/hair silhouette, color map, body/pose, expression, accessories, and finally the environment lock. Confirm that retained cues are recognizable but remain subordinate.

Regenerate once when a requested pet is missing, bodies merge, relative scale changes materially, two or more high-value anchors drift, or one signature anchor disappears. Tighten the affected identity or relationship lock, reduce permitted pose changes, remove competing style language, and repeat the source-image input. If the second result still drifts, disclose the limitation.

## 7. Return preservation details

Return the generated image, final prompt, recipe, photo role, preservation level, five to nine identity anchors, retained environment anchors, and any remaining limitation. Never claim identity preservation without comparing the actual result to the source.
