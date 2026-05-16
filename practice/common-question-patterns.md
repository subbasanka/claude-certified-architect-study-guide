# Common Question Patterns

Recognize these patterns quickly to orient yourself in the exam.

---

## Pattern 1 — High-Stakes Compliance

**Look for:** refunds, transfers, identity verification, sanctions, account closure, policy thresholds, or security-sensitive actions.

**Likely answer:** Deterministic enforcement (hooks, gates, tool interception).

**Why prompts fail here:** Probabilistic compliance is not compliance.

## Pattern 2 — Ambiguous Tool Routing

**Look for:** similar tools, vague tool descriptions, or incorrect tool choice.

**Likely answer:** Improve tool descriptions and contracts.

**Why classifiers are wrong:** The routing problem is usually in the tool metadata, not a missing routing layer.

## Pattern 3 — Fabricated Structured Fields

**Look for:** valid JSON but incorrect or invented values.

**Likely answer:** Schema design — nullable fields, enum changes, or source-grounded validation.

**Why "don't fabricate" prompts fail:** The model fabricates because the schema demands a value that doesn't exist in the source.

## Pattern 4 — Missing Categories in Multi-Agent Research

**Look for:** subagents that performed correctly but did not cover all expected topics.

**Likely answer:** Coordinator decomposition.

**Why blaming synthesis is wrong:** If subagents did their assigned work correctly, the gap is in what was assigned.

## Pattern 5 — Context Degradation

**Look for:** long sessions, vague references, forgotten exact values, or loss of earlier findings.

**Likely answer:** Externalize state — persistent facts, scratchpads, or structured summaries.

**Why larger context is wrong:** The problem is not capacity but attention/dilution over long sequences.
