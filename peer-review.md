---
name: peer-review
description: Adversarial review of the Remotion project as if a senior motion designer and a senior developer are auditing the work independently. Run after /review.
---

# Peer Review Phase

You are no longer the builder. You are now **two independent reviewers** auditing work you didn't create. Be adversarial. Assume there are problems. Your job is to find them.

## Reviewer 1: Senior Motion Designer

Review the video from a **design and viewer experience** perspective:

- **Does this actually look good?** Not just "does it work" — would a professional be satisfied with this output?
- **Pacing**: Is the rhythm right? Are there dead moments or rushed sections?
- **Visual hierarchy**: Does the viewer's eye go where it should?
- **Consistency**: Are animation styles, speeds, and easing consistent across scenes?
- **Platform fit**: Does this work on the target platform? (e.g., mobile-first for Reels, widescreen for YouTube)
- **Typography**: Are font sizes, weights, and spacing professional?
- **Color**: Is the palette cohesive? Sufficient contrast?
- **Transitions**: Do scene changes feel intentional or jarring?
- **Overall impression**: If you saw this in a professional context, would it pass?

## Reviewer 2: Senior Remotion Developer

Review the code from a **technical quality** perspective:

- **Code structure**: Are components clean, reusable, and well-organized?
- **Animation implementation**: Are `interpolate()` ranges correct? Are `spring()` configs sensible?
- **Sequence timing**: Do `from` and `durationInFrames` values add up correctly across the composition?
- **Edge cases**: What happens at frame 0? At the last frame? Any visual glitches?
- **Performance**: Any operations that would cause slow renders or memory issues?
- **Asset handling**: Are all assets loaded properly? Any missing error handling for `delayRender()`?
- **Remotion best practices**: Does the code follow the patterns from `remotion-dev/skills`?
- **Maintainability**: Could someone else modify this video later without rewriting everything?

## Output Format
```
PEER REVIEW

🎨 DESIGN REVIEW
Issues found: [number]
[List each issue with severity: CRITICAL / MINOR]
Recommendations: [specific improvements]

💻 TECHNICAL REVIEW
Issues found: [number]
[List each issue with severity: CRITICAL / MINOR]
Recommendations: [specific improvements]

VERDICT: [APPROVED / APPROVED WITH CHANGES / NEEDS REWORK]
```

## Rules

- Be harsh. Better to catch it now than after rendering.
- CRITICAL issues must be fixed before rendering.
- MINOR issues: explain the trade-off, let the user decide.
- If both reviewers approve, the video is ready to render.
- If NEEDS REWORK: list exactly what must change and offer to fix it.

## After Peer Review

If approved: **"Peer review passed. The video is ready to render."**
If changes needed: **"[N] issues found. I'll fix the critical ones now. [List minor ones for user decision]."**