# Capture, cursor and camera

Checked 2026-10-13. Cursorful + Chrome is the primary route. Preserve its automatic zoom/pan aesthetic. Reuse a user-confirmed workflow without another capability audit. Check installed capabilities when choosing an alternative.

## Choose the route

| Route | Use when | Boundary |
| --- | --- | --- |
| Cursorful through Chrome | Default: existing license, preferred camera style | UI automation; public CLI/API not verified |
| OpenScreen | User prefers its appearance or explicit recording/rendering commands | Windows desktop required; pointer bridge depends on installed version |
| Cap | Its Studio editor/presets suit the job | CLI is documented; automatic zoom generation from CLI needs confirmation |
| Browser capture + authored camera | Repeatable automation outweighs native editor convenience | Camera and cursor compositor must be implemented; raw capture alone fails the brief |

Capture is only one stage. Every accepted output needs intentional zoom/pan, clean cursor movement, readable focal targets and timing aligned with narration. A technically valid MP4 is insufficient.

## Cursorful through Chrome — primary

1. Use the user's Chrome profile/session with Cursorful available. Discover current tabs and operate observed controls through the available browser tool. Keep the product and editor distinguishable by title/URL.
2. Follow the user's established start-recording workflow. Select only the intended demo surface. Perform storyboard actions, leave time for results to settle, then stop using the available recorder control.
3. In Cursorful, inspect generated zooms. Adjust focal targets, timeline, aspect ratio, cursor, background and crop using exposed editor controls. Keep labels and resulting state visible through each move.
4. Export to the run directory; wait for actual completion and verify the downloaded file. Preserve the editable project using supported save/export controls when available. The presence of an Export button is not an export result.
5. Review the first production preview for style, hover states, cursor alignment, legibility and narration timing. Correct the take/editor and re-export where needed. Do not turn this into another proof that Cursorful can be controlled.

Use controls exposed by the current browser connection. If an actual production action is unavailable, report that exact action and finish independent preparation. Respect blocked surfaces; tool capabilities differ between sessions.

Cursorful's extension tracks browser interactions; its desktop app has richer separately recorded cursor effects. Its FAQ describes autozoom triggered by two clicks within three seconds. For representative footage include real nearby actions, not meaningless clicks added solely to trigger a zoom. Arbitrary imported video may need manual zoom placement. [Product and FAQ](https://cursorful.com/), [extension workflow](https://cursorful.com/welcome), [editor](https://cursorful.com/editor).

No public supported CLI, SDK, project schema or unattended export API was verified. This is not evidence that Chrome UI automation is impossible. Never invent flags, `.crsrfl` internals or private endpoint contracts.

## OpenScreen — explicit cinematic automation

Use the maintained [getopenscreen repository](https://github.com/getopenscreen/openscreen), not an archived original or similarly named fork. [v2.0.0](https://github.com/getopenscreen/openscreen/releases/tag/v2.0.0) is a published Windows release. Record the installed version and executable path; CLI/project format can change. Inspect help and actual tools before selecting a workflow.

### CLI with actual pointer input

The [version-pinned CLI](https://github.com/getopenscreen/openscreen/blob/v2.0.0/website/docs/cli.md) documents these shapes; substitute the discovered executable and absolute run paths:

```text
Openscreen.exe sources --json
Openscreen.exe record --window "Product Demo" --duration 20 --project demo.openscreen --cursor editable-overlay --json
Openscreen.exe export demo.openscreen -o demo.mp4 --auto-zoom --quality good --audio voice.mp3 --audio-mode replace --json
```

- Select a unique source title. Start interactions only once recording is active; use an independent process/session so capture does not block product control.
- Native capture needs a real Windows desktop. Its WGC helper requires Windows 10 build 19041+; missing helper can cause browser capture fallback. Treat actual prompts as runtime constraints.
- A real pointer driver can supply captured cursor/click telemetry. Playwright/CDP clicks do **not** move the OS pointer. Do not choose this path for browser automation unless a supported metadata bridge supplies the cursor.
- Check exit status and completion result. Check actual `.cursor.json` contents; a returned path can refer to a missing file. Preserve source, telemetry and project together.
- Stop gracefully using duration, stdin `stop`, or Ctrl+C. Force-killing skips finalization. CLI H.264 export is 60 fps; normalize later only if required.
- `--auto-zoom` uses the editor planner and preserves existing zooms. External narration can replace captured audio. The built-in captions command reads captured audio, so it will not caption narration added only during export. [Shared CLI contract](https://github.com/getopenscreen/openscreen/blob/v2.0.0/src/lib/cliContracts.ts).

### MCP with browser-driven pointer track — version gated

The official [demo skill on main](https://github.com/getopenscreen/openscreen/blob/main/skills/openscreen-demo/SKILL.md) and [media tool source](https://github.com/getopenscreen/openscreen/blob/main/electron/mcp/media-tools.ts) document this integration. Those files were unavailable at the v2.0.0 tag during research. Do not promise the latest installed release includes it.

1. Require installed `help` to list `mcp`; require loaded `startRecording`, `stopRecording`, `setPointerTrack`, `exportVideo` and `getFrames` tools. If absent, use a supported route; do not silently install an unreleased build.
2. If setup is needed and authorized, the documented Codex server shape is `codex mcp add openscreen -- "<executable>" mcp`. Follow the current Codex environment's mechanism for loading newly configured tools.
3. Choose the source and start capture. Log each browser action at execution time, with epoch milliseconds and its target position. Include hover/move events as well as clicks when those states matter.
4. Stop capture. Preserve `projectId`, `checkpointId`, `videoPath`, and `recordingStartedAt`. Pass pointer events to `setPointerTrack` using its installed schema.
5. Keep the **same MCP server process** alive: the source stores recording start times in memory. The bridge accepts that server's own stopped takes; imported video or a server restart is not equivalent.
6. Read the project before editing. Add camera emphasis and callouts, then export and inspect frames. MCP export's documented schema does not include narration audio; compose narration afterward or use a separately verified CLI project export route.

Current main-source request shape, reference only:

```json
{"projectId":"<returned-id>","events":[{"at":0,"x":0.5,"y":0.4,"click":true}]}
```

Replace `at: 0` with the actual logged `Date.now()` value. Coordinates are fractions of the recorded **window**, not CSS page pixels. The current tool description converts page points using:

```text
border = (outerWidth - innerWidth) / 2
x = (border + clientX) / outerWidth
y = (outerHeight - innerHeight - border + clientY) / outerHeight
```

Read the installed description first. Check cropping, DPI and browser chrome against a real frame; do not mix full-display, viewport and window coordinates. The bridge replaces recorded pointer data and adds click-based zooms; it is a mutating edit. Preserve the original checkpoint.

### Short first preview for a newly selected alternative

Use 10–20 seconds with an opening wide shot, two meaningful actions after ~3 seconds, a hover/menu and a scroll. Put one target near an edge. Confirm the pointer reaches each control, hover state appears, zoom includes the result, easing is smooth, and no duplicate cursor exists. Export; probe duration, dimensions and codecs; inspect normal-speed playback plus transition frames. No zoom can be intentional when clicks fall in the planner's opening wide interval. Move relevant actions later or add authored zooms; do not declare the recorder broken based only on that interval.

This preview evaluates the alternative's integration and appearance. An established Cursorful route needs only normal production quality review.

## Cap and authored-camera fallback

[Cap's agent CLI](https://cap.so/docs/agents) supports recording, project configuration and native export. [Studio mode](https://cap.so/docs/recording/studio-mode) provides click-generated zooms and cursor tracking. Inspect `cap guide --json` for the installed contract. Reviewed docs did not establish a dedicated CLI autozoom-generation command; verify populated camera segments before selecting Cap. Full config replacement can reset omitted values: read and preserve the complete project config. Cap cloud/library MCP alone does not record a desktop.

If using browser capture plus HyperFrames/Remotion/OpenScreen-authored zooms, collect timestamps, element bounds, click positions and relevant result regions during execution. Design a camera track: hold, ease into a modest crop, follow only when necessary, hold the result, then ease out. Render a cursor from the same clock and coordinate space. Keep subtitles on the outer canvas. This is custom composition, not Cursorful output; do not claim visual parity without reviewing the result.

Playwright action indicators and raw `recordVideo`/screencast provide interaction evidence, not the requested camera treatment. Use them as source footage only. See [screencast API](https://playwright.dev/docs/api/class-screencast) for the installed version's recording contract.
