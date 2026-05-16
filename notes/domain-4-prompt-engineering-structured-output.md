# Domain 4 — Prompt Engineering and Structured Output

**Focus areas:** categorical criteria, few-shot examples, structured outputs, schema design, validation retry, batch API, confidence calibration

---

## Key Patterns

### Vague Criteria

Replace instructions like "be conservative" or "only high confidence" with concrete include/exclude rules.

### Few-Shot Examples

Use a few targeted examples for ambiguous cases. Do not add dozens of exhaustive examples when a small set would clarify the boundary.

### Structured Output

Use tool schemas to prevent malformed JSON. But remember: schemas prevent syntax errors, not semantic fabrication.

### Nullable Fields

If a required field is fabricated when source data is absent, make the field optional or nullable. This is a schema fix, not a prompt fix.

### Validation Retry

Validation retry helps with format errors. It does not solve genuine information absence.

### Batch API

| Use Case | Batch API? |
|----------|-----------|
| Overnight reports, weekly audits | Yes |
| PR review CI, real-time chat | No — use synchronous API |

---

## Quick Reference Table

| Symptom | Root Cause | Fix |
|---------|-----------|-----|
| Model invents values for absent data | Required field with no source | Nullable/optional schema field |
| JSON output malformed | No schema enforcement | Tool schema or structured output |
| Inconsistent classification | Vague criteria | Concrete include/exclude rules |
| Classification boundary unclear | Ambiguous categories | Targeted few-shot examples |
| Format errors on retry | Syntax issue | Validation retry loop |
| CI blocks on batch API | Wrong API for latency | Switch to synchronous API |
