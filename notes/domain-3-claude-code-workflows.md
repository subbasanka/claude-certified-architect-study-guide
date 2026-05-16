# Domain 3 — Claude Code Configuration and Workflows

**Focus areas:** CLAUDE.md scope, commands, skills, path-specific rules, plan mode vs direct execution, CI invocation, review workflows

---

## Key Patterns

### CLAUDE.md Scope

Use project-level CLAUDE.md for team standards. Use user-level CLAUDE.md for personal preferences.

### Commands and Skills

Always-loaded rules belong in CLAUDE.md. Task-specific procedures belong in commands or skills.

### Plan vs Direct Execution

| Mode | When to Use |
|------|-------------|
| Plan mode | Unclear, broad, or high-impact changes |
| Direct execution | Small, well-defined fixes |
| Hybrid mode | Large but patterned changes (e.g., migration across many files) |

### CI Workflows

For non-interactive CI usage, Claude should run in print mode and produce machine-parseable output when required.

### Independent Review

Do not use the same Claude session to generate and review code. Use a fresh independent review session to avoid self-review bias.

---

## Quick Reference Table

| Symptom | Root Cause | Fix |
|---------|-----------|-----|
| Team members have inconsistent standards | No shared config | Project-level CLAUDE.md |
| Personal prefs override team rules | Wrong config scope | User-level CLAUDE.md for personal only |
| CI pipeline hangs | Interactive mode in CI | Non-interactive print mode |
| Self-review misses issues | Same session bias | Independent review session |
| Large refactor goes wrong | No planning step | Plan mode before execution |
