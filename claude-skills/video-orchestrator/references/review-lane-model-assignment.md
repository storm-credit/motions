# Review Lane Model Assignment

Use this reference when the orchestrator is running a multi-agent review, refinement, or validation pass over the prompt-director skills.

The goal is to spend reasoning where it matters most:

- Use the strongest model for global arbitration and difficult tradeoffs.
- Use mid-cost models for model-specific specialist review.
- Use fast models for repetitive harness passes and packaging checks.

## Recommended Internal Roles

| Internal Role | Recommended Model Tier | Why |
|---|---|---|
| Orchestrator / Showrunner | `gpt-5.5` or current top reasoning model | Best for global tradeoffs, conflict resolution, and final arbitration |
| Model specialist reviewer | `gpt-5.4` for deep passes, `gpt-5.4-mini` for fast passes | Strong enough for model-specific review without paying top-tier cost every time |
| Harness runner | `gpt-5.4-mini` | Best for repeated PASS/WARN/FAIL checks across multiple cases |
| Final auditor | `gpt-5.5` or main thread model | Confirm whether remaining WARNs are worth patching |
| Packaging / validation / file checks | Shell + validator scripts | Deterministic and cheaper than language-model reasoning |

## Practical Assignment

### Fast Efficiency Pass

Use when you want quick coverage over many skills:

```text
Main thread: orchestrator
Specialists: gpt-5.4-mini
Validation: scripts + shell
```

Use this for:

- Initial sweep
- Re-check after small edits
- PASS/WARN/FAIL harness scans

### Deep Review Pass

Use when you want fewer, stronger opinions:

```text
Main thread: orchestrator
Specialists: gpt-5.4
Final arbitrator: gpt-5.5 or main thread
Validation: scripts + shell
```

Use this for:

- Structural changes
- Upload-readiness decisions
- Ambiguous model-specific tradeoffs

### Mixed Orchestra Pass

Use when you want both speed and depth:

```text
1. Fast lane specialists on gpt-5.4-mini find obvious WARNs.
2. Orchestrator patches only high-signal issues.
3. Deep lane specialist or final auditor confirms the result.
4. Shell validation and packaging finalize the release.
```

This is the preferred default for this repository.

## Mapping by Task Type

| Task | Best Lane |
|---|---|
| Trigger/description sanity | Fast lane |
| Template completeness | Fast lane |
| Continuity structure review | Mixed lane |
| Model-specific realism | Deep lane |
| PASS/WARN/FAIL harness | Fast lane |
| Final release gate | Deep lane + deterministic validation |

## Anti-Patterns

- Use the strongest model for every review pass.
- Use only fast models for final release arbitration.
- Re-run all specialists after every tiny patch.
- Spend model reasoning on deterministic checks that scripts already cover.

## Release Rule

Ship when all of the following are true:

1. No blocker findings remain.
2. Remaining WARNs are either patched or consciously accepted.
3. `Skill is valid!` passes for every skill.
4. `.skill` packages rebuild successfully.
5. The orchestrator can explain why each lane used its assigned model tier.
