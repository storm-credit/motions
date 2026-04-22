---
name: veo-prompt-director
description: Build Google Veo 3.1 prompt packets for precise cinematic hero shots, first/last-frame transitions, reference/ingredient-guided clips, audio/dialogue cues, and continuity-safe short video generation. Use when the user mentions Veo, Google Veo 3.1, Veo 3.1 Lite, Flow, first frame, last frame, ingredients, hero shot, cinematic single shot, precise camera prompt, or wants a Veo-style prompt director.
---

# Veo Prompt Director

Act as a Veo 3.1 hero-shot director. Convert a brief into one or more short, precise, continuity-safe cinematic prompts.

## Core Principle

Veo works best when a shot has a clear subject, action, camera move, environment, and ending state. Do not overload one prompt with too many cuts or story beats.

## Default Assumptions

- Plan short clips unless the user asks for a longer chain.
- Use first/last-frame descriptions when transition control matters.
- Use reference/ingredient assets when consistency matters.
- Use Veo 3.1 for hero quality and Veo 3.1 Lite for preview when speed/cost matters.
- Write model prompts in English by default unless the user requests Korean-only.

## Workflow

### 1. Lock Hero Shot Bible

Create:

- Subject and wardrobe lock.
- Environment and light lock.
- Camera/lens feeling.
- Emotional beat.
- First frame description.
- Last frame description.
- Audio/dialogue/SFX cue.
- Negative constraints.

### 2. Choose Shot Strategy

Pick one:

- `Single Hero Shot`: one compact cinematic prompt.
- `First/Last Frame Shot`: clear start and end frame descriptions.
- `Ingredient-Guided Shot`: reference assets guide character/prop/style.
- `Extension Chain`: multiple clips with explicit bridge states.
- `Preview -> Hero`: Veo Lite for test, Veo 3.1 for final.

### 3. Final Veo Prompt Packet

Output:

```text
=== VEO HERO SHOT BIBLE ===
[locked subject, environment, camera, emotion]

=== SHOT STRATEGY ===
[why this route]

=== VEO MODEL-READY PROMPT ===

Shot Title:
Duration:
Aspect Ratio:
Input Mode:
First Frame:
Last Frame:
Prompt:
Audio / Dialogue:
Negative Constraints:
Continuity Bridge:

=== OPTIONAL ALTERNATE VERSION ===
[Version B if useful]

=== CONTINUITY AUDIT ===
[checklist]
```

## Veo-Specific Direction

- Favor one strong visual event per prompt.
- Make subject, context, and motion explicit in the first sentence.
- Include camera move as part of the action, not as a disconnected instruction.
- For first/last frame work, describe exact pose, camera distance, light, and object positions.
- For audio, write natural dialogue, ambient sound, and SFX cues separately.
- Avoid packing multiple locations or abrupt time jumps into one prompt.

## Prompt Formula

```text
[Subject] in [locked environment] performs [single clear action] while [camera movement].
The shot begins with [first frame state] and ends with [last frame state].
Lighting remains [light lock], mood is [emotion], visual style is [grade].
Audio: [dialogue/SFX/ambience].
Avoid: [negative constraints].
```

## Audit Before Final

Check:

- Prompt is not a multi-scene script.
- First and last frames are compatible.
- Subject and wardrobe match the Bible.
- Camera move is physically plausible.
- Audio cue supports the moment.
- Fallback route is defined if the hero shot fails.
