# Prompt Template

Use only the fields that help the task.

```text
Use case: stylized-concept
Asset type: square profile avatar for <platform>
Primary request: Create a recognizable cartoon avatar of <subject>.
Input images: Image 1 is the identity reference. Image 2 is the style reference. <omit unavailable roles>
Identity invariants: Preserve <face shape, hair, eyewear, skin tone, distinctive features>.
Style: <selected style definition from styles.md>.
Expression: <expression>.
Composition: centered head-and-shoulders portrait, facing camera, face readable at small size, safe padding for a circular crop.
Clothing: <simple clothing; preserve category if identity reference is supplied>.
Background: plain <color or tonal family>, uncluttered, strong face/background separation.
Variation: <one deliberate variation axis for this candidate>.
Preserve: apparent age, gender presentation, identity, crop family, clothing category, and selected style.
Avoid: text, logos, watermark, props, scenery, decorative objects, extra people, distorted facial features, busy patterns, accidental identity changes.
```

## Four-Candidate Variations

Use one controlled variation per output:

1. Balanced default: gentle smile, medium crop, neutral palette.
2. More expressive: warmer smile, same identity and style.
3. More graphic: slightly stronger contrast and simplified shapes.
4. More characterful: modestly increased stylization without losing likeness.

## Refinement Template

```text
Edit the selected avatar. Change only <requested change>.
Preserve the person's identity, face shape, hairstyle, eyewear, skin tone, clothing, art style, crop, background family, lighting, and all unmentioned details.
Do not add new objects, text, logos, or decorations.
```
