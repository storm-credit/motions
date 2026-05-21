# Omni Packet Template

```text
=== OMNI SURFACE LOCK ===

- Target surface:
- Use case:
- Availability risk:
- Why Omni:
- Do not assume:

=== SCENE MEMORY BIBLE ===

CREATIVE DIRECTOR MODE
- Primary mode:
- Secondary mode:
- Why this mode:
- Music video notes:
- Film notes:
- Animation notes:

SUBJECT LOCK
- Character / object:
- Wardrobe / material:
- Signature detail:
- Voice / avatar:

WORLD LOCK
- Location:
- Time:
- Weather:
- Light:
- Palette:

MOTION MEMORY
- Start state:
- Main action path:
- End state:
- Motion to preserve:
- Motion to change:

CAMERA MEMORY
- Angle:
- Framing:
- Movement:
- Lens feel:

PHYSICS / KNOWLEDGE ANCHOR
- Physical rules:
- Factual rules:
- Explainability goal:

NEGATIVE / DO NOT CHANGE
- No identity drift.
- No unwanted location jump.
- No wardrobe/material drift.
- No broken physics unless requested.
- No extra props or characters unless requested.

=== INPUT BUNDLE MAP ===

- Asset:
  - Type:
  - Primary role:
  - Must preserve:
  - May reinterpret:
  - Must not affect:

=== MOTION + EDIT STRATEGY ===

- Base motion:
- Edit target:
- Camera change:
- Sync behavior:
- Loop target:
- Crop-safe target:

=== OMNI TURN PLAN ===

TURN 1: BASE CREATE / BASE TRANSFORM
[prompt]

TURN 2: MOTION / ACTION REWRITE
[prompt]

TURN 3: CAMERA / STYLE / ENVIRONMENT REFINE
[prompt]

TURN 4: FINAL POLISH / LOOP / CROP-SAFE VERSION
[prompt if needed]

=== SAFETY / ELIGIBILITY CHECK ===

- Rights over uploaded media confirmed:
- Avatar / voice path appropriate:
- Audio input type allowed on this surface:
- Policy risk:
- Surface limitation note:

=== CONTINUITY AUDIT ===

- Same subject / world / camera memory preserved?
- Motion change isolated cleanly?
- Same scene remembered across turns?
- Music / voice sync logic explicit?
- No fake API assumptions?
```

## Worked Example

```text
=== OMNI SURFACE LOCK ===
- Target surface: Google Flow
- Use case: transform source footage into stylized motion remix
- Availability risk: medium, because audio input behavior is surface-dependent
- Why Omni: needs conversational multi-turn editing on top of existing footage
- Do not assume: stable public API fields

=== SCENE MEMORY BIBLE ===
CREATIVE DIRECTOR MODE
- Primary mode: film
- Secondary mode: N/A
- Why this mode: one dramatic reveal, then a visual escalation

SUBJECT LOCK
- Character / object: one violinist
- Wardrobe / material: black concert jacket, same violin body shape
- Signature detail: silver ring on right hand
- Voice / avatar: N/A

WORLD LOCK
- Location: empty recital hall stage
- Time: blue-hour interior mood
- Weather: N/A
- Light: cool key, warm rim from practicals
- Palette: blue-black with warm amber edge lights

MOTION MEMORY
- Start state: violinist playing mid-phrase in medium shot
- Main action path: bowing continues, slight torso turn, camera circles left
- End state: over-shoulder angle on strings and audience lights
- Motion to preserve: bowing rhythm and body timing
- Motion to change: camera path and hall transformation

CAMERA MEMORY
- Angle: starts front 3/4, ends over-shoulder
- Framing: medium to tighter medium
- Movement: smooth circular glide
- Lens feel: cinematic neutral

PHYSICS / KNOWLEDGE ANCHOR
- Physical rules: keep body and violin movement believable
- Factual rules: bow contact stays plausible
- Explainability goal: N/A

=== INPUT BUNDLE MAP ===
- Source video:
  - Type: video
  - Primary role: performance motion source
  - Must preserve: violin rhythm, hand timing, jacket silhouette
  - May reinterpret: stage design
  - Must not affect: subject identity

=== OMNI TURN PLAN ===
TURN 1: Keep the violinist, performance timing, and jacket exactly the same. Transform the plain stage into a blue-hour recital hall with warm practical lights in the distance. Maintain the same shot timing and bow motion.
TURN 2: Keep everything the same except slowly move the camera into an over-the-shoulder arc around the violinist while preserving the exact playing rhythm.
TURN 3: Keep the same scene and motion. Add subtle floating dust and richer reflections on the violin varnish. Do not change identity, jacket, or performance timing.

=== SAFETY / ELIGIBILITY CHECK ===
- Rights over uploaded media confirmed: yes
- Avatar / voice path appropriate: N/A
- Audio input type allowed on this surface: verify before relying on non-voice audio upload
- Policy risk: low
- Surface limitation note: use conversational turns in Flow, not fake API params
```
