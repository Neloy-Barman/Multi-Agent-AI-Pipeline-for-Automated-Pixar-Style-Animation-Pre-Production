---
name: seedance-1-5-pro-prompt-writing-guide
description: Write, rewrite, and review prompts for the Seedance 1.5 Pro video model (model id seedance-1.5-pro). Covers text-to-video, image-to-video (animating a still), first-frame/last-frame smooth transitions, multi-shot sequences with cuts, dialogue and voiceover with lip-sync, sound effects, background music, camera and lens control, style references, and transformation/VFX shots. Use this skill whenever the user asks for a Seedance prompt, a video-generation prompt for seedance-1.5-pro, a prompt to animate an image, a start-frame/end-frame transition prompt, or a prompt with speech, sound, or music, and also when they misspell it ("Cadence", "Seedence", "Seed dance") or just say "video prompt" in a Seedance context. Also use it to critique or fix a Seedance prompt that gave bad results. Apply it even for quick one-line requests so the prompt follows the proven structure.
---

# Seedance 1.5 Pro Prompt Writing Guide

Seedance 1.5 Pro (`seedance-1.5-pro`) is a video model that generates **picture and sound together** in one pass: ambient sound, action sound effects, background music, and lip-synced speech. It supports text-to-video, image-to-video, and first-frame/last-frame generation. The prompt is the main lever you have, so a well-structured prompt matters more than anything else.

This skill tells you how to turn a rough idea into a prompt the model reads well. Follow it every time you write a Seedance prompt so the user never has to hand-format prompts or guess what is good.

## Workflow

1. **Pick the mode** (see "Modes" below). Infer it from what the user gave you: no image means text-to-video, one image means image-to-video, two images (start and end) means first/last frame.
2. **Fill gaps with sensible defaults** instead of interrogating the user. Ask at most one short question, and only when the subject itself is missing. State your assumptions in one line after the prompt.
3. **Write the prompt** using the formula, the mode's template, and the element guides below.
4. **Run the pre-flight checklist** at the end, and fix any failing line before replying.
5. **Reply in the output format** at the bottom: mode, the prompt in a code block, assumptions.

## Why the structure matters

Seedance weights the opening of a prompt most heavily and loses instructions when asked to do too much at once. That is why the order is fixed (most important first), why each clip gets one subject, one camera move and a few actions, and why vague words ("dynamic", "cool", "camera moves") produce weak results. Specific, concrete, filmmaker-style language is what separates mediocre output from impressive output.

## Modes

| Mode                       | Use when                                              | Prompt's job                                                              |
| -------------------------- | ----------------------------------------------------- | ------------------------------------------------------------------------- |
| **Text-to-video (T2V)**    | No image supplied                                     | Invent the whole shot: subject, action, scene, camera, light, sound       |
| **Image-to-video (I2V)**   | One image supplied                                    | Protect what is in the image; describe only motion, camera, sound         |
| **First/last frame (FLF)** | Two images: start and end                             | Describe the bridge between them: camera path, subject motion, continuity |
| **Multi-shot**             | A sequence with cuts, a conversation, or a mini story | Number the shots, one size and action each, style stated once             |

Multi-shot can be combined with T2V or I2V. Dialogue and sound can be added to any mode.

## The core formula

```
Subject + Action + Environment + Camera + Lighting/Aesthetic + Sound + (Quality tail)
```

Everything after Action is optional, but each skipped element is one the model will guess. Put the most important thing first. A tail such as "cinematic, 4K" tunes the shot and goes last, never first.

**Length.** The sources point in two directions, and both are right for their case:

- **Simple single shot with no speech:** one to three sentences, roughly 20 to 40 words. Past about 50 words, the prompt is usually hiding a second idea that belongs in its own clip.
- **Shots with dialogue, voiceover, transformations or several cuts:** as long as needed, but organized (shot by shot, speaker by speaker). Detail is welcome when it is concrete and non-contradictory.
- **First/last frame:** keep it minimal, one short paragraph (about 25 to 60 words). The two images already carry the visual detail.

## Writing each element

### Subject

Name one clear subject in a few words. Add only the features that must stay stable: age, clothing, hair, one distinctive prop. If you cannot name the main subject in one breath, the model cannot lock onto it. One to two subjects work well; five or more get messy. When several characters appear, give each a consistent, feature-based label ("the tall man in the grey coat") and reuse that label every time.

### Action / motion

Use a specific verb plus a degree adverb. "Mending a net", "sliding down the glass", "raises both hands powerfully toward the sky" beat "moving". Use sequencing words for pacing: "first rotates slowly, then stops and faces the camera". Limit to one subject and two to three actions per clip. Avoid contradictory motions.

### Environment

One or two details that set the place and mood: "wet late-night alley with neon reflecting on the ground". Remove background clutter that does not serve the shot.

### Camera

Use exactly **one** camera move per shot, with a **direction and a speed word**: "camera slowly dollies in", "gently pans right", "slowly cranes up". Generic wording ("dynamic camera", "camera moves") is the usual cause of jerky, too-fast motion.

For a controlled move, use this formula: **starting composition + move + amplitude + ending composition.** Example: "Starts on a medium shot above the chest, slowly dollies in at a steady speed, ending on an extreme close-up of the eyes."

Vocabulary to draw from:

- **Camera angle:** eye-level, high angle, low angle, bird's-eye view, overhead.
- **Narrative perspective:** over-the-shoulder, subjective (first-person) view, surveillance/fisheye view, telescope view.
- **Subject angle:** front, profile, half-profile, back view, top, bottom.
- **Shot size:** wide/full shot, medium shot, medium close-up, close-up, big/extreme close-up. Art terms also work: headshot, bust, half-length, full-length. Grammar: "Subject + shot size" ("close-up of the man on the left").
- **Movement:** dolly in/out, pan, tilt, track/follow, rise/fall (crane), orbit/surround, rotate, zoom, locked-off (static).
- **Combined moves:** Hitchcock zoom = dolly out while the lens zooms in, with the subject's size held constant. Bullet time = slowed time plus an orbit around the subject.

### Lighting and aesthetic

Give a time of day or a light source plus a direction: "golden-hour backlight with long shadows", "soft window light from the left", "cool blue panel light with warm alert flashes". Lighting sells a shot more than extra adjectives, and a flat scene almost always means the lighting line is missing. Add one style phrase that fixes the look: "documentary realism", "2D anime", "Pixar-style 3D animation", "premium commercial", "cyberpunk neon".

**Style references work.** Name a well-known visual style directly: "Imitate the style of Hayao Miyazaki's anime", "Referring to the style of Disney's 2D animated movies", "in the style of the Japanese drama _Little Forest_". An explicit reference conveys mood, tone and palette better than adjectives alone. Reference styles and genres, not named real people's likenesses, since platforms often reject those.

### Quality tail (optional)

"Cinematic, shallow depth of field, 4K" for live-action and commercial looks; "gentle motion, high detail" for anime; "smooth fluid motion" for abstract and macro. These nudge quality, but they cannot rescue a weak subject or a vague action.

### Aspect ratio and duration

These are normally generation settings on the platform. If the user needs a framing intent in the prompt itself (for example a vertical social clip), a short phrase such as "vertical 9:16 framing" is acceptable. Do not invent settings the platform may not have.

## Sound (a core strength of 1.5 Pro)

Sound is generated with the picture, so describe it in the same prompt. Audio that is described tends to sync far better than audio left to chance. Four layers:

### 1. Ambient and effects (SFX)

Describe what is audible and what causes it, tied to a visible event: "rain outside the window grows slightly heavier, drops merging into streams down the glass", "a fuel depot explodes at dusk and a fireball rushes into the sky". Name sounds only when they matter; do not list ten.

### 2. Background music (BGM)

Music is generated automatically to match the prompt by default. To steer it, specify **genre/instrument, mood, and pacing**: "a heart-stirring symphony with a theme full of strength and hope", "a gentle, nostalgic piano or guitar solo with faint reminiscence and a touch of sadness beneath the warmth". Music can drive motion: "fast-paced pop snippet; the cartoon character claps in time with the drumbeat". If the user wants no music, say so explicitly in the prompt (this is not covered in the source documentation, so tell the user to test it).

### 3. Dialogue

This is where 1.5 Pro stands out: lip-synced speech, single or multi-speaker, with stable voice timbre.

- **Declare the language and put the spoken lines in quotes**, labelled by speaker: `English dialogue: Man: "..." Woman: "..."`.
- **Write each line in the target language's own script** (Korean in Hangul, Mandarin/Cantonese in Chinese characters, and so on). Supported: Mandarin and dialects (Cantonese, Sichuan, Shaanxi, Taiwanese accent), English, Japanese, Korean, Spanish, Indonesian.
- **Make every speaker visually identifiable** (gender, age, clothing, position) so lip movements attach to the right face. For groups, describe them by distinct features: "a white female, a Black male, an Asian female and a white male".
- **Control delivery** with the pattern _emotional state + tone + speaking pace_: "In a gentle emotional state, with a soft tone and a slow speaking pace, say: '...'". Examples: calm = even tone, normal pace; restrained = low tone, very slow pace.
- Add a quick note on how each line is said when it matters ("lowering his voice and speaking rapidly", "flustered and helpless").
- **Keep lines short** so they can be spoken within the clip. If unsure, use fewer lines rather than cramming.
- **Dialect cue:** "He said in Cantonese, '...'" works for a single line.

### 4. Voiceover

Describe the voice as timbre, emotion, intonation and pace, then the line: "A deep, calm male voice says, '...'" or "A clear, confident female commercial voice-over with a refined tone and moderate pace delivers: '...'". Make the visuals match what is said (the night-to-dawn scene under a documentary narration; the product close-ups under a commercial read).

## Multi-shot and transitions

Seedance can cut between shots inside one generation while keeping character, style and lighting consistent.

**Structure:**

1. State the style and the characters once at the top (so every shot inherits them).
2. Then list shots. Either use "Shot 1: ... Shot 2: ..." or flowing prose with explicit cut language ("The shot cuts to...", "The camera then cuts back to...").
3. For every shot give: **shot size and angle, what the subject does, and any line spoken**.
4. Close with a pacing note ("the pace slows", "the frame freezes").

**Typical shot rhythm:** establishing medium/wide, then close-ups of the speaker and the reaction, then a return to the wide shot.

**Reverse-shot dialogue:** alternate medium close-up on A (A speaks), close-up on B (B replies), back to a tighter shot on A (silent reaction). Escalating tightness builds tension. For three people, open and close on a group medium shot with individual close-ups in between.

**Visual transformations in shots:** time each beat. For example, Shot 2 close-up of the palm, particles begin to appear; Shot 3 close-up of the neck, particles rise; Shot 4 medium shot, the glowing hat appears; Shot 5 close-up, she smiles and speaks.

Keep multi-shot clips to a handful of shots (about 3 to 5). Each additional cut is another thing that can drift.

## Effects and transformations

For magic, morphs and VFX, the model needs the **trigger, the process, and the end state**:

- **Trigger timing:** what starts the effect ("her finger touches the old ball, and instantly a soft golden light spreads out like ripples").
- **Process:** the order and speed of change ("the cat's body gradually elongates as it stands; fur becomes fluffy orange hair; ears remain; clothing changes"). Use speed language ("within two seconds", "time-lapse speed", "soft and smooth as a marshmallow").
- **End state, concretely:** the final look and detail ("pupils red, black dragon scales spreading along the cheekbones, sparks from gaps between scales").
- **Style tag at the end:** "Solarpunk with a Ghibli feel", "Dark fantasy, body-horror aesthetics".

## Mode templates

### A. Text-to-video

```
[Subject + key features], [action with degree adverb], [environment]. [One camera move with direction and speed], [lighting with source/time], [style]. [Sound: ambient / music / dialogue]. [Quality tail].
```

Because there is no reference image, describe the opening frame clearly: who or what, where, in what light.

### B. Image-to-video

The image already defines composition, subject and style. Do **not** re-describe what is visible. Spend the words on motion.

```
Use @Image1 as the first frame. Keep [the things that must not change: face, product shape, label, layout] unchanged. [What moves, with degree adverbs], [one camera move with speed], [light or atmosphere change]. [Sound].
```

Name what to protect (identity, clothing, product geometry, logo, pose) and what should move. Writing "Based on this image, ..." is also fine. Avoid asking for readable on-screen text, which video models handle poorly.

### C. First frame / last frame (FLF)

Keep it **minimal: one short paragraph**. Do not re-describe the images. Cover three things only: (1) which image is first and which is last, (2) how the camera and subject travel between them, (3) what stays consistent, closing with a smooth-transition cue.

```
@Image1 as the first frame, @Image2 as the last frame. [One camera move with speed] as [the subject's natural movement that bridges A to B]; same [lighting / outfit / location] throughout, smooth transition.
```

Optionally add one short sound clause ("soft click as the lid opens"). If the transition is a big jump (outdoors to indoors, before to after), name the bridging motion explicitly ("tracking in through the door as the light adapts"). Add only the artifact guard that matters for the subject (no logo distortion, no identity drift, no flicker), not a long list.

**Examples:**

- _Product reveal:_ `@Image1 as the first frame, @Image2 as the last frame. Slow push-in with a gentle arc to the right as the box opens naturally; same marble table and warm morning light, smooth transition, no logo distortion.`
- _Before/after:_ `@Image1 as the first frame, @Image2 as the last frame. Subtle forward micro-dolly with natural facial movement only; same model, hairstyle and background, smooth transition, no identity drift.`
- _Scene shift:_ `@Image1 as the first frame, @Image2 as the last frame. Camera tracks in through the doorway as the light shifts from cold rain to neon glow; same coat and bag, consistent reflections, smooth transition.`

The `@Image1` / `@Image2` tags are the convention in the source material. If the platform uses a different way of referencing uploaded images, follow the platform's convention.

## Example prompts by use case

Use these as patterns. Swap the subject, keep the scaffolding.

**Product (T2V, silent):**
`A glass perfume bottle on polished marble, a single water drop sliding down the glass, camera slowly orbits left, clean commercial style, bright studio lighting with soft reflections, shallow depth of field, cinematic, 4K.`

**Nature (T2V, with ambient sound):**
`A misty pine valley at sunrise, low fog drifting between the trees, camera slowly cranes up to reveal the horizon, epic nature documentary style, warm golden-hour backlight. Soft wind and distant birdsong, a calm orchestral swell building. Cinematic, 4K.`

**Character with dialogue (T2V):**
`In a warm, softly lit independent bookstore, a man and a woman stand shoulder to shoulder flipping through the same book, light falling across the pages and their faces. The camera makes an extremely subtle dolly-in, quiet and intimate. English dialogue: Man: "Did you ever read this one before?" Woman: "No, but I think I want to, with you."`

**Anime (T2V):**
`A teenage girl on a rooftop as cherry blossoms fall, her hair and scarf drifting in the breeze, camera slowly pulls back to reveal the city, 2D anime style, soft pastel afternoon light, gentle ambient wind and a light piano melody, gentle motion, high detail.`

**Voiceover documentary (T2V):**
`A deep, calm male voice says, "In the vast silence of the universe, our world is but a fleeting moment." The scene slowly transitions from night to dawn, stars fading as the sun rises behind the mountains, camera slowly cranes up, epic documentary style.`

**Image-to-video (I2V):**
`Use @Image1 as the first frame. Keep the person's face, clothing and the room layout unchanged. She slowly turns her head toward the window and exhales, hair strands moving in a light breeze, soft window light shifting across her face, camera makes a gentle dolly-in. Quiet room tone and a faint distant rain.`

**Multi-shot reverse-shot (T2V):**
`Realistic cinematic style, tense interrogation room. Shot 1: medium close-up of the detective in a dark suit, who says calmly, "You returned to that alley at 11:47, and that's no coincidence." Shot 2: cut to a close-up of the suspect in a grey hoodie, who gives a soft sneer, averts his gaze and says, "Coincidences always seem well-planned in hindsight." Shot 3: cut back to a closer close-up of the detective, expression turning cold, silent, the tension rising. Low ambient hum, no music.`

**Transformation (T2V):**
`A girl stands in a dim bedroom and gently touches an old Christmas ball; instantly a soft golden light spreads out like ripples, her clothes reshape into Christmas attire, a tree grows from the floor and its lights switch on one by one while snow condenses and falls outside the window. Warm cozy lighting, gentle chime sounds, a soft magical melody.`

## Quality keywords (use sparingly)

- **Quality:** cinematic, professional, high-quality, 4K.
- **Lighting:** golden hour, studio lighting, dramatic shadows, soft window light.
- **Depth:** shallow depth of field, bokeh, foreground blur.
- **Style:** photorealistic, anime style, oil painting style.
- **Motion:** smooth, fluid, deliberate, gentle.

## What to avoid

- Vague camera or motion words: "dynamic", "camera moves", "cool".
- More than one camera move per clip, or more than two to three actions.
- Contradictory motions, or competing descriptors for one subject.
- Piling on background objects. One to two subjects is the sweet spot.
- Relying on **negative prompts** ("no X, no Y, not Z") as the main control. Positive direction works better: write what should happen. A short protective clause is fine in I2V and FLF ("keep the logo unchanged").
- Requiring readable on-screen text or logos to be generated.
- Re-describing everything already visible in a supplied image.
- Technical jargon the model is unlikely to understand.

## Pre-flight checklist (run before replying)

1. **One clear subject**, named in a few words?
2. **One specific action**, with a degree adverb?
3. **Exactly one camera move**, with direction and speed? (Multi-shot: one per shot.)
4. **Lighting** with a time of day or a source?
5. **One style phrase** that fixes the look?
6. **Sound addressed** (ambient, music, or speech), unless the user wants it left to the model?
7. If there is dialogue: **language declared, lines quoted in the right script, each speaker visually distinct, delivery described, lines short enough?**
8. If I2V or FLF: **only motion, camera and continuity described**, nothing re-describing the image, FLF kept to one short paragraph?
9. **Quality tail last**, not first?
10. Length matches the mode (short for simple shots, organized and detailed only when dialogue or multi-shot demands it)?

Five out of six on the core visual items (1-5 plus the tail) usually yields a usable clip; a disappointing result almost always traces to a skipped line.

## Troubleshooting and iteration

| Symptom                                      | Likely cause                                                | Fix                                                                    |
| -------------------------------------------- | ----------------------------------------------------------- | ---------------------------------------------------------------------- |
| Subject drifts or morphs                     | Too many competing descriptors                              | Cut to one subject sentence; move style into its own clause            |
| Camera too fast or jerky                     | Camera verb has no speed word                               | Add "slowly" or "gently"; use one move only                            |
| Scene looks flat                             | No lighting direction                                       | Add time of day plus light source                                      |
| Output too busy                              | Too many objects or elements                                | Remove background items; keep 1-2 subjects                             |
| Part of the prompt is ignored                | Asking for too much at once                                 | Trim to one subject, 2-3 actions, one camera move                      |
| Lips match the wrong person                  | Speakers are not distinguishable                            | Give each speaker distinct visible traits; reuse the same labels       |
| Image identity or product changes (I2V/FLF)  | Nothing says what to keep                                   | Add a short "keep X unchanged" clause                                  |
| Transition between frames looks abrupt (FLF) | No bridging motion described                                | Name the camera path and the motion that links the frames              |
| Audio does not fit the picture               | Sound was not described, or mood conflicts with the visuals | Describe the sound source and mood explicitly and align with the scene |

**Iterating:** generate 3 to 4 variations of the same prompt first. If all are poor, fix the prompt; if some are good, just generate more and pick. Change **one** element at a time (camera, lighting, or style) so you can see what helped. Test ideas in a short or low-quality draft before spending a full-quality render.

**Evolving a prompt, worked example:**

- Basic: "A woman in a garden." (no motion, no style)
- Better: "A woman in a flower garden, camera slowly dollies forward." (adds motion)
- Good: "A woman in a sunlit flower garden gently touching the petals, camera slowly dollies forward, golden-hour light, soft birdsong and a light acoustic guitar, shallow depth of field, cinematic." (adds action, light, sound, quality)

**Reusing prompts:** keep the scaffolding (camera, lighting, quality tail) and vary the brief. One prompt adapts to many briefs by changing the pace word, the lighting key (high-key, low-key, natural), the setting, and the style label.

## Output format

When the user asks for a prompt, reply with:

1. **Mode:** T2V, I2V, FLF, or multi-shot (one line).
2. **The prompt**, in a single code block, plain text with no markdown inside, ready to paste. Multi-shot prompts may use "Shot 1: ... Shot 2: ..." inside the block.
3. **Assumptions:** one line (e.g., "Assumed a 5-second vertical clip with ambient sound and no speech.").
4. Offer variations only if asked. If the user asks for several options, vary one dimension (camera, lighting, or style) per variation.

When the user shares a prompt to **review or fix**, name the failing checklist items, explain each in a sentence, and give the corrected prompt in a code block.

Never claim a prompt will render identically every time. Video generation is probabilistic, so present the prompt as a strong structured starting point to test and refine.
