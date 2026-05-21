# Official Doc Sync Notes

Last deep sync: `2026-05-21` (Asia/Seoul)

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
- [Kling Element Library User Guide](https://kling.ai/quickstart/klingai-element-library-3-user-guide)
- [Kling Start and End Frames guide](https://kling.ai/quickstart/ai-video-start-end-frames)
- [Kling VIDEO 3.0 Motion Control guide](https://kling.ai/quickstart/motion-control-user-guide)
- [Kling Extend with Prompts guide](https://kling.ai/quickstart/ai-video-extension)

Key doc-derived constraints and capabilities:

- Kling VIDEO 3.0 officially supports `Multi-Shot` and `Custom Multi-Shot`.
- Kling VIDEO 3.0 officially supports multi-image references and video references as Elements for stronger subject consistency.
- Kling VIDEO 3.0 officially supports upgraded Native Audio with multilingual character speech.
- Kling Element Library officially supports multi-angle reusable elements, voice binding for character elements, up to 3 bound elements in start-frame/start-and-end-frame generation, and up to 7 reference characters in video generation.
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
- Reference asset image guidance is officially documented for Veo 3.1 on supported tiers.
- Extend videos are officially documented for Veo 3.1 on supported tiers.
- Reference image to video on Veo 3.1 supports only `8` seconds.
- Style reference images are **not** supported on Veo 3.1 and remain a Veo 2 path.
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

## Gemini Omni Flash

Official sources reviewed:

- [Introducing Gemini Omni](https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-omni/)
- [Gemini Omni for Google Flow and Flow Music](https://blog.google/innovation-and-ai/models-and-research/google-labs/flow-updates/)
- [Gemini app update with Gemini Omni](https://blog.google/innovation-and-ai/products/gemini-app/next-evolution-gemini-app/)
- [Lyria 3 Pro launch post](https://blog.google/innovation-and-ai/technology/ai/lyria-3-pro/)

Key doc-derived constraints and capabilities:

- Google officially announced a new `Gemini Omni` family, with `Gemini Omni Flash` as the first released model.
- Omni is officially positioned as a model that can create from `any input`, starting with video.
- Official blog says Omni can combine `images`, `audio`, `video`, and `text` as input to generate or edit video.
- Official launch post says Omni supports conversational editing where each instruction builds on the last and the scene remembers prior turns.
- Official blog highlights stronger world knowledge, improved intuitive physics, and knowledge-grounded explainers.
- Official rollout surfaces are `Gemini app`, `Google Flow`, `YouTube Shorts`, and `YouTube Create`; Flow updates also announce Omni support for `Google Flow Music`.
- Official Flow update says Omni Flash improves character consistency and preserves identity and voice across scenes in Flow.
- Official launch post says `only voice references` are supported for audio references to start, with other audio input types rolling out later, so general audio-upload behavior should be treated as surface-dependent.
- Official launch post says avatar videos start with `your own voice` through `Avatars`, while broader speech/audio editing is still being tested.
- Official launch post says all Omni-generated videos include `SynthID`.
- Official launch post says developer and enterprise APIs are coming `in the coming weeks`, so stable public API assumptions should be avoided unless newer official docs are supplied.

## How These Notes Were Applied

These official-doc findings were used to tighten:

- `claude-skills/seedance-prompt-director`
- `claude-skills/kling-prompt-director`
- `claude-skills/veo-prompt-director`
- `claude-skills/omni-prompt-director`
- `claude-skills/sora-prompt-director`
- `claude-skills/video-orchestrator`
- `PROMPT_DIRECTOR_SKILL_PACK.md`
