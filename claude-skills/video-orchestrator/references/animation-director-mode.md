# Animation Director Mode

Use this reference when the project is anime, toon, painterly 2D, stylized 3D, stop-motion-like, or hybrid 2.5D.

## Core Question

What stylization rules make this world readable and stable from shot to shot?

## Required Packet Additions

### Animation Look Bible

- `animation_family`
- `render_mode`
- `line_treatment`
- `shading_model`
- `background_treatment`
- `deformation_budget`
- `pose_language`
- `fx_language`
- `forbidden_style_drift`

Defaults:

- `anime -> 2D cel, 2-tone shading, crisp line, restrained smear`
- `toon -> squash/stretch medium, pose contrast high`
- `stylized_cg -> volume preserving, cel or stylized PBR`
- `hybrid_2_5d -> layered parallax, limited camera roll`

### Animation Performance

- `acting_beat`
- `key_pose_A_B_C`
- `contact_pose`
- `hold_feel`
- `accent_frames`
- `mouth_activity`
- `phoneme_density`
- `secondary_action`
- `fx_beat`
- `parallax_intent`
- `silhouette_goal`

Defaults:

- Dialogue shots: max `2` acting beats per `4-6s`
- Action shots: max `3` key poses
- `anime` favors holds plus accents
- `toon` favors broader arcs
- `CG` favors smoother arcs

### Animation Asset Pack / Model Sheet Pack

- `hero_model_sheet`
- `turnaround_views`
- `expression_sheet`
- `mouth_chart`
- `hand_shape_sheet`
- `prop_orthos`
- `layout_board`
- `color_script`
- `animatic_or_storyboard`
- `asset_priority`
- `platform_binding_method`

Defaults:

- Every recurring hero should have at least `front + 3/4` coverage.
- Every story-critical prop should have an ortho lock.
- If visual sheets are missing, synthesize a text proxy and warn.

## Routing Defaults

- `Seedance 2.0`: longer animated sequences with multimodal references and segment-level style locks
- `Kling 3.0`: pose continuity, multi-angle element binding, and readable action arcs
- `Veo 3.1`: stylized hero shots, asset-image-guided heroes, and extend plans
- `Sora 2`: stylized interpretation, alternate visual worlds, and non-human character asset control paths

## Audit

- No off-model silhouette drift.
- No line boil or line dropout unless intentionally textured.
- No shadow flip or highlight jump.
- No BG/character style mismatch.
- No rig break, joint pop, or parallax mismatch.
- No prop-scale drift.
- No silent fallback into photoreal live action.
