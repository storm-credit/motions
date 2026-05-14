# Prompt Director Skill Pack

This repository contains a Claude/Codex-compatible AI video prompt director skill pack.

The pack is organized in two layers:

- `video-orchestrator`: top-level showrunner that chooses the best model/tool route.
- `*-prompt-director`: model-specific prompt directors that produce paste-ready prompt packets.

## Official Doc Sync

As of `2026-05-14`, the model-specific prompt directors were re-checked against current official docs for:

- `Seedance 2.0`
- `Kling 3.0`
- `Google Veo 3.1`
- `Sora 2`

See `OFFICIAL_DOC_SYNC_NOTES.md` for the exact sources reviewed and the capability/constraint changes that were tightened in the skills.

## Skill Files

Upload these `.skill` packages individually when you want them available as separate Claude skills:

- `dist/video-orchestrator.skill`
- `dist/seedance-prompt-director.skill`
- `dist/kling-prompt-director.skill`
- `dist/veo-prompt-director.skill`
- `dist/sora-prompt-director.skill`

## Intended Use

Use `video-orchestrator` when the user has not chosen a model and wants the system to decide.

Use a specific director when the user already knows the target model:

- Seedance-style multi-shot prompt packet: `seedance-prompt-director`
- Kling-style motion/extension prompt packet: `kling-prompt-director`
- Veo-style precise hero-shot prompt packet: `veo-prompt-director`
- Sora-style cinematic visual prompt packet: `sora-prompt-director`

## Expected Output Pattern

Every director skill should produce:

1. A locked continuity bible.
2. A shot or scene plan.
3. A model-ready final prompt block.
4. Negative constraints.
5. Ending bridge state.
6. Continuity audit.

The director skills are intentionally not just "advice" skills. They are prompt production skills.

## Orchestra Review Policy

This pack is maintained with an orchestra-style review lane:

- `Orchestrator / Showrunner`: top reasoning lane for arbitration and final decisions.
- `Model-specific specialists`: medium or fast reasoning lane depending on the pass.
- `Harness passes`: fast lane for repeated PASS/WARN/FAIL checks.
- `Validation / packaging`: deterministic scripts and shell commands.

Preferred default:

```text
Fast lane specialists -> orchestrator patches -> final validation
```

Deep lane is used only when structural ambiguity or release risk is high.

## Recommended Workflow

```text
Idea
-> video-orchestrator if model is unknown
-> selected prompt director
-> paste-ready prompt packet
-> generation
-> repair with Kling Edit / Motion Control / DOP if needed
```

## Current Director Roles

| Skill | Main Job |
|---|---|
| `seedance-prompt-director` | Continuity-locked multi-shot Seedance 2.0 prompt packets |
| `kling-prompt-director` | Motion-safe Kling 3.0 prompt packets and extension/edit handoffs |
| `veo-prompt-director` | Precise Veo 3.1 hero-shot and first/last-frame prompt packets |
| `sora-prompt-director` | Cinematic Sora 2 prompt packets with style-safe alternatives |

## Local Source

Skill source folders live in:

```text
claude-skills/
```

Packaged upload files live in:

```text
dist/
```
