# Creative Specialist Modes

Use this reference when the user wants not only a model expert, but also a genre or directing expert layered on top of the model workflow.

Pick one primary mode by default:

- `music video`
- `film`
- `animation`

Add a secondary mode only when the user explicitly blends formats, such as `animated music video` or `cinematic anime teaser`.

## Shared Rule

The creative specialist never replaces the model specialist. It shapes the packet by adding the right directing priorities, timing logic, and audit rules.

Every final packet should explicitly say:

```text
Creative Director Mode:
Primary specialist:
Secondary specialist (if any):
Why this mode:
```

## Music Video Director

Use when:

- The user mentions MV, music video, performance clip, dance, chorus, beat drop, lyric mood, or reel built around music.
- Rhythm, cuts, gesture timing, fashion, glamour, or hook retention matter more than dialogue realism.

Core question:

- What musical section is this clip serving, and what emotional or visual payoff lands on the beat?

For the full MV packet schema, read `music-video-director-mode.md`.

Required additions:

- `Song section`: intro / verse / pre-chorus / chorus / post-chorus / bridge / outro
- `Performance vs narrative ratio`
- `Beat map`: accent points, beat-drop moments, cut-on-beat notes
- `Movement signature`: dance phrase, walk cycle, instrument gesture, hair/fabric motion
- `Hero motif`: prop, color, repeated camera move, or repeated stage image
- `Lip-sync policy`: exact, implied, or none

Model emphasis:

- `Seedance`: strongest for full MV packets, beat map, multi-shot rhythm, and audio-aware sequences
- `Kling`: strongest for choreography continuity, camera movement, and extensions
- `Veo`: strongest for glamour inserts, iconic hero closeups, and single emotional hits
- `Sora`: strongest for visual-concept alternates, stylized dream beats, and memorable version B

Audit checks:

- Does the hook land in the first 1.5 seconds?
- Do shot changes align with musical accents?
- Does movement repeat intentionally instead of drifting randomly?
- Is the chorus or drop visually distinct from verse energy?

## Film Director

Use when:

- The user wants movie-like, drama, cinematic scene, teaser, trailer beat, suspense, dialogue scene, or character-driven narrative.
- Geography, motivation, subtext, or coverage logic matter more than pure visual spectacle.

Core question:

- What changes for the character by the end of the shot or scene?

For the full narrative and cinematography schema, read `film-director-mode.md`.

Required additions:

- `Scene objective`
- `Dramatic turn`
- `Blocking geography`
- `Lens plan`: wide / medium / close progression, or fixed-lens rationale
- `Eyeline / screen direction`
- `Cut motivation`: reveal, emotional reaction, spatial clarification, impact
- `Subtext note`: what the character feels but does not say

Model emphasis:

- `Veo`: strongest for hero moments, emotionally precise inserts, and controlled first/last-frame beats
- `Sora`: strongest for atmospheric filmic interpretation and unforgettable cinematic imagery
- `Seedance`: strongest for multi-shot scene assemblies with continuity and audio logic
- `Kling`: strongest for physically coherent movement across beats, entrances, exits, and transitions

Audit checks:

- Is the dramatic objective visible on screen?
- Does blocking make spatial sense?
- Does the camera size/move support the emotional turn?
- Do the start and end states feel like part of one dramatic action?

## Animation Director

Use when:

- The user wants anime, stylized 2D/3D, toon, painterly, stop-motion-like, CG short, or family-animation energy.
- Silhouette clarity, expression design, or stylized motion matters more than live-action realism.

Core question:

- What stylization rules make this world readable and stable from shot to shot?

For the full animation look/performance schema, read `animation-director-mode.md`.

Required additions:

- `Animation medium`: anime / painterly 2D / stylized 3D / stop-motion-like / hybrid
- `Shape language`: round / angular / elegant / chunky / graphic
- `Line/render rule`: clean line, soft paint, cel-shaded, textured, etc.
- `Pose rhythm`: pose-to-pose, floaty, snappy, weighted, exaggerated
- `Expression rule`: eye shape, mouth logic, reaction intensity
- `Effects rule`: speed lines, glow, smear, squash/stretch, particles

Model emphasis:

- `Sora`: strongest for broad stylized reinterpretation and atmosphere-heavy animation moods
- `Veo`: strongest for one locked stylized hero shot with clear beginning and ending poses
- `Kling`: strongest for preserving pose continuity and action arcs when motion readability is critical
- `Seedance`: strongest for longer animated sequences when audio rhythm and repeated visual rules matter

Audit checks:

- Is the stylization rule explicit enough to prevent drifting back to live action?
- Are silhouette and pose readable at a glance?
- Are exaggeration and effects intentional rather than random artifacts?
- Is expression intensity consistent with the chosen animation mode?

## Hybrid Examples

Use these only when the user clearly blends categories:

- `animated music video`: primary `music video`, secondary `animation`
- `cinematic anime teaser`: primary `animation`, secondary `film`
- `concert-film trailer`: primary `film`, secondary `music video`

When using a hybrid, keep one mode primary and say what the secondary mode is allowed to influence.
