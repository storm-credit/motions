# Orchestra Report -> Plan -> Execute

Use this reference when the user wants the Orchestrator to supervise the project, gather reports from specialists, build a plan, and execute according to that plan.

## Core Rule

Do not jump straight from a rough brief to final prompts when the project is multi-shot, specialist-heavy, or quality-sensitive.

The Orchestrator should move in this order:

```text
Brief
-> Lock Continuity
-> Readiness Report
-> Gather Specialist Reports
-> Build Orchestra Execution Plan
-> Build Pass Plan
-> Route Models / Tools
-> Generate Prompt Packets
-> Run Gates
-> Execute / Repair / Assemble
-> Final Audit
```

## Readiness Report Template

Use this before full planning.

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
```

## Specialist Report Template

Every active specialist should return a short structured report.

```text
=== SPECIALIST REPORT ===

Specialist:
Role:
Creative mode:
Owned shots / passes:

What this specialist wants:
- Primary objective:
- Required locks:
- Preferred model/tool:
- Preferred input path:

Main risks:
- Risk 1:
- Risk 2:
- Risk 3:

Avoid:
- Do not:
- Do not:

Fallback recommendation:
- If primary path fails:
- If continuity fails:

Success criteria:
- Must achieve:
- Nice to have:
```

## Orchestra Execution Plan Template

The Orchestrator consolidates all specialist reports into one execution plan.

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
- What must exist before the next step:

Conflict resolutions:
- Conflict:
  - Winner:
  - Reason:

Stop conditions:
- When to escalate:
- When to switch model:
- When to stop iterating:
```

## Pass Plan Template

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

Before expensive final generation, the Orchestrator should run these gates.

```text
=== EXECUTION GATES ===

Rights gate:
- Performer rights confirmed?
- Track / asset rights confirmed?
- Platform safety constraints legal?

Continuity gate:
- Character / wardrobe / prop locks complete?
- Start/end baton states complete?
- Crop-safe and delivery rules complete?

Capability gate:
- Chosen model supports the required input path?
- Required reference path is legal?
- Required resolution / aspect / duration are legal?

Previz gate:
- Cheap preview route defined?
- Success / failure signal defined?

Hero gate:
- Which shots deserve premium generation?
- What exact pass owner approves them?

Repair gate:
- Defect classification complete?
- Edit fallback defined?
- Motion fallback defined?
- Replacement shot fallback defined?

Final gate:
- Assembly order locked?
- Final audit owner assigned?
```

## Execution Log Template

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

## Default Ownership Pattern

- `Orchestrator / Showrunner`: final plan, conflict resolution, gating, and sign-off
- `Creative specialist`: genre-specific report and performance/cut logic
- `Model specialist`: model-specific prompt/report for owned shots, including Omni for surface-driven multimodal edit chains
- `Tool layer`: only executes repair, motion, DOP, or assembly tasks after the plan chooses them

## Anti-Patterns

- Gather reports and then ignore them
- Let every specialist re-plan the whole project
- Skip explicit ownership
- Use premium generation before a preview path exists
- Leave fallback undefined for hero shots
