---
name: review
description: Self-review the Remotion implementation for bugs, timing issues, visual quality, and plan compliance. Only run after /execute.
---

# Review Phase

You are entering the review phase. Step back from builder mode and become a **critical reviewer**. Your goal is to catch every issue before the user sees the output.

## Review Checklist

### 1. Plan Compliance
- Does every scene match the approved plan?
- Are durations correct?
- Are all specified animations implemented?
- Are any elements missing or added without approval?

### 2. Technical Correctness
- Does the composition render without errors?
- Are all `delayRender()` / `continueRender()` calls properly paired?
- Are all assets referenced correctly via `staticFile()`?
- Are there any missing imports?
- Is `fps` consistent across compositions?
- Are `<Sequence>` from/durationInFrames values correct?
- Do animations use proper easing (no linear motion where spring was intended)?

### 3. Timing & Pacing
- Do elements appear and disappear at the right moments?
- Is there enough hold time for text to be read? (rule of thumb: 3 seconds minimum for a sentence)
- Are transitions smooth, not abrupt?
- Does total duration match the target?

### 4. Visual Quality
- Are elements properly centered/aligned?
- Is text readable at the target resolution?
- Are colors consistent with brand guidelines?
- Is there enough contrast for readability?
- Are font sizes appropriate for the platform (mobile vs desktop)?

### 5. Audio (if applicable)
- Is audio properly synced?
- Are volume levels reasonable?
- Does audio start/end at the right times?
- Are there any gaps or overlaps?

### 6. Performance
- Any GPU-heavy effects that could cause slow rendering? (blur, box-shadow, gradients)
- Any unnecessary re-renders?
- Are video/image assets optimized for the target resolution?

## Output Format
```
REVIEW RESULTS

✅ Passed: [list what's correct]
⚠️ Warnings: [non-critical issues]
❌ Issues: [must-fix problems]

FIXES APPLIED: [list changes made]
FIXES PENDING: [anything that needs user input]
```

Fix all ❌ issues immediately. For ⚠️ warnings, explain the trade-off and let the user decide.

After review: **"Review complete. Run `/peer-review` for a second opinion, or render the video."**