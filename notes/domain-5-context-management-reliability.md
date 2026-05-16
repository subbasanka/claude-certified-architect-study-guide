# Domain 5 — Context Management and Reliability

**Focus areas:** long-context reliability, summarization loss, persistent facts, tool-result trimming, escalation, partial failure handling, source attribution, evaluation strategy

---

## Key Patterns

### Exact Facts

If exact values are lost in long conversations, preserve them in a persistent facts block included verbatim in every prompt.

### Lost in the Middle

Long documents may require restructuring: section headers, key findings up front, and targeted retrieval rather than dumping everything into context.

### Partial Failures

Do not silently suppress subagent or tool failures. Propagate structured errors, partial results, and coverage gaps.

### Source Conflicts

If two credible sources conflict, surface both with attribution and dates. Do not average incompatible statistics.

### Evaluation

Aggregate accuracy can hide weak spots. Segment metrics by document type, vendor, field, scenario, and confidence level.

---

## Quick Reference Table

| Symptom | Root Cause | Fix |
|---------|-----------|-----|
| Exact values drift in long sessions | Context dilution | Persistent facts block |
| Model ignores mid-document content | Lost-in-the-middle effect | Restructure, headers, targeted retrieval |
| Silent data gaps in output | Suppressed partial failures | Surface structured errors and coverage gaps |
| Contradictory stats reported | Conflicting sources merged | Attribute both with dates, do not average |
| Good aggregate but bad edge cases | Single-metric evaluation | Segment by type, field, scenario |
