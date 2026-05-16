# Domain 1 — Agentic Architecture and Orchestration

**Focus areas:** agent loops, stop conditions, subagent delegation, coordinator decomposition, parallel execution, tool-call interception, handoff design, multi-pass review architectures

---

## Key Patterns

### Stop Conditions

Use structured signals such as `stop_reason`, not natural language text like "I am done."

### Coordinator Decomposition

If subagents worked correctly but the final report is missing entire categories, the likely root cause is the coordinator's decomposition — it failed to assign coverage for those categories.

### Parallel Subagents

If independent subagents are running sequentially and latency is high, emit multiple task calls in a single coordinator response to enable parallel execution.

### High-Stakes Actions

For refunds, transfers, compliance checks, account closure, or policy enforcement, prompt instructions are not enough. Use deterministic enforcement such as hooks, gates, or tool interception.

### Handoff to Humans

A useful handoff is self-contained. Include: summary, customer/context identifiers, root cause, attempted actions, and recommendation.

---

## Quick Reference Table

| Symptom | Root Cause | Fix |
|---------|-----------|-----|
| Report missing categories | Coordinator decomposition gap | Fix task assignment in coordinator |
| High latency, independent tasks | Sequential execution | Parallel subagent dispatch |
| Policy violated occasionally | Prompt-only enforcement | Runtime hooks or gates |
| Agent never stops | NL-based stop condition | Structured `stop_reason` signal |
| Human gets incomplete handoff | Missing context in handoff | Self-contained handoff structure |
