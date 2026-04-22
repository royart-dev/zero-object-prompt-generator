# Zero Object Prompt Generator

A Claude skill for generating [Nano Banana 2](https://deepmind.google/technologies/nano-banana/) (NB2) prompts that produce 3D single-object renders in a specific aesthetic: **Y2K consumer-electronics × designer-object × quiet personality.**

Think 1998 Braun × Teenage Engineering × MSCHF restrained mode, with a face baked into every object.

## What it generates

Single-object 3D renders that feel:

- **Chunky, catalog-honest** — not Apple-hero, not sterile jewelry shoot, not Fisher-Price toy, not sci-fi
- **Translucent-jelly when the object affords it** — iMac G3 / Game Boy Color candy-saturation
- **Quietly playful** — one face per object (a rubber mouth button + a printed eye decal)
- **Y2K-labeled** — restrained diegetic detail (model codes, spec lines, warning decals, functional labels)
- **Fully isolated** — floating on pure white, no shadow, no base, no cables exiting the silhouette

## How it was built

Derived from 33 iterative NB2 test renders plus a session-length correction log. Every rule in this skill was locked after a render failed in a specific, reproducible way.

## Install

### As a Claude Code plugin / skill

Drop the repo into your Claude skills directory:

```bash
# Example on macOS/Linux
git clone https://github.com/royart-dev/zero-object-prompt-generator.git ~/.claude/skills/zero-object-prompt-generator

# Example on Windows
git clone https://github.com/royart-dev/zero-object-prompt-generator.git %USERPROFILE%\.claude\skills\zero-object-prompt-generator
```

Claude will auto-discover `SKILL.md` and invoke the skill whenever the trigger conditions in the frontmatter match.

### Manual use

If you're not using Claude Code, you can still use the skill content directly — point any capable LLM at `SKILL.md` plus the `references/` directory and ask it to follow the 6-layer prompt structure.

## Usage

The skill fires only on **explicit invocation** — it does NOT auto-trigger on generic render, NB2, Y2K, "our style," or reference-image requests. This is deliberate; undertriggering is the preferred failure mode.

Ways to invoke:

- *"Make me a zero object for the course card."*
- *"Use the zero object prompt generator on this reference image."*
- *"Render this as a zero object."*
- `/zero-object-prompt-generator` (or `/zero-object` as a short form)

Once invoked, the skill handles three input modes:

- **Mode A (named object)**: *"Make a zero object walkie-talkie."*
- **Mode B (concept)**: *"I need a zero object for the empty search state."*
- **Mode C (reference image)**: *"Zero-object this reference."* (attach image)

Output is a single paste-ready NB2 prompt per object.

## What's inside

```
zero-object-prompt-generator/
├── SKILL.md                      # entry point — when to trigger, workflow, failure modes
├── references/
│   ├── rules.md                  # absolute rules + 6-layer prompt structure + closing block
│   ├── modes.md                  # Mode A/B/C input handling
│   ├── face-formula.md           # mouth × eye variation table + decal vs sculpt rule
│   ├── palette.md                # 7 approved tints + multi-panel treatments + saturation
│   ├── jelly-shell.md            # translucent-shell calibration and softening language
│   └── canonical-examples.md     # three full worked prompts (clock, CRT, Rubik's cube)
├── LICENSE                       # CC BY-NC 4.0
└── README.md                     # this file
```

## The 6-layer prompt structure

Every prompt stacks these in order:

1. **Opening** — object type, camera angle, floating on pure white
2. **Creative twist** — what makes it a designer piece (jelly shell is the workhorse)
3. **Per-component material palette** — 5–10 components, each with assigned material, crisp hard boundaries
4. **Electronic touch** — LCD with diegetic text + rubber face button + LED + silkscreen labels
5. **Y2K diegetic detail** — 8–10 elements (model code, spec line, functional labels, decals)
6. **Closing technical block** — material accuracy + surface finish + shadowless/baseless staging + camera + aspect ratio

Full worked examples in [`references/canonical-examples.md`](references/canonical-examples.md).

## Known failure modes the skill defends against

- **"Clearly visible" / "bold interior" language on jelly shells** — renders fully see-through with full PCB exposed
- **Pale / washed / milky tints** — breaks the iMac G3 saturation register
- **Brand names, real or invented** — reads as dominant text anchor
- **External emissions** (laser beams, steam, projected light) on white backgrounds — bleeds off the silhouette
- **Cables exiting the silhouette** — breaks isolation
- **Bases / pedestals / stands / feet** — breaks the floating form
- **Repeating face formula across a set** — reads as template stamp
- **Dark tints on jelly shells** — render near-black; purple on spheres renders metallic

Each is documented with its fix in `SKILL.md` and the relevant reference file.

## License

[CC BY-NC 4.0](LICENSE) — free to use, remix, and share non-commercially with attribution. Commercial use requires permission.

## Credits

Built by Roy (Vishnu) at Zero. Derived from in-house iteration on NB2 prompt engineering for the Zero product's visual language.

If you use or extend this skill, a link back is appreciated.
