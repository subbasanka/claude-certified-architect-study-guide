# Wrong-Answer Elimination Strategies

When reviewing multiple-choice options, eliminate answers that propose the wrong layer of fix.

---

## Usually Wrong Unless Strongly Justified

These answers are almost always incorrect in the exam context:

- "Use a more powerful model"
- "Increase the context window"
- "Strengthen the prompt" for high-stakes guarantees
- "Add confidence thresholds" without calibration
- "Ask the model to be more careful"
- "Retry more times" for genuine absence of data
- "Pick ambiguous matches by recency or activity"
- "Average conflicting statistics"
- "Give every subagent every tool"
- "Read every file upfront"
- "Use batch for blocking workflows"

---

## Layer-Mismatch Examples

| Symptom | Bad Fix (Wrong Layer) | Better Fix (Right Layer) |
|---------|----------------------|--------------------------|
| Refund policy occasionally violated | Stronger prompt | Tool-call hook / runtime gate |
| Required absent field fabricated | Prompt says "do not fabricate" | Nullable schema field |
| Tool misroutes between similar tools | Add classifier | Improve descriptions and boundaries |
| Missing research categories | Blame synthesis | Fix coordinator decomposition |
| Long conversation loses exact values | Larger context | Persistent facts block |
| CI hangs | Longer timeout | Non-interactive print mode |

---

## Elimination Decision Tree

```text
Is the answer "use a stronger prompt" for a high-stakes scenario?
  → Almost certainly wrong. Look for enforcement mechanisms.

Is the answer "increase context/model size"?
  → Almost certainly wrong. Look for structural information management.

Is the answer adding complexity (classifier, extra agent) to solve a description problem?
  → Likely wrong. Look for simpler contract/description improvements.

Does the answer blame a component the question says worked correctly?
  → Definitely wrong. Look upstream at coordination or input.

Is the answer a quantitative tweak (more retries, higher threshold) for a categorical problem?
  → Likely wrong. Look for structural/schema-level changes.
```

---

## The "Root Cause" Test

Before selecting an answer, ask: "Does this fix the root cause or just reduce the symptom frequency?"

- **Root-cause fix:** Changes the architecture, schema, or control flow so the failure cannot recur
- **Symptom reduction:** Lowers probability of failure without eliminating the mechanism
