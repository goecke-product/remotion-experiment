---
name: plan
description: Create a concrete scene-by-scene video blueprint with timing, animations, and asset requirements. Only run after /explore.
---

# Planning Phase

You are entering the planning phase. The exploration is done. Now create a **concrete, buildable blueprint** that the user can approve before any code is written.

## What to produce

Create a scene-by-scene plan using this structure:
```
VIDEO PLAN: [Title]
Resolution: [e.g. 1920x1080] | FPS: [e.g. 30] | Duration: [e.g. 25s] | Format: [e.g. MP4]

SCENE 1: [Name] (0:00 – 0:03)
- Visual: [What's on screen]
- Animation: [How things move]
- Audio: [Music/SFX/silence]
- Assets needed: [List any files required]

SCENE 2: [Name] (0:03 – 0:08)
...

ASSETS CHECKLIST:
☐ [Asset 1 — status: provided / needed / to be created]
☐ [Asset 2]
...

DEPENDENCIES:
- [Anything that needs external tools: voiceover, image generation, etc.]
```

## Rules

- Every scene must have a concrete duration in seconds
- Animations described in visual language, not code ("logo fades in over 1 second, then scales up slightly with a bounce")
- Flag any scene that pushes Remotion's limits (⚠️ mark it)
- Flag missing assets — don't assume things exist
- Keep total complexity manageable. If the plan has more than 8-10 scenes, challenge whether it's needed
- Transitions between scenes must be specified
- If audio is involved, specify sync points

## Quality checks before presenting the plan

- Does total duration match the user's target?
- Are all assets accounted for?
- Is any scene overly complex for Remotion? Simplify or flag it.
- Is the pacing right? (not too fast for the audience)

## Output

Present the full plan and ask: **"Does this plan match what you have in mind? I'll adjust anything before we build."**

Only after explicit approval: **"Plan approved. Run `/execute` to start building."**