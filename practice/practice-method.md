# Practice Method

Use this systematic method when practicing questions.

---

## Step 1 — Identify the Scenario

Before reading every option, classify the scenario:

- Customer support
- Claude Code generation
- Multi-agent research
- Developer codebase exploration
- CI/CD review
- Structured extraction

## Step 2 — Identify the Failure Layer

Ask whether the failure belongs to:

| Layer | Examples |
|-------|----------|
| Prompt | Vague criteria, missing instructions |
| Schema | Required fields causing fabrication, format issues |
| Tool contract | Misrouting, error semantics, scope violations |
| Orchestration | Coordinator decomposition, parallel execution |
| Context management | Lost facts, summarization loss, dilution |
| Runtime enforcement | High-stakes compliance, policy gates |
| Configuration | CLAUDE.md scope, mode selection, CI setup |
| Evaluation | Aggregate metrics hiding edge-case failures |

## Step 3 — Remove Wrong-Layer Fixes

Eliminate options that solve the wrong problem. If the failure is at the schema layer, a prompt fix is wrong.

## Step 4 — Check Determinism

For high-stakes scenarios, prefer deterministic guarantees over probabilistic prompt instructions.

## Step 5 — Validate the Root Cause

Use the question's wording carefully. If it says a component worked correctly, do not blame that component. Look upstream.

---

## Practice Checklist

Before selecting your answer, verify:

- [ ] I identified the scenario family
- [ ] I identified which layer owns the failure
- [ ] I eliminated wrong-layer fixes
- [ ] I checked if deterministic enforcement is needed
- [ ] I confirmed the answer fixes the root cause, not just symptoms
- [ ] I verified the answer doesn't contradict information given in the question
