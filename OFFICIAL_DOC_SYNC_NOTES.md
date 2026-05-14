# Official Doc Sync Notes

Last deep sync: `2026-05-14` (Asia/Seoul)

This file records the official-doc findings used to align the current prompt-director skill pack.

## Seedance 2.0

Official sources reviewed:

- [Seedance 2.0 official launch blog](https://seed.bytedance.com/en/blog/seedance-2-0-official-launch)
- [Seedance 2.0 model page](https://seed.bytedance.com/en/seedance2_0)
- [Seedance 2.0 1080p announcement on Volcengine](https://developer.volcengine.com/articles/7632954025926721590)

Key doc-derived constraints and capabilities:

- Official launch highlights mixed-modality input across text, image, audio, and video.
- Launch blog says users can combine up to `9` images, `3` video clips, and `3` audio clips in one flow.
- Launch blog shows explicit reference notation like `@Image 1`, so explicit asset tags are valid on supported official surfaces.
- Official messaging emphasizes `15-second` high-quality multi-shot audio-video output.
- Official messaging emphasizes extension and editing support.
- Official messaging highlights dual-channel / stereo audio generation and multi-track output.
- Volcengine announced native `1080p` generation support for Seedance 2.0.

## Kling 3.0

Official sources reviewed:

- [Kling quickstart](https://kling.ai/quickstart)
- [Kling VIDEO 3.0 Model User Guide](https://kling.ai/quickstart/klingai-video-3-model-user-guide)
- [Kling Start and End Frames guide](https://kling.ai/quickstart/ai-video-start-end-frames)
- [Kling VIDEO 3.0 Motion Control guide](https://kling.ai/quickstart/motion-control-user-guide)
- [Kling Extend with Prompts guide](https://kling.ai/quickstart/ai-video-extension)

Key doc-derived constraints and capabilities:

- Kling VIDEO 3.0 officially supports `Multi-Shot` and `Custom Multi-Shot`.
- Kling VIDEO 3.0 officially supports multi-image references and video references as Elements for stronger subject consistency.
- Kling VIDEO 3.0 officially supports upgraded Native Audio with multilingual character speech.
- Start and End Frames guidance says the two images should be similar; large differences may cause a shot switch.
- Motion Control guidance says facial element binding uses facial information only, not clothing, hairstyle, makeup, or props.
- Extend with Prompts guidance says extensions usually add `4-5` seconds and can continue up to `3 minutes`, with prompt continuity centered on `Subject + Movement`.

## Google Veo 3.1

Official sources reviewed:

- [Veo 3.1 model page on Vertex AI](https://docs.cloud.google.com/vertex-ai/generative-ai/docs/models/veo/3-1-generate)
- [Veo first and last frames guide](https://docs.cloud.google.com/vertex-ai/generative-ai/docs/video/generate-videos-from-first-and-last-frames)
- [Veo asset/style image guide](https://docs.cloud.google.com/vertex-ai/generative-ai/docs/video/use-reference-images-to-guide-video-generation)
- [Veo prompt guide on Vertex AI](https://docs.cloud.google.com/vertex-ai/generative-ai/docs/video/video-gen-prompt-guide)
- [DeepMind Veo prompt guide](https://deepmind.google/models/veo/prompt-guide/)

Key doc-derived constraints and capabilities:

- Veo 3.1 officially supports `4`, `6`, or `8` second videos.
- Veo 3.1 officially supports `16:9` and `9:16`.
- Veo 3.1 officially supports `720p` and `1080p` output at `24 FPS`.
- Veo 3.1 model page lists official prompt-language support as `English`.
- First/last-frame generation is officially supported.
- Asset / ingredient image guidance is officially documented for Veo 3.1.
- Style reference images are **not** supported on Veo 3.1 and are still a Veo 2 path.
- Vertex prompt guide documents negative prompts and recommends listing unwanted elements directly rather than phrasing them as "don't" instructions.

## Sora 2

Official sources reviewed:

- [OpenAI video generation with Sora API guide](https://developers.openai.com/api/docs/guides/video-generation)
- [OpenAI Sora 2 launch post](https://openai.com/index/sora-2/)
- [OpenAI model catalog](https://developers.openai.com/api/docs/models)

Key doc-derived constraints and capabilities:

- OpenAI's official API guide says Sora supports prompt-only generation, image references, reusable character assets, extensions, and edits.
- `input_reference` controls the opening frame of a single generation.
- `characters` are reusable assets for non-human subjects across generations.
- Official API docs say character uploads with human likeness are blocked by default.
- Official API docs say real people/public figures cannot be generated, copyrighted characters/music are rejected, and input images with human faces are currently rejected.
- Official API docs say extensions preserve continuity but accept only a source video and prompt; they do not support characters or image references.
- Official API docs position `sora-2` for speed/iteration and `sora-2-pro` for higher fidelity / 1080p production output.
- Official API docs state that the Sora 2 Videos API is deprecated and scheduled to shut down on `2026-09-24`.

## How These Notes Were Applied

These official-doc findings were used to tighten:

- `claude-skills/seedance-prompt-director`
- `claude-skills/kling-prompt-director`
- `claude-skills/veo-prompt-director`
- `claude-skills/sora-prompt-director`
- `claude-skills/video-orchestrator`
- `PROMPT_DIRECTOR_SKILL_PACK.md`
