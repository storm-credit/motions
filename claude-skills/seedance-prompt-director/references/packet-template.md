# Seedance Packet Template

Use this as the full output skeleton for complex Seedance requests.

```text
=== CONTINUITY BIBLE ===

WORLD
- Genre / tone:
- Reality layer:
- Visual grade:
- Aspect ratio:
- Seed strategy:

ANIMATION LOOK BIBLE
- Animation family:
- Render mode:
- Line treatment:
- Shading model:
- Background treatment:
- Deformation budget:
- Pose language:
- FX language:

CREATIVE DIRECTOR MODE
- Primary mode:
- Secondary mode:
- Why this mode:
- Music video notes:
- Film notes:
- Animation notes:

NARRATIVE BEAT SHEET
- Scene ID:
- Sequence ID:
- Beat objective:
- Obstacle:
- Turn or reveal:
- Dominant POV:

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

BLOCKING GEOMETRY
- Actor marks:
- Eyeline target:
- Prop hand:
- Entry/exit lanes:

CHARACTERS
- Character ID:
- Appearance:
- Wardrobe locked:
- Signature detail:
- Emotional baseline:
- Emotional target:

TIME
- Time of day:
- Weather:
- Light direction:
- Time progression:

SPACE
- Primary location:
- Spatial layout:
- Camera axis:
- Blocking:

HOOK STRATEGY
- 0-0.5s:
- 0.5-1.5s:
- 1.5s+:

MUSIC STRUCTURE
- Track source:
- Rights status:
- BPM:
- Time signature:
- Section map:
- Lyric priority lines:
- Sync priority:
- Section energy:

PROPS / MOTIFS
- Prop:
- Motif:

REFERENCE INVENTORY
- Asset 1:
  - Type:
  - Bound role:
  - Must preserve:
  - Can ignore:
- Asset 2:
  - Type:
  - Bound role:
  - Must preserve:
  - Can ignore:
- Conflict rule:

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

AUDIO 3-LAYER
- Opening stinger:
- Rhythm beat:
- BPM:
- Dialogue timing:
- Beat-aligned cut notes:
- Ending tail:

PERFORMANCE COVERAGE
- Shot role:
- Artist visibility:
- Lip-sync mode:
- Lyric excerpt:
- Dance dependency:
- Count-in:
- Count-out:
- Full-body required:
- Hands/feet visibility:
- Formation rule:
- Fallback cutaway:

REFRAIN PLAN
- Chorus anchor shot ID:
- Repeat count:
- Must-match locks:
- Allowed variation:
- Motif callback:
- Final chorus escalation:
- Thumbnail frame:
- Loop-out frame:

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

NEGATIVE CONSTRAINTS
- No text, subtitles, watermarks, logos unless requested.
- No face/body defects.
- No time/light drift.
- No wardrobe flicker.
- No prop pop-in/pop-out.
- No AI plastic skin.

=== SHOT TIMELINE ===

SHOT 1 ([time]) - [name]
- Continuity anchor:
- Shot role:
- Coverage type:
- Editorial role:
- Action:
- Camera:
- Effects:
- Audio:
- Ending state:

SHOT 2 ([time]) - [name]
- Continuity anchor from SHOT 1:
- Action:
- Camera:
- Effects:
- Audio:
- Ending state:

SHOT N ([time]) - [name]
- Continue the same schema.
- Every shot must inherit the previous shot's ending state unless a motivated transition is stated.

=== FINAL PROMPT ===

SEGMENT 1 ([time range])

[Korean Block]
- Technical parameters:
- Creative Director Mode:
- Audio 3-layer:
- Music structure:
- Performance coverage:
- Refrain plan:
- BPM / dialogue timing / beat-cut notes:
- Scene prompts:
- Negative prompt:
- Speed / Camera / Transitions / Optical:
- Effects density map:
- Exact ending state / next segment bridge:

[English Block if useful]
- Technical parameters:
- Audio 3-layer:
- BPM / dialogue timing / beat-cut notes:
- Scene prompts:
- Negative prompt:
- Speed / Camera / Transitions / Optical:
- Effects density map:
- Exact ending state / next segment bridge:

SEGMENT 2 ([time range], if needed)
- Start from Segment 1 exact ending state.
- Repeat the full prompt block.
- Default 30s split: Segment 1 = 0-15s, Segment 2 = 15-30s unless user specifies otherwise.

=== CONTINUITY AUDIT ===
- Character:
- Wardrobe:
- Light:
- Space:
- Props:
- Audio:
- Hook:
- Prompt load:
- Continuity load:

=== EDITORIAL PLAN ===
- Cut type:
- Cut trigger:
- Match-on-action anchor:
- J-cut or L-cut:
- Sound bridge:
- Insert required:
- Reaction required:
- Pickup priority:
- Repair hide point:
```
