# Continuity Templates

Use these templates when creating continuity-safe video prompt packets.

## Continuity Bible

```text
=== CONTINUITY BIBLE ===

PROJECT
- Title:
- Format: short / ad / music video / drama / product / experiment
- Creative Director Mode: music video / film / animation
- Primary specialist:
- Secondary specialist:
- Target duration:
- Aspect ratio:
- Final delivery model:
- Candidate models:
- Language:
- Output style:

WORLD
- Genre:
- Tone:
- Reality layer:
- Visual grade:
- Color palette:
- Texture:
- Forbidden style drift:

ANIMATION LOOK BIBLE
- Animation family:
- Render mode:
- Line treatment:
- Shading model:
- Background treatment:
- Deformation budget:
- Pose language:
- FX language:
- Forbidden style drift:

CHARACTERS
- Character ID:
- Role:
- Age range:
- Face type:
- Body type:
- Hair:
- Wardrobe locked:
- Signature detail:
- Emotional baseline:
- Emotional arc:
- Must not change:

PROPS
- Prop ID:
- Description:
- Owner:
- Screen position rule:
- Continuity importance:
- Must not change:

TIME
- Time of day:
- Weather:
- Light source:
- Light direction:
- Time progression:
- Forbidden time drift:

SPACE
- Primary location:
- Layout map in words:
- Camera axis / 180-degree line:
- Foreground:
- Midground:
- Background:
- Entry/exit paths:
- Forbidden spatial drift:

CAMERA LANGUAGE
- Default lens feeling:
- Framing rules:
- Camera movement style:
- Allowed camera moves:
- Forbidden camera moves:
- Shot rhythm:

CINEMATOGRAPHY PACKAGE
- Focal length eq:
- Sensor feel:
- Aperture / DOF:
- Camera height:
- Subject distance:
- Rig:
- Movement motivation:

LIGHTING PLAN
- Key source:
- Fill ratio:
- Backlight:
- Practicals:
- Light continuity note:

BLOCKING GEOMETRY
- Actor marks:
- Eyeline target:
- Prop hand:
- Entry/exit lanes:
- Reverse allowed:

CREATIVE DIRECTION
- Music video notes:
- Music structure:
- Performance coverage:
- Refrain plan:
- Film notes:
- Animation notes:
- Primary payoff:

NARRATIVE BEAT SHEET
- Scene ID:
- Sequence ID:
- Beat objective:
- Obstacle:
- Turn or reveal:
- Dominant POV:

PERFORMANCE MAP
- Objective:
- Tactic:
- Subtext:
- Tempo:
- Gaze direction:
- Micro-expression trigger:
- Emotion start:
- Emotion end:
- Breath / effort note:
- Speaker visibility:

AUDIO
- Music mood:
- BPM:
- Opening stinger:
- Rhythm layer:
- Diegetic sound:
- Dialogue:
- Ending tail:

DELIVERY VARIANTS
- Master aspect:
- Social aspect:
- Center safe zone:
- Text safe zone:
- Crop-safe blocking:
- Reframe fallback:

RIGHTS / ELIGIBILITY
- Performer type:
- Real-person rights confirmed:
- Track rights confirmed:
- Audio source type:
- Face input required:
- Target model allows input:
- Copyright risk:

HOOK STRATEGY
- 0.0-0.5s:
- 0.5-1.5s:
- 1.5s+:
- Payoff:

NEGATIVE CONSTRAINTS
- No text/subtitles/watermarks/logos unless requested:
- No real-person likeness unless rights are confirmed:
- No face/body defects:
- No wardrobe flicker:
- No time/light drift:
- No prop pop-in/pop-out:
- No AI plastic skin:
- Brief-specific negatives:

REFERENCE ASSETS
- Asset ID:
- Asset type: image / video / audio / sketch
- Purpose:
- Use as first frame: yes / no
- Use as motion reference: yes / no
- Use as style reference: yes / no
- Natural-language description:

ANIMATION ASSET PACK
- Hero model sheet:
- Turnaround views:
- Expression sheet:
- Mouth chart:
- Hand-shape sheet:
- Prop orthos:
- Layout board:
- Color script:
- Animatic or storyboard:
- Asset priority:
- Platform binding method:

SEED / REPRODUCIBILITY
- Seed strategy:
- Successful generation ID:
- Reuse rules:
- Fallback if seed unavailable:

ENDING STATE
- Final character pose:
- Final expression:
- Final camera position:
- Final light state:
- Final prop positions:
- Bridge to next segment:
```

## Shot Spec

```text
=== SHOT SPEC ===

SHOT ID:
Timecode:
Purpose:
Assigned model:
Fallback model:

Continuity anchors:
- Character:
- Wardrobe:
- Prop:
- Location:
- Light:
- Emotional state:

Action:
- Main action:
- Secondary action:
- Micro gesture:

Animation performance:
- Acting beat:
- Key pose A:
- Key pose B:
- Key pose C:
- Contact pose:
- Hold feel:
- Accent frames:
- Mouth activity:
- Phoneme density:
- Secondary action:
- FX beat:
- Parallax intent:
- Silhouette goal:

Camera:
- Framing:
- Angle:
- Movement:
- Lens feeling:
- Blocking:

Audio:
- Music cue:
- Sound effect:
- Dialogue:

Model-specific notes:
- Seedance:
- Kling:
- Veo:
- Sora:
- Creative specialist note:

Coverage:
- Coverage type:
- Editorial role:
- Shot priority:

Editorial:
- Cut type:
- Cut trigger:
- Match-on-action anchor:
- J-cut or L-cut:
- Sound bridge:
- Insert required:
- Reaction required:
- Pickup priority:
- Repair hide point:

Ending state:
- Pose:
- Expression:
- Camera:
- Prop:
- Light:

Risks:
- Continuity risk:
- Motion risk:
- Face/body risk:
- Prompt overload risk:
```

## Specialist Handoff

```text
=== SPECIALIST HANDOFF ===

To:
Assigned shot IDs:
Goal:
Model/tool:

Use only this Continuity Bible:
[paste locked Bible]

Use these shot specs:
[paste assigned shot specs]

Your task:
- Optimize only the assigned shots.
- Keep all locked continuity facts unchanged.
- Produce model-ready prompts.
- Include any model-specific warnings.
- Include ending state for the next shot.

Do not:
- Rewrite the whole story.
- Change character design.
- Change wardrobe.
- Change time of day or location unless explicitly instructed.
- Add new props unless approved by the Orchestrator.
```

## Specialist Report

```text
=== SPECIALIST REPORT ===

Specialist:
Role:
Creative mode:
Owned shots / passes:

Primary objective:
- 

Required locks:
- 

Recommended model/tool:
- Primary:
- Fallback:

Main risks:
- 

Avoid:
- 

Success criteria:
- 
```

## Readiness Report

```text
=== READINESS REPORT ===

Status:
Owner:
Version:
Review date:

Scene function / dramatic question:
Success condition:

Input completeness:
- Known facts:
- Assumptions:
- Unknowns:
- Blockers:
- Defaults used:

Asset readiness:
- Asset:
  - Status: approved / proxy / missing
  - Allowed uses:
  - Missing prep:

Coverage gap report:
- Opener:
- Pivot:
- Payoff:
- Button:
- Insert / reaction safety:

Continuity risk register:
- Axis:
- Eyeline:
- Prop hand:
- Wardrobe:
- Light direction:
- Geography:
- Performer match:

Model feasibility:
- Primary route:
- Failure risk:
- Simplify or split needed:

Decision:
- GO / HOLD / REVISE
- Reason:

For music video mode, also include:
- Music source report:
- Asset readiness report:
- Rights policy report:
- Assumptions and blockers:
- Success targets:
```

## Orchestra Execution Plan

```text
=== ORCHESTRA EXECUTION PLAN ===

Goal:
Delivery target:
Creative Director Mode:
Why this route:

Active specialists:
- Specialist:
  - Why active:
  - Owns:

Execution order:
1. Previz:
2. First-pass generation:
3. Hero pass:
4. Motion / extension:
5. Edit / repair:
6. Final assembly:

Shot ownership:
- Shot ID:
  - Owner:
  - Model/tool:
  - Fallback:
  - Editorial role:

Dependencies:
- 

Conflict resolutions:
- 

Stop conditions:
- 

For music video mode, also include:
- Execution board:
  - Section / Shot:
  - Owner:
  - Model/tool:
  - Fallback order:
  - Dependency assets:
  - First-pass vs hero pass:
  - Repair owner:
  - Stop condition:
```

## Pass Plan

```text
=== PASS PLAN ===

Shot ID:
- Coverage tier: hero / safety / pickup / expendable
- Dependencies:
- Previz owner:
- Hero owner:
- Repair owner:
- Assembly owner:

Acceptance criteria:
- Previz pass:
- Hero pass:
- Repair pass:
- Assembly pass:

Retake policy:
- Max attempts:
- Repair threshold:
- Regenerate threshold:
- Escalation path:
```

## Execution Gates

```text
=== EXECUTION GATES ===

Rights gate:
- Performer rights confirmed?
- Track / asset rights confirmed?
- Platform safety constraints legal?

Continuity gate:
- Character / wardrobe / prop locks complete?
- Start/end baton states complete?
- Delivery variants complete?

Capability gate:
- Chosen model supports the required input path?
- Required reference path is legal?
- Required resolution / aspect / duration are legal?

Previz gate:
- Cheap preview route defined?
- Success / failure signal defined?

Hero gate:
- Premium shots identified?
- Approval owner defined?

Repair gate:
- Edit fallback defined?
- Motion fallback defined?
- Replacement shot fallback defined?

Final gate:
- Assembly order locked?
- Final audit owner assigned?
```

## Execution Log

```text
=== EXECUTION LOG ===

Shot ID:
- Current state: queued / previz pass / hero pass / repair / locked
- Last owner:
- Last action:
- Result:
- Defects found:
- Delta from previous pass:
- Next step:
```

## Final Prompt Packet

```text
=== FINAL VIDEO PROMPT PACKET ===

1. Continuity Bible
[locked project bible]

2. Creative Director Mode
[music video / film / animation plus specialist notes]

3. Specialist Reports
[creative specialist + model specialist reports]

4. Orchestra Execution Plan
[execution order, ownership, dependencies, stop conditions]

5. Shot Timeline
[shot-by-shot timeline]

6. Model Assignment
[shot -> model/tool -> reason -> fallback]

7. Model-Ready Prompts
[only selected models, not every model by default]

8. Tool / Edit / Motion Passes
[motion/edit/dop instructions if needed]

9. Execution Gates
[gate checklist before final generation]

10. Continuity Audit
[checklist results]

11. Next Action
[what to generate first]
```

## Continuity Audit

```text
=== CONTINUITY AUDIT ===

Character:
- Same face type preserved?
- Same body type preserved?
- Same hair preserved?
- Same wardrobe preserved?
- Signature detail visible when needed?

World:
- Same genre and tone preserved?
- Same color palette preserved?
- No style drift between shots?

Time / Light:
- Time of day consistent?
- Weather consistent?
- Light direction consistent?
- No sudden day/night jump?

Space:
- Location layout consistent?
- 180-degree line respected?
- Character screen direction preserved?
- Props remain in plausible positions?

Action:
- Shot starts from previous ending state?
- Motion direction consistent?
- Emotional progression justified?

Audio:
- Opening stinger present?
- Rhythm layer consistent?
- Dialogue does not contradict action?
- Ending tail supports next segment?

Prompt:
- Not overloaded?
- No contradictory instructions?
- Negative constraints included?
- Model-specific controls separated?

Animation:
- Off-model silhouette avoided?
- Line boil or line dropout controlled?
- Cel-shadow consistency maintained?
- Rimlight consistency maintained?
- Texture shimmer controlled?
- Rig break or joint pop avoided?
- Parallax mismatch avoided?
- FX density drift avoided?
- Prop scale drift avoided?

Routing:
- Assigned model matches shot purpose?
- Fallback model selected?
- Repair path defined?
```
