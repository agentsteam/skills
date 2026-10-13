# ElevenLabs narration and timeline

Use for both full tutorials and feature shorts. Checked 2026-10-13; recheck account/model capabilities before first paid run.

## Setup and voice selection

- Read `ELEVENLABS_API_KEY` from environment or managed secrets. Save only its presence in logs. Keep keys out of scripts, narration, manifests, screenshots, and generated assets.
- Reuse user's chosen `voice_id`, language, model, and pronunciation dictionary. If missing, list available voices/models and resolve voice choice before producing a whole batch. Do not substitute a stock voice silently.
- Product marketing requires an applicable commercial license. ElevenLabs says paid subscriptions cover eligible generated content; free-plan content and Beta Services have different restrictions. Check the actual selected service and account. [Commercial-use guidance](https://help.elevenlabs.io/hc/en-us/articles/13313564601361-Can-I-publish-the-content-I-generate-on-the-platform).
- Use REST or official SDK for repeatable runs; installed official CLI is also suitable. Keep ElevenLabs even when a renderer offers its own TTS provider.

## Generate once per stable narration unit

Complete a silent rehearsal before synthesis. Each unit should describe one visible action/result or a short coherent sequence. Use full spoken sentences, not compressed agent prose. Spell product terms consistently; expand ambiguous acronyms or use pronunciation dictionaries.

Supported request shape:

```http
POST https://api.elevenlabs.io/v1/text-to-speech/{voice_id}/with-timestamps?output_format=mp3_44100_128
Content-Type: application/json
xi-api-key: value-from-environment
```

```json
{
  "text": "Open the project settings. Choose your workspace, then save the change.",
  "model_id": "eleven_multilingual_v2"
}
```

`eleven_multilingual_v2` is a documented example, not a requirement or assertion that it is the newest/best model. Select a currently available model suitable for user's language and consistent tutorial delivery. Output formats have plan restrictions; MP3 above is a practical baseline. [TTS with timestamps](https://elevenlabs.io/docs/api-reference/text-to-speech/convert-with-timestamps/), [TTS capabilities](https://elevenlabs.io/docs/overview/capabilities/text-to-speech).

Save decoded `audio_base64` directly to disk, plus `alignment`, `normalized_alignment`, request ID, settings, and generation cost when returned. Never print the base64 payload. Probe decoded duration; timing metadata alone does not establish file duration.

Use `previous_text`/`next_text` when supported to preserve continuity between units. Include these fields, pronunciation dictionary version, model, voice, output format, and voice settings in the cache key alongside narration text. A supplied seed is best effort, not guaranteed reproducibility.

Keep a generation ledger. Reuse matching successful files on rerun. Changed wording invalidates its audio and dependent timing. An ambiguous network timeout may still have consumed credits: inspect saved response/history before generating again. Retry a failed scene within remaining authorized budget, not the entire project. [API response metadata](https://elevenlabs.io/docs/api-reference/introduction/).

## Convert speech into action cues

1. Prefer non-null `normalized_alignment` for displayed spoken text. Its character and start/end arrays must have equal lengths and finite, monotonic timing.
2. Group contiguous characters into words, retaining punctuation and original order. Each word takes its first character's start and last character's end. Do not match normalized numbers against unnormalized script offsets.
3. Link each UI action to a unique phrase/word span. Repeated phrases need an occurrence index. Record action cue time, expected result, and a short viewing hold.
4. Prepare/reset app before starting each scene capture. Begin actions at their planned cue, then wait for observable result. Waits for content readiness are assertions; scheduled holds are editorial timing. They are different operations.
5. Compare actual events against cues. If loading or animation makes an action late, repair that scene or revise its narration/pauses. Padding only the final frame cannot fix an action already shown at the wrong spoken cue.

Narration is normally the timing reference. Record deliberate pre-action/post-action holds. Keep speech at natural speed. A shorter visual can hold on its verified result; a longer visual requires trimming irrelevant waiting, splitting the scene, or revised narration. Never silently cut speech with `-shortest` to conceal a duration mismatch.

For Chrome UI automation with variable tool latency, record usable shots with generous holds and log actual action times. Cut idle gaps and map source action times to their spoken cues during editing. Do not retain agent thinking/tool delays as final-video pacing. Preserve the time viewers need to understand loading, navigation, and results.

For missing/invalid alignment, use actual audio plus its exact transcript with [Forced Alignment](https://elevenlabs.io/docs/api-reference/forced-alignment/create). Account for its separate usage cost. Do not request transcription merely to recover timing already returned by TTS. Alignment confirms timing; it does not prove pronunciation quality.

## Final timeline and captions

Keep all local timings in seconds. For frame-based output, convert boundaries consistently using actual output fps; recalculate final durations after trimming and padding.

Build one ordered schedule including any opening hook, intro, product scenes, chapter cards, and outro. For scene `i`:

```text
scene_start = sum(duration of all preceding timeline items) - preceding transition overlaps
caption_start = scene_start + narration_offset_in_scene + word.start
caption_end   = scene_start + narration_offset_in_scene + word.end
```

Count each item's duration exactly once; an outcome shown before the intro is still a timeline item. Any transition overlap changes `scene_start`; include it explicitly. Simple hard cuts and brief graphic transitions reduce drift in long tutorials. Keep caption timing separate from camera keyframes so zoom edits cannot move speech.

Create UTF-8 SRT for delivery. Group words into readable phrases with at most two lines; keep captions out of essential UI. Shorts can additionally burn captions into the composition. Supply HyperFrames captions as supported word objects, e.g. `{ "id": "s02-w03", "text": "workspace", "start": 8.24, "end": 8.78 }`, with offsets already applied. Verify current component's timing contract before import.

Completion: all narration units have cached audio, measured duration, usable alignment, unique action cues, and global caption offsets. Listen/check audio using available audio tools; record any unperformed listening check honestly.
