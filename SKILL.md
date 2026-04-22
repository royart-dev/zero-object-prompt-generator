---
name: zero-object-prompt-generator
description: Generate a Nano Banana 2 (NB2) prompt for a 3D single-object render in the Zero visual language (Y2K consumer-electronics × designer-object × quiet-personality aesthetic — chunky, translucent-jelly, Y2K-labeled, with a face baked into each object). ONLY trigger this skill when the user explicitly invokes it by name — e.g., says "zero object", "zero object prompt generator", "zero object generator", "make a zero object", "render this as a zero object", or calls it as a named / slash command. Do NOT trigger on generic requests like "render an object", "make a 3D render", "write an NB2 prompt", "do it in Y2K style", "do it in our style", reference-image renders, or concept-to-visual briefs, unless the user specifically names "zero object". This is a deliberately narrow trigger — when in doubt, do not trigger.
---

# Zero Object Prompt Generator

Generates NB2 prompts for 3D single-object renders in a specific Y2K consumer-electronics aesthetic. Every render produced by this skill should feel:

- **Chunky, catalog-honest** — 1998 Braun × Teenage Engineering × MSCHF restrained mode. Not Apple-hero. Not sterile jewelry shoot. Not Fisher-Price toy. Not sci-fi.
- **Translucent-jelly when the object affords it** — iMac G3 / Game Boy Color candy-saturation
- **Quietly playful** — one face baked into each object (a mouth button + an eye decal)
- **Y2K-labeled** — restrained diegetic detail (model codes, spec lines, warning decals, functional labels)
- **Fully isolated** — floating on pure white, no shadow, no base, no cables exiting the silhouette

## When to use this skill

**Narrow, explicit trigger only.** This skill is intentionally NOT auto-triggered on generic render requests. It fires only when the user names it.

Trigger when the user says any of:

- *"zero object"* / *"a zero object"* / *"make a zero object"*
- *"zero object prompt generator"* / *"zero object generator"* / *"use the zero object prompt generator"*
- *"render this as a zero object"* / *"do this as a zero object"*
- A slash/command-style invocation (e.g., `/zero-object`, `/zero-object-prompt-generator`, `@zero-object-prompt-generator`)
- Any phrasing where "zero object" appears as the named thing being requested

**Do NOT trigger** on any of these, even though they sound related:

- Generic *"render an object"* / *"make a 3D render"* / *"product shot of X"*
- *"write an NB2 prompt"* / *"Nano Banana 2 prompt"* without naming this skill
- *"do it in Y2K style"* / *"iMac G3 style"* / *"jelly shell"* on their own
- *"our style"* or *"in the Zero aesthetic"* as ambient style references
- Reference-image-plus-render requests
- Concept-to-visual briefs (*"hero image for empty state"*, *"visual for trust"*)

If the user clearly wants a render in this aesthetic but hasn't named "zero object," prefer to ask them explicitly whether they want to invoke the zero-object-prompt-generator rather than silently triggering it. Undertrigger is the desired behavior.

## Workflow

1. **Identify input mode.** Read `references/modes.md`. The three modes are:
   - **A** — Named object (user just said "render a walkie-talkie")
   - **B** — Concept (user briefed an idea; you pick the object)
   - **C** — Reference image (user dropped an image and wants "our style")
2. **For Modes B and C: confirm the object back to the user in one line before writing the prompt.** This is a cheap redirect point — it saves a wasted render. For Mode C specifically, identify the object and then STRIP the reference's aesthetic (don't carry over its materials, lighting, or mood).
3. **Check the absolute rules.** Read `references/rules.md` first — the non-negotiable constraints (no shadows, no bases, no brand names, no cables exiting silhouette, no external emissions, no wood, no dirt).
4. **Pick the creative twist.** Most common and most forgiving: the translucent jelly shell — see `references/jelly-shell.md`. Other options: material swap, electronic graft, hybrid/morph, impossible balance.
5. **Assign the face.** See `references/face-formula.md`. Pick one mouth and one eye. **If generating a set of objects (course cards, UI tiles, product family), make sure the mouth×eye pair doesn't repeat across the set.**
6. **Pick a color.** See `references/palette.md` for the 7 approved tints, the saturation requirement, and the two approved multi-panel treatments (mono-with-shades, mixed-palette).
7. **Write the prompt** following the 6-layer structure in `references/rules.md`. See `references/canonical-examples.md` for three full worked templates.

## Output format

One prose paragraph per object — ready to paste directly into NB2. The prompt should stack in this order:

1. **Opening sentence** — object, camera angle, floating on pure white
2. **Creative twist** — what makes this a designer piece (jelly shell is the workhorse)
3. **Per-component material palette** — 5–10 components, each with its assigned material, hard boundaries between them
4. **Electronic touch** — LCD + rubber face button + LED + silkscreen labels (graft one onto non-electronic objects)
5. **Y2K diegetic detail** — 8–10 elements total (model code, spec line, functional labels, warning decal, barcode, QC sticker, face decal, face button, LED, optional contained wire)
6. **Technical block** — material accuracy + surface finish + shadowless/baseless staging + camera + aspect ratio + anti-text clause

See `references/rules.md` for the closing technical block text that goes at the end of every prompt.

## Key failure modes to avoid

- **"Clearly visible" / "bold interior" / "visible component outlines" language on jelly shells** — always renders fully see-through with full PCB detail exposed. Use softening: "softly visible as faint darker shapes", "gentle silhouettes", "quiet interior geography".
- **Pale / washed / milky tints** — always specify "saturated, candy-bright, iMac G3 saturation, NOT pale NOT milky NOT washed".
- **Brand names, real or invented** — banned across the board. Real brands (PALM, Fluke, Mattel) read as the dominant text anchor just as much as invented ones (DataPilot, ScanCore).
- **External emissions on white backgrounds** — laser beams, steam, projected light, mist all bleed off the silhouette and break isolation. Keep all light contained inside the object.
- **Cables exiting the silhouette** — wires contained on the object are fine (coiled, looped, terminating at an on-object connector). Trailing ends onto the backdrop are forbidden.
- **Bases, pedestals, stands, feet** — always render the baseless variant. Objects are single self-contained floating forms.
- **Repeating face formula across a set** — diversify the mouth×eye pair so each object has a distinct expression.
- **Dark tints on jelly shells** — deep violet, navy, dark green render near-black. Purple on spheres renders metallic. Stay light-to-mid luminosity.

## File pointers

- `references/rules.md` — absolute rules + 6-layer prompt structure + closing technical block (read first, every time)
- `references/modes.md` — Mode A/B/C workflow details
- `references/face-formula.md` — mouth × eye variation table + decal vs sculpt rule
- `references/palette.md` — 7 approved tints + multi-panel treatments + saturation
- `references/jelly-shell.md` — translucent-shell calibration and softening language
- `references/canonical-examples.md` — three full worked prompts (alarm clock, CRT monitor, Rubik's cube)

---

*Derived from 33 iterative NB2 tests and a session-length correction log. This skill encodes the locked state as of 2026-04-22.*
