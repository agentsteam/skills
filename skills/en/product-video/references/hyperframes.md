# HyperFrames production reference

Use for every product-video composition: mandatory brand treatment, intro/outro, chapter cards, callouts, effects, captions, and final render. Cursorful + Chrome recording/autozoom is the default input route; reuse a confirmed workflow when supplied. Researched 2026-10-13; no renderer version was executed during research. Check installed CLI before production.

## 1. Choose input and visual contract

- **Polished Cursorful/OpenScreen export:** preserve baked camera movement, cursor, clicks, framing, and timing. Compose surrounding branding and narration; avoid a second automatic zoom pass. Log which effects are already baked in.
- **Raw capture:** require an explicit cinematic camera plan before final composition. A raw Playwright video alone does not satisfy the requested visual quality. Derive camera moves from recorded actions/target boxes, then verify a representative moving render.
- **Full tutorial:** use general composition patterns (`general-video`) with chapters and independently retryable scenes. The upstream product-launch workflow targets short promos; it is not a long-tutorial limit of the renderer.
- **Single-feature video:** reuse one verified scenario and its result; choose 16:9 or intentionally composed 9:16. Use `motion-graphics` knowledge for brief logo stings, titles, and overlays, not as the main tutorial workflow. [Workflow catalog][workflows]
- Narration provider remains ElevenLabs. Read [narration-and-timing.md](narration-and-timing.md) for synthesis/alignment and scene scheduling. HyperFrames receives local audio and timing files.

## 2. Pin runtime and verify CLI

Use Node.js 22+, FFmpeg, FFprobe, and HyperFrames' pinned Chrome. Native Windows rendering is covered by upstream CI; this does not prove the current host works. Docker is optional for local rendering. Apache-2.0 covers HyperFrames itself; assets/cloud services have separate terms. [Environment][doctor] · [Windows CI][windows] · [License][license]

On first setup, resolve a release, run a short real-footage smoke test, then pin that successful version and record it. Reuse the project's exact dependency/lockfile thereafter. Avoid unattended `latest` upgrades.

PowerShell bootstrap template: replace `REPLACE_WITH_TESTED_VERSION` before execution; run from the video's own work directory.

```powershell
$hfPackage = 'hyperframes@REPLACE_WITH_TESTED_VERSION'
$env:HYPERFRAMES_NO_TELEMETRY = '1'
$env:HYPERFRAMES_SKIP_SKILLS = '1'
npx --yes $hfPackage --help
npx --yes $hfPackage init --help
npx --yes $hfPackage check --help
npx --yes $hfPackage render --help
npx --yes $hfPackage doctor --json
```

`doctor` always exits zero: inspect the JSON checks for Node, FFmpeg, FFprobe, Chrome, available disk/memory. Optional local voice/Docker failures need not block this local ElevenLabs workflow. If Chrome is missing, use `browser ensure`. For existing Windows binaries set `HYPERFRAMES_FFMPEG_PATH` and `HYPERFRAMES_FFPROBE_PATH` to their absolute `.exe` paths. [Environment][doctor]

Proceed when required checks pass and the pinned CLI supports the flags below. If flags differ, read that version's help/docs and record the corrected command; do not guess aliases.

## 3. Scaffold, brand, and assets

```powershell
npx --yes $hfPackage init ./composition --non-interactive --resolution landscape --skip-transcribe
```

`landscape` = 1920×1080; `portrait` = 1080×1920; 4K presets exist. `--skip-transcribe` avoids duplicate speech processing when audio/timestamps already exist. Upstream currently ignores `--skip-skills`; the environment opt-out above prevents automatic skill refresh in controlled runs. [Scaffolding][init]

Use local footage, logo variants, licensed fonts, cursor artwork, and optional licensed music. Freeze brand colors, typography, spacing, frame/shadow, intro/outro, and callout/caption styles in the project. Fonts need shipped files plus `@font-face`; a font installed on the author's machine is insufficient. [Core][core]

Search existing effects with `catalog --query "<English visual intent>" --json`; install only the chosen item using `add <item> --no-clipboard`. Blocks are sub-compositions; components are snippets. Read installed code before wiring it. Keep chosen assets/components versioned; `add` requires network even when catalog metadata is cached. [Registry][registry]

`capture URL` creates screenshot/asset scenes, not evidence of a completed interactive product workflow. Use it only for reference/brand assets. Actual demonstrated actions must come from the capture stage. [Scaffolding][init]

## 4. Author deterministic timeline

- Standalone `index.html`: root directly in `<body>`, with `data-composition-id`, `data-width`, `data-height`, and finite `data-duration`; root CSS width/height 100%. Sub-composition roots use `<template>`. [Core][core]
- Use seconds throughout HyperFrames. Write final root duration before rendering: static `data-duration` is compiled before script/variable evaluation. Clip windows are `[start, start + duration)`; finish exits before the final boundary. `data-track-index` is a Studio lane; use CSS for stacking. [Attributes][attributes]
- Build exactly one completed `gsap.timeline({paused:true})` per composition; register it as `window.__timelines[compositionId]` only after initialization/tweens finish. HyperFrames seeks it. Dynamic source data becomes a fixed scene schedule before render. [Determinism][determinism]
- Keep render state time-seekable: local assets, seeded randomness if needed, finite loops, transform/opacity motion. Render-critical state must not depend on clocks, input events, live network requests, or `tl.play()`. Animate inner children; framework owns timed-clip visibility. [Determinism][determinism]
- Each sub-composition uses scene-local media/tween times. Root time = sum of ancestor scene starts + local time. Match host ID, child composition ID, and timeline registry key. Put sub-composition CSS/JS inside its template. Unique IDs across assembled output. [Sub-compositions][subcomps]

## 5. Place footage and narration

Use muted video for UI capture and a separate identified audio element for ElevenLabs narration. Every media element needs a unique ID; missing audio IDs can silently omit audio. HyperFrames owns media play/pause/seek. Use `data-media-start` for source trims. A timed video must not have an ordinary timed ancestor; keep wrapper untimed or use a proper sub-composition. [Media][media]

Schedule narration from actual probed duration. Include useful lead-in and result holds; retain time needed to understand the action. Keep source-clock → edited-scene-clock → final-video-clock mappings in the scene manifest. Cuts and speed changes invalidate dependent event/caption/camera times. [Editing recipes][edits]

For optional music, author explicit `data-automation` volume lanes on clip-local time for fades/ducking. One volume automation mechanism per element; an existing lane wins over a competing timeline tween. Verify narration has no duplicate recorded voice underneath. [Editing recipes][edits]

## 6. Cinematic camera branch for raw footage

This is custom camera authoring, not an undocumented HyperFrames autozoom feature. Supported primitives include scale/pan and clip-path reframing on inner wrappers; source time and sound remain unchanged. [Editing recipes][edits]

1. Read action sidecar: source time, viewport, cursor position/path, clicked target bounds, expected result, and narrative purpose. Group related actions into shots.
2. Start with context; smoothly focus target; hold through action/result; return wide or move to the next meaningful region. Prioritize readable labels and stable holds over frequent effects.
3. Convert source pixels through initial fit/letterbox mapping. Clamp camera position/scale to keep context visible and prevent blank edges. Recalculate for each aspect ratio.
4. Transform footage and cursor/click highlights together inside an untimed camera wrapper. Clip them with the screen frame. Keep logo, captions, chapter titles, and fixed callouts outside camera transforms.
5. Generate paused GSAP keyframes from the finalized event schedule. After retiming footage, regenerate dependent camera/cursor positions from the mapping.
6. Render a short comparison including zoom entrance, click, menu/result, hold, and return. Accept only if cursor alignment, text sharpness, motion, framing, and narration synchronization satisfy the cinematic target.

Once this camera pass is baked into an export, mark it polished and follow the first input branch. Do not promise Cursorful parity until the rendered comparison demonstrates it.

## 7. Captions and shorts

Convert ElevenLabs alignment to `{id,text,start,end}` word records in seconds, then apply scene/final offsets. HyperFrames supports normalized word arrays; SRT/VTT are phrase timing only. Validate words, product names, numbers, monotonic times, and complete spoken coverage. [Transcript formats][transcripts]

Use one caption group at a time, bounded by actual speech. Keep text legible against video and outside taught controls. Reusable caption components are available through catalog discovery; verify group exits and bundled fonts. The upstream ElevenLabs “no timestamps” claim is not authoritative for provider capabilities; use current ElevenLabs docs. [Captions][captions]

Portrait requires a new layout decision: focus region, readable UI scale, contextual navigation, caption band, brand placement. Reflow intro/outro and annotations; inspect menus near crop boundaries. Prefer recapture at a suitable viewport when reframing makes the task incomprehensible. Do not stretch 16:9 footage into 9:16.

## 8. Long-video continuity and QA

Partition long tutorials into semantic scenes with stable IDs, local times, shared output settings, and reusable branding. Cache scene inputs; rerender only changed scenes. Keep transition handles and caption/audio offsets explicit. Use visually restrained chapter transitions; preserve continuity of UI state and narration. Prefer source-level assembly/final encode over repeated lossy intermediates.

Run `lint` during initial authoring. Final gate uses `check` for lint/runtime/layout/motion/contrast; `validate`, `inspect`, and `layout` are deprecated. Where supported by pinned version:

```powershell
npx --yes $hfPackage check ./composition --json --snapshots --at-transitions
npx --yes $hfPackage render ./composition --format mp4 --fps 30 --quality delivery --output ./final.mp4
```

Inspect JSON `browserSkipped`: skipped browser audits are not passed audits. Read findings and actual PNGs; use scene midpoints plus transition/zoom extrema. Current qualities are `draft`, `looks`, `delivery`; older `standard`/`high` aliases exist. `--docker` is the documented reproducibility option, not required for Windows. [Checks][checks] · [Rendering][render]

Automation authorization covers composing, checking, and rendering within the agreed brief. Do not add upstream per-render approval pauses, skill auto-upgrades, feedback submissions, or telemetry. Use preview as optional review surface when requested, not an unattended-production gate.

Open/review actual final MP4, not preview alone. Verify all scenes contain real footage, audio is complete, joins/captions/cursors remain synchronized, and portrait/landscape controls are readable. Read [delivery.md](delivery.md) for final media checks and publishing rules. If verification fails, repair the affected scene; report unresolved blockers without claiming completed production.

[workflows]: https://github.com/heygen-com/hyperframes/blob/main/README.md
[doctor]: https://github.com/heygen-com/hyperframes/blob/main/skills/hyperframes-cli/references/doctor-browser.md
[windows]: https://github.com/heygen-com/hyperframes/blob/main/.github/workflows/windows-render.yml
[license]: https://github.com/heygen-com/hyperframes/blob/main/LICENSE
[init]: https://github.com/heygen-com/hyperframes/blob/main/skills/hyperframes-cli/references/init-and-scaffold.md
[core]: https://github.com/heygen-com/hyperframes/blob/main/skills/hyperframes-core/SKILL.md
[registry]: https://github.com/heygen-com/hyperframes/blob/main/skills/hyperframes-registry/SKILL.md
[attributes]: https://github.com/heygen-com/hyperframes/blob/main/skills/hyperframes-core/references/data-attributes.md
[determinism]: https://github.com/heygen-com/hyperframes/blob/main/skills/hyperframes-core/references/determinism-rules.md
[subcomps]: https://github.com/heygen-com/hyperframes/blob/main/skills/hyperframes-core/references/sub-compositions.md
[media]: https://github.com/heygen-com/hyperframes/blob/main/skills/hyperframes-core/references/variables-and-media.md
[edits]: https://github.com/heygen-com/hyperframes/blob/main/skills/hyperframes-core/references/creator-editing-recipes.md
[transcripts]: https://github.com/heygen-com/hyperframes/blob/main/skills/media-use/audio/references/captions/transcript-handling.md
[captions]: https://github.com/heygen-com/hyperframes/blob/main/skills/media-use/audio/references/captions/authoring.md
[checks]: https://github.com/heygen-com/hyperframes/blob/main/skills/hyperframes-cli/references/lint-validate-inspect.md
[render]: https://github.com/heygen-com/hyperframes/blob/main/skills/hyperframes-cli/references/preview-render.md
