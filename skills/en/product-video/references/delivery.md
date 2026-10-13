# Verification and delivery

Use after composition. This procedure defines project QA targets, not platform guarantees.

## Verify actual output

- Check expected product result in every recorded scene against screenshot/assertion evidence. Narration must describe what the video demonstrates.
- Inspect opening, each action and camera move, scene joins, and final frame. Inspect at output size and a typical smaller player size. UI labels, cursor, captions, and branding must remain legible.
- Smooth zoom/pan/cursor is a release criterion: no abrupt scale jumps, wandering camera, clipped targets, duplicate cursor, or camera movement that hides the outcome. Compare the pilot with the chosen visual reference before expanding a batch.
- Probe final file for duration, dimensions, fps, video/audio streams, and decodable frames. Reject unexplained black/frozen segments, missing speech, truncated final words, or unintended silence. Intentional holds and fades are allowed.
- Check audible pronunciation, volume, and alignment at every scene boundary. As an initial sync tolerance, investigate action/caption errors above 200 ms; tighten where the scene demands it.

Useful FFmpeg/ffprobe commands after files exist, run with correct working directory:

```text
ffprobe -v error -show_entries format=duration:stream=codec_type,codec_name,width,height,avg_frame_rate,sample_rate,channels -of json final.mp4
ffmpeg -v error -i final.mp4 -f null -
ffmpeg -hide_banner -i final.mp4 -af loudnorm=I=-16:TP=-1.5:LRA=11:print_format=json -vn -f null -
```

`-16 LUFS` / `-1.5 dBTP` is a useful starting production target, not a YouTube requirement. For normalization, use measured two-pass settings and verify final encoded audio; preserve timeline duration. [FFmpeg loudnorm](https://ffmpeg.org/ffmpeg-filters.html#loudnorm), [ffprobe](https://ffmpeg.org/ffprobe.html).

YouTube-compatible baseline: MP4, H.264, yuv420p, AAC at 48 kHz, progressive frames, fast-start metadata. Keep intended capture/render fps consistent. Choose bitrate/quality from actual motion and UI readability, not file extension. [YouTube encoding guidance](https://support.google.com/youtube/answer/1722171?hl=en).

If concatenating independently rendered segments with FFmpeg, normalize dimensions, codecs, fps, pixel format, audio layout/sample rate, and time bases first. Concat stream-copy requires compatible streams. Avoid blindly copying heterogeneous segments. [FFmpeg concat demuxer](https://ffmpeg.org/ffmpeg-formats.html#concat).

## Deliver local package

Keep intermediates until final QA passes. Deliver:

- `final.mp4` and `captions.srt`.
- Thumbnail from real product imagery with accurate title; no unrelated generated UI.
- `youtube.md`: title, description, language, thumbnail text, and chapters for full tutorials where useful.
- Editable composition, scene manifest, narration text, brand config, recording/action script, and exact dependency versions.
- `qa.json`: pass/fail/untested checks, measured media properties, unresolved issues, actual generation usage, and artifact paths.

Return clickable local paths and explicit readiness: `ready`, `needs_review`, or `blocked`, with reasons. File existence alone is not success. If audio playback or visual inspection was unavailable, mark the relevant checks untested.

## Optional YouTube publication

Creation requests end with local artifacts unless upload/publication is also authorized. Reuse authorization already given; do not ask again merely because this reference mentions publication.

When upload is requested, resolve channel, audience setting, visibility, and schedule from user's instruction. Use OAuth and supported YouTube Data API, explicit `status.privacyStatus`, and resumable upload. Save resumable session/video ID before retrying; inspect upload state to avoid duplicate videos. Add caption track and thumbnail, then verify returned video state and URL. [Upload protocol](https://developers.google.com/youtube/v3/guides/using_resumable_upload_protocol), [videos.insert](https://developers.google.com/youtube/v3/docs/videos/insert), [captions.insert](https://developers.google.com/youtube/v3/docs/captions/insert), [thumbnails.set](https://developers.google.com/youtube/v3/docs/thumbnails/set).

Google's documentation checked 2026-10-13 contains conflicting statements about private-only restrictions for unverified API projects. Check current project eligibility and returned status; do not rely on default visibility or promise public publication in advance. State synthetic-media disclosure based on actual content and current [YouTube guidance](https://support.google.com/youtube/answer/14328491?hl=en), not a blanket assumption that every AI-assisted tutorial has the same disclosure requirement.

## Retry boundaries

Keep successful audio/capture/render outputs and rerun only invalidated stages. For repeatable local failures, make at most two targeted repair attempts per stage before reporting the cause and preserved artifacts. Do not keep issuing paid generations or uploads after an ambiguous outcome.

For headless jobs, return structured blocked status if authentication, native desktop permissions, voice selection, or required publishing details are missing. Preserve partial work; do not invent success or silently change tools when a required visual capability is absent.
