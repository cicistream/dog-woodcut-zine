# Quality gate

Inspect the generated image itself. Pass only when all critical checks succeed.

## Critical checks

- Every requested pet reads immediately as a dog at thumbnail size; no requested pet is missing.
- Anatomy is coherent for each pet: plausible head/body relationship, ears, muzzle, four-limb logic, paws, and tail; no fused or duplicated parts. Multi-pet bodies, faces, coats, accessories, and limbs remain distinct.
- For photo transforms, compare side by side at full view and thumbnail view. Face geometry, ear silhouette, eye spacing, muzzle, coat color/markings, hair or fur character, proportions, expression, and preserved accessories must agree with each declared identity lock. Multi-pet count, relative scale, ordering, spacing, and relationship must agree with the relationship lock.
- Relief-cut lines visibly construct the dog's form; they are not merely paper grain, noise, or a uniform overlay.
- Open paper, medium hatching, and localized dense cuts are all present.
- One coherent negative-space region remains, and dark ink is localized.
- Retained source-environment cues are recognizable as sparse fragments, occupy no more than 18% of the canvas, and remain less detailed and lower contrast than the dog.
- At thumbnail size, the dog's outer silhouette separates from the paper through coat-to-paper hue or value contrast. The paper must not merge with the dominant coat.
- In a mental grayscale check, at least one broad dog region remains distinguishable from the adjacent paper without relying on a dark perimeter.
- The palette contains a confident chromatic dark and restrained fresh accents.
- The composition feels calm, original, and editorial rather than commercial or cute-mascot generic.
- No copied reference wording, logo, signature, watermark, or exact layout appears.
- For regional style fusion, the pet follows the content photo, the dog region alone follows the dog-style master's line/color/carving, and the background alone follows the background master's paper/layout/environment color system.
- A fusion request returns exactly one integrated finished canvas, not a dog/background pair, diptych, split screen, collage, contact sheet or multiple variants.

## Failure triggers

Regenerate once with a tighter prompt if any of these occur:

- a requested dog is missing, malformed, merged with another pet, loses identity, or becomes human-like;
- a photo transform becomes a generic member of the breed, changes facial markings or fur character, invents accessories, or copies unwanted background objects;
- the image reads as a photograph with halftone/wood grain added;
- the page becomes a dense black-and-cream antique linocut;
- a sticker, badge, white-bordered blob, or full photographic rectangle contains the dog;
- paper becomes brown, muddy, or faux-vintage;
- the paper shares both the dominant coat's warm/cool family and a similar value, causing the silhouette to disappear;
- typography dominates or contains large garbled text;
- decorative paw prints, bones, hearts, stars, frames, or unrelated symbols appear;
- negative space collapses or several focal points compete.
- the source room is copied literally, environmental cues cover too much of the page, or a retained object competes with the dog's face.
- a fusion leaks styles across regions, copies the background-reference dog, recolors/fades the dog to match the background, imports the dog reference's background, changes the background layout, or produces more than one image/panel.

When coat and paper merge, change the paper field first. Do not compensate by thickening or darkening the dog's outer contour. After one failed regeneration, disclose the remaining limitation instead of presenting the result as fully successful.
