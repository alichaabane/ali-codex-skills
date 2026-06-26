---
name: codex-debugging
description: Defect investigation workflow for Codex. Use when Codex is asked to diagnose, reproduce, isolate, explain, or fix a software bug by gathering evidence, testing hypotheses, identifying root cause, applying the smallest fix, and verifying the reported issue.
---

# Codex Debugging

Use this skill to investigate and isolate software defects before attempting a fix.

## Debugging Workflow

1. Reproduce the issue.
   - Understand the reported behavior and user-visible impact.
   - Gather exact reproduction steps, inputs, environment, and observed output.
   - Distinguish expected behavior from actual behavior.

2. Narrow the scope.
   - Identify affected components, code paths, data, configuration, or integrations.
   - Check whether recent changes, dependencies, or environment differences are relevant.
   - Reduce the issue to the smallest reproducible case when practical.

3. Gather evidence.
   - Read logs, stack traces, error messages, failing output, and relevant state.
   - Follow the execution path through the code that can produce the behavior.
   - Inspect runtime state or intermediate values when available.
   - Avoid guessing when evidence can be collected.

4. Form hypotheses.
   - Prefer hypotheses tied to observed evidence.
   - Test one hypothesis at a time.
   - Eliminate possibilities systematically before changing code.

5. Fix the root cause.
   - Choose the smallest change that resolves the defect.
   - Avoid masking symptoms without addressing the cause.
   - Preserve existing behavior outside the affected path.

6. Verify the fix.
   - Confirm the original reproduction no longer fails.
   - Check for regressions in nearby or affected behavior.
   - Report any remaining uncertainty or unverified assumptions.

## Output

- Summarize the reproduction, evidence, root cause, fix, and verification.
- Separate confirmed facts from hypotheses.
- State any remaining uncertainty clearly.
