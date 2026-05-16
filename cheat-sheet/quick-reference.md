# Claude Certified Architect — Quick Reference

A lightweight companion to the full [15-page PDF cheat sheet](claude_architect_cheat_sheet.pdf). Use this for a final 5-minute review before the exam.

---

## Universal Reflexes

Ask these before choosing any answer:

1. What is the failure mechanism?
2. Which architectural layer owns the fix?
3. Is this high-stakes enough to require deterministic enforcement?
4. Is the proposed answer fixing the root cause or tuning around it?
5. Is this a categorical problem being treated with a quantitative tweak?
6. Is information reaching the component that needs it?
7. Did the question explicitly say another component worked correctly?
8. Can I identify the scenario in the first 1-2 sentences?

---

## Scenario Recognition (First 1-2 Sentences)

| Opening Pattern | Scenario | First Instinct |
|-----------------|----------|---------------|
| Customer support agent | High-stakes + facts + disambiguation | Check for enforcement needs |
| Claude Code generating code | CLAUDE.md + commands + workflows | Check config scope |
| Coordinator and subagents | Decomposition + attribution + scoping | Check coordinator logic |
| Developer exploring codebase | Grep/Glob + scratchpads + context | Check search strategy |
| CI pipeline or PR review | Print mode + JSON + independent session | Check invocation mode |
| Extraction system with schema | Nullable + enum + validation | Check schema design |

---

## Correct-Answer Families

| Category | Answer Pattern |
|----------|---------------|
| High-stakes compliance | Runtime hook or gate (100% enforcement) |
| Tool routing confusion | Improve tool descriptions and boundaries |
| Fabricated required field | Make field nullable/optional in schema |
| Enum doesn't fit document | Add `other` or `unclear` enum value |
| Missing research categories | Fix coordinator decomposition |
| Exact values lost in conversation | Persistent facts block (verbatim, never summarised) |
| Team-wide coding standards | Project-level CLAUDE.md |
| Personal preferences | User-level ~/.claude/CLAUDE.md |
| Self-review bias | Two independent Claude sessions |
| CI pipeline hangs | `-p` flag (print mode) |
| Machine-parseable CI output | `--output-format json` with `--json-schema` |
| Latency-tolerant bulk work | Batch API |
| Context degradation in long sessions | Scratchpad files + fresh session with summary |
| Subagent can't be spawned | `allowedTools` missing `Task` |
| Forced first tool call | `tool_choice: {type: 'tool', name: 'X'}` |

---

## Auto-Eliminate (Almost Always Wrong)

| Trap Answer | Why |
|-------------|-----|
| Use a more powerful model | Capability doesn't fix architecture |
| Increase context window | Capacity doesn't fix structure; lost-in-middle still applies |
| Strengthen prompt for high-stakes | Probabilistic can't enforce non-negotiable rules |
| Add confidence threshold to prompt | Vague instruction antipattern |
| Ask the model to "be more careful" | Vague instruction in disguise |
| Retry for genuine data absence | Can't surface what doesn't exist |
| Pick ambiguous match by recency | Heuristic disambiguation — ask for identifier |
| Average conflicting statistics | Methodologies differ; averaging is meaningless |
| Give every subagent every tool | Scope violation; causes confusion |
| Read every file upfront | Context-budget killer |
| Batch API for blocking workflows | 24-hr SLA breaks real-time/CI |
| Sentiment-based escalation | Frustration doesn't equal case complexity |
| Terminate pipeline on any failure | Throws away partial results |

---

## The 5 Domains (Weight)

| Domain | Weight | One-Line Summary |
|--------|--------|-----------------|
| 1. Agentic Architecture | ~25% | Loops, decomposition, hooks, parallel execution |
| 2. Tool Design & MCP | ~20% | Descriptions, contracts, scoping, build vs reuse |
| 3. Claude Code Workflows | ~20% | CLAUDE.md scope, skills, plan/direct, CI modes |
| 4. Prompt & Structured Output | ~20% | Schema design, few-shot, nullable, batch API |
| 5. Context & Reliability | ~15% | Persistent facts, partial failures, attribution, eval |

---

## Final Exam-Day Principle

**Recognize the scenario first. Match the symptom signature. Verify against options — don't search options for the answer.**

The PDF cheat sheet has the full pattern tables. This page is your last-look reminder of the reflexes.
