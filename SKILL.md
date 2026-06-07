---
name: generate-avatar
description: Generate or refine cartoon profile avatars for Xiaohongshu, X, GitHub, and other social platforms from a user photo, a style reference, or a text-only brief. Use when the user asks to make an avatar, profile picture, social-media portrait, cartoonized headshot, avatar variants, circular preview, platform-sized exports, or a reusable avatar prompt.
---

# Generate Avatar

Create recognizable, uncluttered cartoon avatars through a guided visual workflow. Use the built-in `image_gen` tool for generation and editing.

## Core Workflow

1. Determine the target platform and intended impression.
2. Determine the input mode:
   - **Photo mode:** Use the supplied portrait as the identity reference.
   - **Reference mode:** Use one image for identity and another for style.
   - **Text-only mode:** Create a fictional or described person without implying identity preservation.
3. Gather only missing high-impact details:
   - platform
   - subject or theme
   - preferred style
   - important identity traits, if no photo is supplied
4. If the user has not chosen a style, show `assets/avatar-style-board.png` and briefly recommend 2-3 styles. Do not require the user to understand style terminology from text alone.
5. Generate four square candidates with meaningful variation.
6. Present the four candidates clearly and ask the user to choose one.
7. Refine the selected candidate with one targeted change at a time.
8. Deliver one final square avatar by default. Offer optional circular preview, platform exports, and the reusable final prompt.

Do not repeatedly ask for information already supplied. When the brief is sufficient, generate immediately.

## Clarification Rules

Ask no more than three concise questions at once. Prioritize:

1. Which platform is this for?
2. Will the user provide a portrait, or should the avatar be created from text?
3. Which visual direction do they prefer?

If the user is unsure about style, show the style board instead of asking an abstract style question. If the user says "you decide," choose a platform-appropriate style and state the choice briefly.

## Candidate Generation

Create four separate candidates rather than one contact sheet when possible. Keep the same:

- identity and recognizable facial structure
- selected art style
- head-and-shoulders framing
- clothing category
- clean, simple background treatment

Vary only useful dimensions:

- expression intensity
- crop or camera distance
- restrained color palette
- degree of stylization

Make every candidate work at small profile-picture size. Keep the face centered with safe padding for circular crops.

## Identity Preservation

When a portrait is supplied:

- Treat it as the identity reference.
- Preserve face shape, hairline, hairstyle, eyewear, skin tone, and distinctive features.
- Preserve apparent age and gender presentation unless the user requests a change.
- Do not beautify into a different person.
- Prefer a clear front-facing photo. If the source is ambiguous, explain the limitation briefly.

When no portrait is supplied, do not claim that the output resembles the user.

## Visual Defaults

- Use a square canvas.
- Use a head-and-shoulders composition.
- Keep the background plain or subtly tonal.
- Do not add text, logos, props, symbols, scenery, frames, or decorative elements unless requested.
- Do not imitate a living artist or named studio. Translate such requests into generic visual characteristics.
- Avoid photorealism unless explicitly requested; default to approachable cartoonization.
- Avoid busy patterns and low-contrast face/background combinations.

Read `references/styles.md` when building or adapting a style prompt. Read `references/platforms-and-delivery.md` when recommending styles, preparing crops, or exporting sizes.

## Prompt Construction

Build prompts from `references/prompt-template.md`. Include:

- usage and platform
- input-image roles
- identity invariants
- selected style
- expression and framing
- background constraint
- variation axis for each candidate
- explicit avoid list

For refinement, preserve all unmentioned attributes and change only the requested element.

## Delivery

Default deliverable:

- one high-quality square avatar

Optional deliverables:

- circular preview with no destructive crop
- platform-specific PNG sizes
- alternate background color
- expression or crop variants
- reusable final prompt

Save project-bound outputs in the current workspace and report their absolute paths. Never leave a final project asset only under the image tool's generated-image directory.

## Safety

Do not create deceptive identity documents or imply identity verification. For public figures, avoid misleading impersonation contexts. For minors, keep styling age-appropriate and non-sexualized.
