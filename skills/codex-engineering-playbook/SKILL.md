---
name: codex-engineering-playbook
description: Codex-native engineering workflow for inspecting, editing, debugging, reviewing, refactoring, testing, or migrating a codebase through small changes, existing patterns, concrete verification, and clear risk reporting.
---

# Codex Engineering Playbook

Use this playbook to make code changes procedurally: inspect first, change narrowly, verify concretely, and communicate residual risk.

## Workflow

1. Inspect the repository before editing.
   - Identify the project structure, relevant files, existing conventions, and available test or build commands.
   - Check repository status and preserve unrelated user changes.
   - Discover canonical commands from project files, scripts, CI config, and docs.
   - Prefer fast search tools such as `rg` for finding files, symbols, and references.
   - Read surrounding code before changing it.

2. Define the work before touching files.
   - Restate the concrete goal when the request is broad or ambiguous.
   - Surface assumptions that affect implementation choices.
   - Ask only when missing information blocks a safe change.
   - For multi-step work, use a short plan with verification points.

3. Make small focused changes.
   - Edit only files required by the task.
   - Avoid drive-by formatting, unrelated cleanup, and speculative features.
   - Do not revert, overwrite, stage, or commit unrelated work unless explicitly asked.
   - Remove only unused code introduced by the current change unless asked otherwise.
   - Keep each change easy to review and easy to revert.

4. Reuse existing patterns.
   - Match local style, naming, error handling, tests, and abstractions.
   - Prefer existing helpers, framework conventions, and project scripts over new machinery.
   - Add an abstraction only when it removes real duplication or matches an established pattern.

5. Verify with concrete commands.
   - Run the narrowest useful project-defined test, typecheck, lint, build, or manual command available.
   - When fixing a bug, reproduce it first when practical, then verify the fix.
   - If a check fails or cannot be run, separate the command, outcome, likely cause, and remaining risk.

6. Report the result clearly.
   - Summarize changed files and behavior.
   - State tests or commands run and their outcome.
   - Call out assumptions, failed or skipped checks, limitations, and follow-up work that matters.

## Operating Rules

- Prefer the simplest implementation that satisfies the current request.
- Do not silently choose between materially different interpretations.
- Do not hide uncertainty; name it and either resolve it or proceed with an explicit assumption.
- Keep diffs proportional to the task.
- Treat verification as part of the work, not as an optional final step.
