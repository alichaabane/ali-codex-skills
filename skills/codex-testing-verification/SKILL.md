---
name: codex-testing-verification
description: Testing and verification workflow for Codex. Use when Codex needs to choose, run, interpret, or report checks for code changes using project-defined tests, typechecks, lint, builds, manual verification, and clear risk reporting.
---

# Codex Testing Verification

Use this skill to choose, run, interpret, and report verification for code changes.

## Verification Workflow

1. Discover verification commands.
   - Inspect package scripts, Makefiles, task runners, CI config, docs, and project conventions.
   - Prefer project-defined commands over invented commands.
   - Note required environment, services, fixtures, or setup when visible.

2. Choose the right scope.
   - Run the narrowest useful check first.
   - Expand to related tests, typecheck, lint, build, or full suite when risk justifies it.
   - Match verification depth to the change size, affected area, and failure impact.

3. Verify behavior.
   - For bug fixes, confirm the failing case is covered.
   - For features, verify expected behavior and important edge cases.
   - For refactors, verify behavior remains unchanged.

4. Interpret results.
   - Separate failures caused by the change from pre-existing or unrelated failures.
   - Do not claim success when checks were skipped, unavailable, or inconclusive.
   - Treat flaky or partial results as lower confidence, not as clean passes.

5. Report clearly.
   - List commands run and outcomes.
   - Explain skipped checks and remaining risk.
   - Recommend follow-up verification when needed.

## Output

- State each command or manual check and its result.
- Summarize what behavior is verified.
- Call out failures, skipped checks, uncertainty, and recommended follow-up.
