# Scenario Patterns

The exam often becomes easier once you identify the scenario family. Recognize the opening pattern, then apply the matching architectural fixes.

---

## 1. Customer Support Resolution Agent

Common patterns:

- High-stakes actions require hooks or runtime gates
- Explicit human requests should escalate
- Ambiguous customer records require additional identifiers
- Long conversations need persistent facts blocks
- Tool errors must distinguish valid empty results from failures

**Key question:** Is the failure about safety/compliance (needs enforcement) or information quality (needs context management)?

## 2. Claude Code Generation

Common patterns:

- Team standards belong in project CLAUDE.md
- Personal preferences belong in user-level CLAUDE.md
- Long task-specific procedures belong in commands or skills
- Broad refactors need plan mode
- Small known fixes can use direct execution

**Key question:** Is this a configuration scope issue or a workflow mode issue?

## 3. Multi-Agent Research System

Common patterns:

- Missing categories usually indicate coordinator decomposition failure
- Source attribution must be preserved structurally
- Synthesis agents should not receive every tool
- Partial failures must be surfaced through coverage annotations

**Key question:** Did the subagents fail, or did the coordinator fail to assign the right work?

## 4. Developer Productivity with Claude

Common patterns:

- Use Grep for content search
- Use Glob for filename or path-pattern search
- Do not read every file upfront
- Use scratchpad files for long explorations
- Use fresh sessions with summary injection when context degrades

**Key question:** Is the failure about finding information (search strategy) or retaining it (context management)?

## 5. Claude Code for CI/CD

Common patterns:

- Hanging CI often means non-interactive print mode is missing
- Machine-parseable output needs JSON output and schema
- Review should happen in an independent session
- Batch API is wrong for blocking CI review

**Key question:** Is this a mode/invocation issue or an output format issue?

## 6. Structured Data Extraction

Common patterns:

- Malformed JSON requires structured tool/schema output
- Fabricated absent fields require nullable schema fields
- Ambiguous enum categories need `other` or `unclear` options
- Validation retry helps with formatting, not missing information

**Key question:** Is the model hallucinating because of a schema design flaw or a genuine data absence?

---

## Scenario Recognition Cheat Sheet

| Opening Pattern | Likely Scenario | First Instinct |
|-----------------|----------------|----------------|
| Customer support agent | High-stakes + facts + disambiguation | Check for enforcement needs |
| Claude Code generating code | CLAUDE.md + commands + workflows | Check config scope |
| Coordinator and subagents | Decomposition + attribution + scoping | Check coordinator logic |
| Developer exploring codebase | Grep/Glob + scratchpads + context | Check search strategy |
| CI pipeline or PR review | Print mode + JSON + independent session | Check invocation mode |
| Extraction system | Schema + nullable + validation | Check schema design |
