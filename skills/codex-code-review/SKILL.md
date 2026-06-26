---
name: codex-code-review
description: Practical code review workflow for Codex. Use when Codex is asked to review a diff, pull request, patch, or proposed code change for correctness, security, regressions, maintainability, test gaps, and verification issues.
---

# Codex Code Review

Use this skill to review code changes as a practical engineering reviewer.

## Review Workflow

1. Start with the diff.
   - Inspect changed files before reading unrelated code.
   - Use surrounding context only where needed to understand behavior.
   - Compare the changes against the user's requested scope.

2. Prioritize material issues.
   - Look first for correctness bugs, security risks, regressions, broken contracts, data loss, and missing edge cases.
   - Then consider maintainability, unclear behavior, risky coupling, and test or verification gaps.
   - Skip style nitpicks unless they affect clarity, correctness, or future risk.

3. Ground findings in evidence.
   - Cite specific files, functions, lines, symbols, or changed behavior when possible.
   - Explain the user-visible or system-level impact.
   - Distinguish confirmed issues from plausible risks.

4. Separate blockers from suggestions.
   - Treat issues that can break behavior, security, data integrity, builds, or deploys as blockers.
   - Label nonblocking improvements as suggestions.
   - Avoid turning personal preference into required work.

5. Call out verification gaps.
   - Note missing or insufficient tests only when they matter to the changed behavior.
   - Mention skipped, absent, or failing verification when it affects confidence in the change.

6. Keep the review concise.
   - Lead with findings ordered by severity.
   - If no issues are found, say so clearly and mention any remaining uncertainty.
   - Keep summaries secondary to actionable findings.

## Output

- List findings first, with severity and precise location when possible.
- Include open questions only when they affect correctness or review confidence.
- End with a brief summary or "No issues found" statement.
