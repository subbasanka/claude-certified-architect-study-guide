# Claude Certified Architect (Foundations) — Study Guide

[![Claude Certified Architect - Passed](https://img.shields.io/badge/Claude_Certified_Architect-Passed-blue.svg)](https://verify.skilljar.com/c/dv93ugng74jx)

A **pattern-recognition study guide** for the Claude Certified Architect (Foundations) exam, focused on architectural reasoning rather than memorization.

I passed the exam and created this repository to help others prepare with a practical, scenario-based approach.

> The exam becomes much easier when you recognize the scenario, identify the failure mechanism, and choose the intervention at the correct architectural layer.

---

## Exam Overview

The **Claude Certified Architect (Foundations)** is a certification exam offered by Anthropic that validates your ability to design and reason about production systems built with Claude.

| Detail | Info |
|--------|------|
| **Provider** | Anthropic |
| **Cost** | Free |
| **Format** | Multiple-choice, proctored |
| **Registration** | [claudecertifications.com](https://claudecertifications.com/) |
| **Preparation** | [Anthropic Academy / Skilljar](https://anthropic.skilljar.com/) |

### Exam Domains and Weights

| Domain | Weight | What It Tests |
|--------|--------|---------------|
| 1. Agentic Architecture & Orchestration | 27% | Agent loops, stop conditions, coordinator decomposition, parallel execution, handoffs, hooks |
| 2. Tool Design & MCP Integration | 18% | Tool contracts, error semantics, routing, scoping, build vs reuse decisions |
| 3. Claude Code Configuration & Workflows | 20% | CLAUDE.md scope, commands, skills, plan/direct/hybrid modes, CI invocation |
| 4. Prompt Engineering & Structured Output | 20% | Schema design, nullable fields, few-shot examples, validation retry, batch API |
| 5. Context Management & Reliability | 15% | Persistent facts, partial failure handling, source conflicts, evaluation strategy |

### What Background Helps

- Familiarity with Claude's API and tool use
- Understanding of agentic architecture patterns (orchestration, delegation, multi-agent)
- Experience with Claude Code or similar AI-assisted development workflows
- General knowledge of prompt engineering and structured outputs

---

## What This Repository Contains

| Folder | Contents |
|--------|----------|
| [`cheat-sheet/`](cheat-sheet/) | 15-page pattern-recognition cheat sheet (PDF) + quick-reference markdown |
| [`notes/`](notes/) | Domain-specific study notes covering all five exam domains |
| [`practice/`](practice/) | Scenario reasoning, wrong-answer elimination, and practice methods |
| [`resources/`](resources/) | Recommended links and full credits |

The **cheat sheet PDF** is the core artifact — it maps every question signature to its answer family across all 5 domains and 6 scenarios, with auto-eliminate wrong-answer patterns.

## Who This Is For

This guide is for anyone preparing for the Claude Certified Architect Foundations exam who wants to strengthen their understanding of:

- Agentic architecture and orchestration
- Tool design and MCP integration
- Claude Code configuration and workflows
- Prompt engineering and structured outputs
- Context management and reliability
- CI/CD workflows using Claude
- Multi-agent research and synthesis systems

## My Biggest Exam Insight

The exam is not just about Claude feature recall. It repeatedly tests whether you can identify:

- The true failure mechanism
- The correct layer for intervention
- When prompts are insufficient and deterministic controls are required
- Whether a proposed fix is structural or only a quantitative tweak
- How to reason through agent, tool, schema, and context failures

**Key principles:**

| Symptom | Wrong Instinct | Right Fix |
|---------|---------------|-----------|
| High-stakes action violated | Stronger prompt | Hooks, gates, or schema-level enforcement |
| Tool routing confusion | Add a classifier | Improve tool descriptions and contracts |
| Context loss in long conversations | Larger context window | Persistent facts block or structural memory |
| Multi-agent missing categories | Blame synthesis agent | Fix coordinator decomposition |

## Quick Start

1. Read the [Pattern Recognition Cheat Sheet](cheat-sheet/claude_architect_cheat_sheet.pdf)
2. Review the five domain notes in [`notes/`](notes/)
3. Study the scenario patterns in [`notes/scenario-patterns.md`](notes/scenario-patterns.md)
4. Practice wrong-answer elimination using [`practice/elimination-strategies.md`](practice/elimination-strategies.md)
5. Review the credited resources in [`resources/recommended-links.md`](resources/recommended-links.md)

## Repository Structure

```text
.
├── README.md
├── cheat-sheet/
│   ├── claude_architect_cheat_sheet.pdf
│   └── quick-reference.md
├── notes/
│   ├── domain-1-agentic-architecture.md
│   ├── domain-2-tool-design-mcp.md
│   ├── domain-3-claude-code-workflows.md
│   ├── domain-4-prompt-engineering-structured-output.md
│   ├── domain-5-context-management-reliability.md
│   └── scenario-patterns.md
├── practice/
│   ├── common-question-patterns.md
│   ├── elimination-strategies.md
│   └── practice-method.md
├── resources/
│   ├── recommended-links.md
│   └── credits.md
├── CONTRIBUTING.md
├── DISCLAIMER.md
└── LICENSE
```

## Core Mental Model

When reading a question, ask:

1. What system is failing?
2. Which layer owns that failure?
3. Is the failure probabilistic or deterministic?
4. Are the stakes high enough to require enforcement instead of prompting?
5. Is the proposed solution fixing the root cause or only tuning around it?
6. Is this a context, schema, tool, orchestration, or configuration problem?

## Resources That Helped Me

- [Claude Certifications](https://claudecertifications.com/) — free prep material and learning paths
- [Anthropic Academy / Skilljar](https://anthropic.skilljar.com/) — official learning platform
- [X thread by @hooeem](https://x.com/hooeem/status/2033198345045336559) — community prep perspective
- [Towards AI Complete Guide](https://pub.towardsai.net/claude-certified-architect-the-complete-guide-to-passing-the-cca-foundations-exam-9665ce7342a8) — exam-domain framing
- [paullarionov/claude-certified-architect](https://github.com/paullarionov/claude-certified-architect) — community study materials

Full credits: [`resources/credits.md`](resources/credits.md)

## Ethical Use

This repository does **not** contain exam dumps, leaked questions, or guaranteed answers.

It contains personal preparation notes, study patterns, and architectural reasoning guidance based on my learning process. Use it to understand the concepts, not to memorize answers.

## Contributing

Contributions are welcome if they improve conceptual clarity, correct mistakes, or add better study explanations. See [`CONTRIBUTING.md`](CONTRIBUTING.md) for guidelines.

## License

[MIT](LICENSE)
