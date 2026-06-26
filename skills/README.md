# Skills Index

This directory contains Codex skills for practical software engineering work. Use the most specific skill for the task, and use `codex-engineering-playbook` as the general operating baseline.

## `codex-engineering-playbook`

- Purpose: General workflow for making software changes with small diffs, existing patterns, concrete verification, and clear risk reporting.
- Use when: Codex needs to plan or execute a code change, refactor, migration, or implementation task.
- Differs from others: Broad operating playbook; it does not go deep on discovery, review, debugging, or verification.

## `codex-repository-analysis`

- Purpose: Map an unfamiliar repository before planning or editing.
- Use when: Codex needs to identify project type, structure, entry points, package managers, configs, docs, CI/CD, conventions, dependencies, and task-relevant areas.
- Differs from others: Discovery-only; it stops before implementation, review, debugging, or verification strategy.

## `codex-code-review`

- Purpose: Review diffs and proposed code changes like a practical engineering reviewer.
- Use when: Codex is asked to review a patch, pull request, or changed files for correctness, security, regressions, maintainability, test gaps, and verification issues.
- Differs from others: Review-only; it produces findings and questions rather than implementation plans or fixes.

## `codex-debugging`

- Purpose: Investigate and isolate software defects before applying a fix.
- Use when: Codex needs to reproduce an issue, gather evidence, narrow scope, test hypotheses, identify root cause, and verify the reported defect is resolved.
- Differs from others: Bug-investigation focused; it includes only the fix work needed to resolve the diagnosed defect.

## `codex-testing-verification`

- Purpose: Choose, run, interpret, and report verification for code changes.
- Use when: Codex needs to discover project-defined checks, choose the right verification scope, run tests or related commands, and report outcomes and risk.
- Differs from others: Verification-only; it does not cover repository discovery, implementation, debugging investigation, or code review.
