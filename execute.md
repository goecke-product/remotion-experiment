---
name: execute
description: Build the Remotion video code scene by scene following the approved plan. Only run after /plan is approved.
---

# Execution Phase

You are entering the execution phase. The plan is approved. Now build it.

## Process

1. **Load Remotion skills first**: Read the relevant rule files from the Remotion skills (`remotion-dev/skills`) before writing code:
   - Always: `rules/animations.md`, `rules/sequencing.md`, `rules/compositions.md`
   - If assets: `rules/assets.md`, `rules/images.md`
   - If audio: `rules/audio.md`
   - If video clips: `rules/assets.md`
   - If subtitles: `rules/subtitles.md`
   - If charts: `rules/charts.md`
   - If 3D: `rules/3d.md`
   - If fonts: `rules/fonts.md`
   - If audio visualization: `rules/audio-visualization.md`

2. **Build scene by scene**: Implement one scene at a time, following the approved plan exactly. Do not deviate from the plan without asking.

3. **After each scene**: Briefly tell the user what was built and what's next. No lengthy explanations — just confirmation.

4. **Handle deviations**: If something from the plan turns out harder than expected during implementation:
   - Stop
   - Explain the issue in plain language
   - Propose a concrete alternative
   - Get approval before continuing

## Code Standards

- Clean, well-structured components — one per scene
- Use `interpolate()` and `spring()` for animations
- Use `<Sequence>` for timing/ordering
- Use `<AbsoluteFill>` for layout
- Use `<Img>` from `remotion` for images (not HTML `<img>`)
- Use `<OffthreadVideo>` for video embeds
- Use `staticFile()` for assets in `public/`
- Separate content/data from visual components where possible
- Keep individual components under 150 lines

## Rules

- Follow the plan. If the plan says "fade in over 1 second", implement exactly that.
- Don't add effects or elements not in the plan
- Don't over-engineer. Simple and working beats clever and fragile.
- If you need an asset that doesn't exist, stop and ask — don't use placeholders without telling the user
- Ensure the video can render without errors before moving to the next scene

## Output

After all scenes are built: **"Build complete. Run `/review` to check for issues."**