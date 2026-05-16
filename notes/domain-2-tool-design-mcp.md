# Domain 2 — Tool Design and MCP Integration

**Focus areas:** tool descriptions, tool contracts, error semantics, tool scoping, MCP server selection, built-in tools vs MCP tools

---

## Key Patterns

### Tool Misrouting

If tools have vague or overlapping descriptions, improve tool descriptions first. Do not add a routing classifier as the first fix.

### Tool Contract Design

A valid empty result and an actual tool failure must be structurally different.

```json
{ "success": true, "data": [] }
```

versus:

```json
{ "isError": true, "errorCategory": "transient" }
```

### Tool Scope

Do not give every agent every tool. Keep tools scoped to the role. Add constrained cross-role tools only when justified.

### MCP Build vs Reuse

Evaluate existing MCP servers before building a custom one. "We want full control" alone is not a strong justification.

---

## Quick Reference Table

| Symptom | Root Cause | Fix |
|---------|-----------|-----|
| Wrong tool selected | Vague/overlapping descriptions | Improve tool descriptions and boundaries |
| Agent hallucinates after empty result | No distinction between empty and error | Structured success/error contract |
| Agent uses tool it shouldn't | Over-broad tool scoping | Scope tools per agent role |
| Team builds custom MCP unnecessarily | Not evaluating existing servers | Assess existing MCP ecosystem first |
