# Ali Codex Skills

Ali Codex Skills is a Codex-native engineering playbook for using ChatGPT Codex on real software projects.

## Purpose

This repository provides modular engineering skills for ChatGPT Codex. Each skill has a focused responsibility, so Codex can apply the right workflow without loading or repeating unrelated guidance.

The skills are intended to work together, but they are not a single linear process. Use the skill that matches the task, and combine skills only when the work actually needs them.

## Core Workflow

Recommended flow for substantial engineering work:

1. Repository Analysis
2. Engineering Playbook
3. Debugging, when investigating defects
4. Testing & Verification
5. Code Review

Not every task requires every skill. Small edits may only need the engineering playbook and verification. A review request may only need the code review skill. A bug report may start with debugging and use testing verification at the end.

## Available Skills

### `codex-engineering-playbook`

General operating workflow for making software changes with small diffs, existing project patterns, concrete verification, and clear risk reporting. Use it as the baseline for implementation, refactoring, migrations, and other code-change tasks.

### `codex-repository-analysis`

Repository discovery workflow for understanding an unfamiliar codebase before planning or editing. Use it to identify structure, entry points, tooling, configuration, documentation, conventions, automation, dependencies, and task-relevant areas.

### `codex-debugging`

Defect investigation workflow for reproducing issues, gathering evidence, narrowing scope, forming hypotheses, identifying root cause, applying the smallest fix, and verifying the reported behavior.

### `codex-testing-verification`

Verification workflow for discovering project-defined checks, choosing the right scope, running commands or manual checks, interpreting results, and reporting skipped checks or remaining risk.

### `codex-code-review`

Review workflow for evaluating diffs, pull requests, patches, or proposed changes. Use it to prioritize correctness, security, regressions, maintainability, test gaps, and verification issues.

## Engineering Principles

- Understand before changing.
- Keep changes focused.
- Prefer existing project patterns.
- Verify work with evidence.
- Report assumptions and remaining risk.
- Keep skills modular and avoid duplication.

## Repository Design

- `SKILL.md` files contain procedural workflows for Codex.
- `README.md` explains the project and migration status.
- `skills/README.md` indexes the available skills.
- `CODEX.md` connects the project purpose, workflow, skills, principles, and repository structure.
