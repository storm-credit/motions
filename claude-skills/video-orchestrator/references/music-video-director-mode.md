# Music Video Director Mode

Use this reference when the project is primarily a music video, performance clip, dance clip, lyric-driven short, or chorus-first social cut.

## Core Question

What musical section is this clip serving, and what visual payoff lands on the beat?

## Required Packet Additions

### Music Structure

- `track_source`
- `rights_status`
- `BPM`
- `time_signature`
- `section_map`
- `lyric_priority_lines`
- `sync_priority`
- `section_energy`

Defaults:

- If BPM is unknown, infer from supplied audio or use `120`.
- If time signature is unknown, use `4/4`.
- Every musical section must have at least one assigned visual function.

### Performance Coverage

- `shot_role`: performance / narrative / detail / transition
- `artist_visibility`
- `lip_sync_mode`
- `lyric_excerpt`
- `dance_dependency`
- `count_in`
- `count_out`
- `full_body_required`
- `hands_feet_visibility`
- `formation_rule`
- `fallback_cutaway`

Defaults:

- `lip_sync_mode: implied`
- `fallback_cutaway: insert/profile`
- For choreography-led choruses, `full_body_required: yes`

### Refrain Plan

- `chorus_anchor_shot_id`
- `repeat_count`
- `must_match_locks`
- `allowed_variation`
- `motif_callback`
- `final_chorus_escalation`
- `thumbnail_frame`
- `loop_out_frame`

Defaults:

- Early choruses should get one exact-repeat anchor.
- Final chorus may escalate once in camera, performance, or FX density.

### Delivery Variants

- `master_aspect`
- `social_aspect`
- `center_safe_zone`
- `text_safe_zone`
- `crop_safe_blocking`
- `reframe_fallback`

Default:

- If the output may be cut down for Reels, Shorts, or TikTok, block every hero performance shot to survive a 9:16 crop even when the master is 16:9.

### Rights / Eligibility

- `performer_type`
- `real_person_rights_confirmed`
- `track_rights_confirmed`
- `audio_source_type`
- `face_input_required`
- `target_model_allows_input`
- `copyright_risk`

Default:

- `audio_source_type: original_or_licensed_only`

## Routing Defaults

- `Seedance 2.0`: base multi-shot MV segments, beat-map packets, audio-aware sequences
- `Kling 3.0`: dance continuity, choreography extensions, movement stabilization
- `Veo 3.1`: hero inserts, glamour closeups, emotional bridge lifts
- `Sora 2`: concept interludes, alternate worlds, stylized Version B

## Audit

- Every bar or phrase is assigned to a visual role.
- Every chorus has an anchor shot.
- Lyric-critical lines do not land on weak-sync coverage.
- Dance shots preserve feet visibility and travel direction.
- Repeated chorus shots match wardrobe, hair, light, and camera language unless the escalation is intentional.
