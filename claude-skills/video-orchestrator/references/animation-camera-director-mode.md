# Animation Camera Director Mode

Use this reference when animation work depends on camera grammar, multiplane depth, parallax readability, or layout-safe action staging.

## Core Question

What camera rules make this animated world feel dynamic without breaking silhouette, layout, or depth logic?

## Required Packet Additions

Before hero generation, require an animation-camera report with:

- `status / decision`
- `staging readability`
- `parallax legality`
- `move risk`
- `go / hold / revise`

### Animation Camera Package

- `staging_depth_plan`
- `parallax_tiers`
- `layout_anchor`
- `horizon_rule`
- `lens_equivalent_feel`
- `roll_limit`
- `pan_speed_rule`
- `push_pull_rule`
- `orbit_legality`
- `perspective_distortion_budget`
- `action_axis`
- `verticality_budget`
- `impact_move_policy`
- `foreground_wipe_policy`

Defaults:

- `anime`: restrained roll, deliberate push-ins, readable lateral pans, impact moves only on reveals or power beats
- `toon`: broader swings allowed, stronger push/pull exaggeration, but keep staging readable
- `stylized_cg`: smoother orbits allowed, distortion budget medium, foreground wipe only when depth is clear
- `hybrid_2_5d`: prioritize multiplane slides, limited roll, limited orbit, strong layout anchors

### Shot-Language Rules

- `opener_move`
- `hero_move`
- `transition_move`
- `impact_move`
- `forbidden_move`
- `camera_motivation`
- `panel_sequence_logic`

Defaults:

- Dialogue-heavy shots: one main move only
- Action-heavy shots: one hero move plus one accent move max
- If the move cannot be drawn as clear storyboard panels, simplify it

### Staging + Parallax Checks

- `silhouette_readability`
- `foreground_midground_background_lock`
- `parallax_sync_rule`
- `line_of_action_visibility`
- `screen_direction_protection`
- `crop_safe_motion`

Defaults:

- Keep the action line readable at every key pose
- Do not let background motion overpower character intent
- Protect the 180-degree line unless a deliberate break is staged

## Routing Defaults

- `Kling 3.0`: first choice when action readability and camera/action sync are the priority
- `Seedance 2.0`: use when the same camera grammar must continue across a multi-shot sequence or music-led beat map
- `Veo 3.1`: use when one premium stylized hero move carries the whole shot
- `Gemini Omni Flash`: use when the operator is transforming an animatic, previz, or source clip conversationally on Google surfaces
- `Sora 2`: use when the camera mood itself is exploratory and stylized interpretation is desired
- `Higgsfield DOP`: add only as a camera boost layer after the main route is already stable

## Audit

- No unreadable parallax wobble.
- No roll beyond the chosen budget.
- No layout break that destroys line of action.
- No camera drift that feels unmotivated.
- No foreground wipe that hides the key acting beat.
- No pseudo-live-action move that conflicts with the chosen animation family.

## Animation Camera Execution Gates

- `Report -> Plan`: block hero planning until staging depth, roll limits, and move legality are explicit.
- `Plan -> Previz`: require a board-like move description and key pose visibility check.
- `Previz -> Hero`: promote only shots that preserve silhouette, screen direction, and parallax intent.
- `Hero -> Repair`: classify camera problems as timing, parallax, layout, or motivation errors before editing.
- `Final Release`: sign off only when the move reads clearly both as motion and as storyboard logic.
