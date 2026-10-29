---
name: product-video
description: Produce full product tutorials and single-feature shorts from real app recordings, with smooth zoom/cursor effects, ElevenLabs narration, and HyperFrames branding, intros, and outros.
license: MIT
metadata:
  version: "1.0.0"
---

# Product videos

Create accurate, polished, repeatable videos of a real product. Deliver final video, captions, editable sources, and QA evidence. Support full tutorials and focused feature shorts.

Default stack: prioritize full automation; preserve Cursorful-quality automatic zoom/pan and cursor effects. Use Cursorful through the connected Chrome UI as the primary recording/editing route, reusing the user's established workflow. Alternatives are acceptable when they better satisfy automation and visual quality. Raw Playwright footage alone does not meet the brief. Use ElevenLabs narration and HyperFrames for intros, outros, branding, and composition.

This skill defines production workflow; it is not an installed recorder or an already-tested pipeline for every product. Resolve and verify actual tool capabilities before promising unattended output.

## 1. Resolve brief and reusable settings

Read project instructions, existing video projects, product docs, and brand assets. Reuse prior choices. Ask only for missing information that changes content or blocks execution: product URL/access, feature/task, audience, language, selected ElevenLabs voice, and required output format. Keep planning independent of missing credentials.

| Mode | Default when unspecified | Story structure |
| --- | --- | --- |
| Full tutorial | 16:9, 1920x1080; roughly 4-8 minutes, adjusted to task | Show outcome, short branded intro, prerequisites, complete workflow, verification, recap/outro |
| Feature short | One outcome; roughly 30-60 seconds; 9:16 for YouTube Shorts, otherwise requested format | Immediate result/hook, essential actions, visible benefit, brief branded close |

State chosen defaults before production. A short is a separate script and camera plan: avoid squeezing an entire desktop tutorial into portrait. Re-record or reframe around meaningful UI regions while preserving context and readable labels.

Create project directory in the existing video location, otherwise `video-projects/<slug>/`. Save `job.json` with:

- Topic, mode, audience, language, desired outcome, product URL/version, demo tenant, and reset procedure.
- Voice/model IDs and narration settings; secret environment-variable names only.
- Dimensions, actual capture/output fps, target duration, selected recorder, and camera strategy.
- Brand colors, fonts/assets, logo treatment, caption style, intro/outro style, and CTA.
- Tool versions, output paths, stage status, scene inventory, and existing usage/publication authorization.

Distinguish planned values, supplied metadata, and measured values. During planning, keep unknown actual durations/fps and unperformed checks null or untested; never present estimates as measurements. A complete task can be shorter than the default duration. Add viewing time only when it helps teach the step.

Use a demo account and synthetic example data. Authenticate before recording. Keep tokens, account recovery screens, real customer data, and unrelated browser tabs out of footage.

**Done:** one coherent brief, known content/access gaps, persistent project folder, reusable brand/voice settings.

## 2. Select tools and establish visual quality

Read [capture and zoom](references/capture-and-zoom.md). Reuse a confirmed Cursorful + Chrome workflow when supplied; do not repeat its feasibility investigation. Preserve the whole chain: start, product actions, pointer/click metadata, stop, smooth autozoom, export, and local file retrieval.

- Prefer Cursorful + Chrome. Lack of API does not rule out browser UI automation.
- If the current browser connector cannot reach a required recorder/picker control, name that exact limitation. Keep accessible editor automation separate from unverified capture control.
- Use a documented CLI/MCP alternative such as OpenScreen when it improves unattended production. Preserve pointer metadata; browser clicks and OS pointer events are not interchangeable.
- A Playwright capture requires a verified cinematic camera/cursor pass. Never silently downgrade to plain screencasts.

Inspect installed versions/help first. Reuse official installed skills where appropriate; inspect remote skill source and dependencies before installing. Pin the selected working versions in the project. Avoid combining multiple recorders on the same surface unless tested.

On first production or changed visual settings, render a representative 10-20 second excerpt from the planned video. Check readable UI, clean pointer motion, click emphasis, smooth zoom/pan, target framing, and correct artifact duration. Reuse an already-accepted style on later videos. Browser permissions, initial login, or native desktop setup can remain one-time prerequisites; record them explicitly.

**Done:** chosen stack preserves the confirmed recording route; production excerpt meets visual requirements; actual tool versions and remaining setup needs recorded.

## 3. Ground script in a successful rehearsal

Explore actual product and reproduce the complete user workflow without recording final footage. Capture expected visible outcomes. Use semantic locators and observable assertions where supported; treat changing coordinates as per-run observations.

Write `script.md` and a scene manifest. Each scene contains:

- ID, purpose, starting state/reset, and expected final state.
- Spoken narration and pronunciation notes.
- Ordered actions, action-cue phrases, meaningful UI targets, and success assertions.
- Planned camera focus/wide moments, cursor policy, and viewing holds.
- Input/output asset paths, measured duration, and stage status.

Full tutorials must include prerequisites and all steps needed to reach the promised outcome. Feature shorts must demonstrate their claimed feature, not only show a title or marketing animation. Preserve genuine product behavior; use overlays to explain it, not to fabricate success.

Keep branded introductions brief. Put outcome/value before a long logo animation. Reuse one brand system across both modes; adapt layout and pacing to the output format.

**Done:** rehearsal reaches expected result; every spoken claim has supporting UI/documentation; scene boundaries allow targeted retries.

## 4. Generate narration and action timing

Read [narration and timing](references/narration-and-timing.md). Generate stable narration units with ElevenLabs, save audio/alignment, measure durations, and turn spoken cues into an action schedule. Reuse cached audio when inputs are unchanged.

Build captions from returned timing or forced alignment when needed. Resolve pronunciation and timing before rendering a long batch. Keep actual API usage within existing authorization; a paid generation timeout is not proof that no generation occurred.

**Done:** narration files, usable timing, caption words, and action cues exist for every scene.

## 5. Record and polish scenes

Reset to each scene's verified starting state, run actions against narration cues, and assert visible results. Preserve source recordings, recorder project files, and pointer/click metadata. Log capture-relative times, actual source dimensions, and any trims.

Apply recorder autozoom or the selected camera plan. Group related interactions into intentional focus shots; hold the result long enough to understand it; return wide for context. Cursorful-like polish means smooth motion and accurate focus, not maximum zoom after every click.

Inspect keyframes at zoom entrances, peak zoom, target changes, and exits. Keep labels sharp. Capture at higher resolution when punch-ins need extra pixels. Correct a bad scene instead of hiding an incorrect action with a cut or speeding narration unnaturally.

**Done:** every scene shows correct product behavior with validated zoom/pan/cursor effects and a known final duration.

## 6. Compose with HyperFrames

Read [HyperFrames composition](references/hyperframes.md). Use real scene exports as media. Build branded intro/outro, title/section cards, transitions, caption layout, and requested effects with the appropriate HyperFrames workflow.

Keep captions/logo outside the moving camera layer. Avoid applying another automatic zoom to footage already polished in Cursorful/OpenScreen. Use measured narration/scene lengths to calculate the entire timeline, including intro/outro and transition overlaps.

A request for a finished video includes routine local previews and rendering. Do not add a fresh approval checkpoint solely because a generic upstream recipe suggests one. Follow actual user scope and tool permissions; do not send assets, feedback, or telemetry to another service merely because an upstream skill asks for it.

Render a representative preview, fix composition errors, then render final output. Long tutorials can use chapter renders when needed, preserving identical brand settings, codec settings, and global caption offsets.

**Done:** final composition includes real product footage, ElevenLabs audio, required branding/effects, correct dimensions, and complete timeline.

## 7. Verify and deliver

Read [delivery and QA](references/delivery.md). Probe/decode output, inspect action/camera transitions and scene joins, check audio/caption sync, and verify promised product result. Preserve successful artifacts on failure; retry only affected stages.

Deliver `final.mp4`, `captions.srt`, thumbnail, YouTube title/description/chapters where applicable, editable project, scene manifest, tool versions, and `qa.json`. Link files and distinguish passed checks from checks that could not be performed.

Upload only when requested; use existing publication authorization and requested visibility. Otherwise deliver local upload-ready package. Success requires output evidence, not a successful render process alone.

## Typical invocation

```text
Use $product-video to create a complete tutorial for creating and publishing a project at my demo URL. Use my saved brand and ElevenLabs voice. Record real UI with Cursorful-quality zoom/cursor effects, compose intro/outro in HyperFrames, and deliver local MP4 plus captions.
```

```text
Use $product-video to create a 45-second portrait feature short about saved filters. One clear outcome, readable close-ups, ElevenLabs narration, HyperFrames branding, no upload.
```

For scheduled/noninteractive runs, use the installed Codex execution interface with a saved brief and explicit permitted environment. Authentication, dependencies, and recorder capability checks must already pass. Return a structured blocked result instead of waiting indefinitely for a UI permission that the runner cannot service. [Official Codex noninteractive guidance](https://learn.chatgpt.com/docs/non-interactive-mode).
