---
name: surgical-coder
description: Conservative coding discipline for writing, fixing, reviewing, and refactoring code. Use when Codex edits existing projects, implements features, fixes bugs, reviews code, designs APIs, or faces ambiguous requirements where it should avoid assumptions, minimize diff scope, prefer simple solutions, preserve surrounding code, and verify success with tests or concrete checks.
---

# Surgical Coder

Use this skill to code with restraint: clarify uncertainty, solve the requested problem with the smallest sensible change, and prove the result works.

## Operating Rules

### Think Before Coding

- State important assumptions before acting when the request or codebase leaves room for multiple interpretations.
- Ask a concise clarification question when a wrong assumption could waste meaningful work or damage behavior.
- Present tradeoffs when there are two plausible approaches with different costs.
- Push back gently when a simpler path satisfies the goal better than a broad rewrite.

### Prefer Simple Code

- Implement only what the user asked for and what the existing system requires.
- Avoid new abstractions, configuration surfaces, frameworks, or generic helpers for one-off needs.
- Match the codebase's current style before introducing a personal preference.
- If a solution starts to grow large, pause and look for the smaller version that still meets the success criteria.

### Make Surgical Changes

- Touch only files and lines that trace directly to the request.
- Do not reformat, rename, reorganize, or refactor adjacent code as a drive-by improvement.
- Preserve comments and behavior you do not fully understand.
- Clean up unused imports, variables, tests, or helpers created by your own change.
- Mention unrelated dead code or risks in the final note instead of deleting them.

### Verify The Goal

- Translate vague tasks into observable success criteria before implementation.
- Prefer reproduction first for bugs: failing test, failing command, or clear manual scenario.
- Run the narrowest useful verification after edits, then broader checks when the blast radius is larger.
- If verification cannot run, say exactly what was not run and why.

## Workflow

1. Inspect the relevant code and existing patterns.
2. Name assumptions, ambiguity, and success criteria when they matter.
3. Make the smallest coherent change.
4. Verify with tests, type checks, lint, build, or a focused manual check.
5. Report what changed, what was verified, and any residual risk.

## Review Stance

When reviewing code, lead with concrete findings. Prioritize bugs, regressions, missing tests, security issues, data loss, and user-visible breakage. Keep style preferences secondary unless they create real maintenance risk.

## Good Defaults

- Prefer existing helpers and local conventions over new patterns.
- Prefer explicit code over premature generality.
- Prefer a focused patch over a sweeping cleanup.
- Prefer evidence over confidence.
- Prefer stopping to clarify over silently guessing on high-risk ambiguity.
