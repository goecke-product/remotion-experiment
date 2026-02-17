# remotion-experiment
How I Built a Book Trailer With Claude Code and Remotion (Without Writing Code) This document explains the setup behind my LinkedIn post about building a video trailer for our textbook Produktmanagement -- Kontinuierliche Innovation digitaler Produkte (Springer Gabler, 2025).

**LinkedIn post:** https://www.linkedin.com/posts/lutzgoecke_remotion-claudecode-productmanagement-activity-7429164455277719552-8mCD

---

## What is this?

These files turn Claude Code into a structured video production assistant. Claude Code is Anthropic's CLI tool that lets you interact with Claude directly in your terminal. Remotion is an open-source framework that generates videos from React code.

The combination means: you describe what you want in plain language, Claude writes the React/TypeScript code, and Remotion renders it into a video file.

I cannot write code. These files made it possible for me to produce a complete book trailer in a single session.

## What you get

Six files that work together as a system:

| File | What it does |
| CLAUDE.md | The main configuration. Defines Claude's role, rules, and what Remotion can and cannot do. |
| explore.md | The /explore command. For understanding your video idea before planning. |
| plan.md | The /plan command. Creates a scene-by-scene blueprint with timing. |
| execute.md | The /execute command. Builds the actual video code. |
| review.md | The /review command. Self-checks the implementation. |
| peer-review.md | The /peer-review command. Adversarial quality review. |

## How the workflow works

Every video project follows a strict pipeline. You trigger each phase manually - Claude never jumps ahead without your go-ahead.

```
/explore -> /plan -> /execute -> /review -> /peer-review
```

**Phase 1: Explore** -- You describe your video idea. Claude asks questions, assesses what Remotion can handle, and pushes back on things that will not work. No coding happens here.

**Phase 2: Plan** -- Claude creates a concrete blueprint: scene-by-scene, with durations, animations described in visual language, and an asset checklist. You approve or adjust before anything gets built.

**Phase 3: Execute** -- Claude builds the video code one scene at a time, following the approved plan. If something turns out harder than expected, Claude stops and proposes an alternative.

**Phase 4: Review** -- Claude steps back from builder mode and checks the implementation against the plan: timing, visual quality, technical correctness, audio sync.

**Phase 5: Peer Review** -- Two simulated reviewers audit the work: a senior motion designer (design quality, pacing, consistency) and a senior Remotion developer (code structure, performance, edge cases).

## Why this structure matters

Without these files, you get generic AI assistance. With them, you get a co-worker who:

- Tells you upfront what Remotion *cannot* do (no AI-generated video, no motion tracking, no color grading) instead of letting you waste time
- Uses visual language ("the text slides in from the left") instead of code jargon
- Follows a plan instead of improvising
- Catches problems through two separate review phases

## Remotion

Remotion is the engine underneath all of this. It is an open-source framework that lets you create videos programmatically using React. You write (or in my case: let Claude write) React components, and Remotion renders them frame by frame into an MP4 or WebM file.

You need a Remotion project before any of the other files do anything. To create one:

```
bun create video
```

This scaffolds a working project with a preview server, a sample composition, and the rendering pipeline. You need Node.js (v18+) and either bun or npm installed. Remotion also requires Chrome or Chromium for rendering.

Full docs and installation guide: https://www.remotion.dev/docs/

## Remotion Best Practices Skill

On top of my own files, I used the official **Remotion Best Practices Skill** by the Remotion team. This is a curated set of 31 rule files that teach Claude Code how Remotion actually works -- animations, sequencing, audio, video, fonts, transitions, 3D, and more.

Without it, Claude guesses. With it, Claude knows the correct API patterns.

Install it in your Remotion project directory:

```
npx skills add remotion-dev/skills
```

That is it. Claude Code picks up the rules automatically. You can also browse the skill at https://skills.sh/remotion-dev/skills/remotion-best-practices

## How to set it up

1. Install Claude Code (https://docs.anthropic.com/en/docs/claude-code/overview)
2. Set up a Remotion project (https://www.remotion.dev/docs/)
3. Install the Remotion Best Practices Skill: `npx skills add remotion-dev/skills`
4. Place CLAUDE.md in the root of your Remotion project directory (or in a `.claude/` folder)
5. Place the five command files (explore.md, plan.md, execute.md, review.md, peer-review.md) in `.claude/commands/`
6. Open a terminal in your project directory and start Claude Code
7. Type `/explore` and describe your video idea

## What I built with this

For the book trailer, my ingredients were:

- Stock footage of a bookstore (from Pexels)
- Stock audio track
- A screen recording of me scrolling through the book
- A screenshot of the book cover
- Endorsement quotes from Petra Wille, Julia Boesch, and Steffen Wicker

One session produced: a bookstore opening clip, animated cover reveal, page scroll in timelapse, endorsement quote animations, and a closing call-to-action -- with transitions, background music, and proper typography.

## Credits

- **Kristian Fagerlie** - His video on Remotion + Claude Code put me onto this combination. https://www.linkedin.com/in/kristian-fagerlie/
- **Zevi Arnovitz** - His approach to shipping products without writing code inspired the project setup.
- **Remotion** - Open-source framework by Jonny Burger. https://www.remotion.dev/

## About the book

**Produktmanagement - Kontinuierliche Innovation digitaler Produkte**
Lutz Göcke & Michael Schultheiss
Springer Gabler, 2025

https://link.springer.com/book/9783658491093

---

Questions? Reach out on LinkedIn: https://www.linkedin.com/in/lutzgoecke/
