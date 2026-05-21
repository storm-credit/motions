# Gemini Omni Official Surface Notes

Use this reference before routing work to `Gemini Omni Flash`.

## What Google Officially Says

As of `2026-05-21`, official Google sources say:

- `Gemini Omni` is a new model family.
- The first released model is `Gemini Omni Flash`.
- It can combine `text`, `image`, `video`, and `audio` input to create video.
- It is designed for conversational editing where each turn builds on the last.
- It is positioned around world knowledge, physics, continuity across edits, and multimodal creation.

## Official Surfaces

Officially announced rollout surfaces:

- `Gemini app`
- `Google Flow`
- `Google Flow Music`
- `YouTube Shorts`
- `YouTube Create`

Developer and enterprise APIs were announced as coming `in the coming weeks`, so do not assume a stable public API contract unless the user explicitly provides newer official docs.

## Launch-Time Cautions

- Official Google blog says Omni can combine images, audio, video, and text as input overall.
- The same launch post also says that for audio references, `only voice references will be supported for audio to start`, with other audio input types rolling out later.
- Therefore, do not assume every Omni surface currently accepts arbitrary uploaded music/audio the same way.
- Use `surface-ready prompt turns`, not fake API JSON, unless the operator is working on a documented developer surface.

## Motion / Edit Strengths

Route to Omni when the task needs:

- conversational scene edits across multiple turns
- source-footage transformation
- motion remix from input video or mixed references
- camera/style/environment changes while preserving scene memory
- explainers or knowledge-grounded motion sequences
- Flow Music music-video iteration

## Avoid Routing to Omni When

- deterministic motion control is required
- the shot depends on hard first/last-frame guarantees
- the operator needs a fully documented stable API right now
- the task is better handled by specialized motion or edit tools already in the stack

## Safety / Policy Notes

- Official blog says Omni videos are watermarked with `SynthID`.
- Google states avatar creation starts with `your own voice` using `Avatars`.
- The blog also says editing video to change audio and speech more broadly is still being tested for responsible rollout.
- Require rights over uploaded media and avoid routing requests that depend on unclear rights status.
