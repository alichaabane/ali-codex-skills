# Review: Codex Engineering Playbook Skill

Scope: `skills/codex-engineering-playbook/SKILL.md`

## 1. Strengths

- The skill is concise and easy to scan.
- The frontmatter uses the Codex skill shape correctly with `name` and `description` only.
- The body is procedural rather than philosophical.
- The workflow preserves the inherited intent: inspect first, avoid assumptions, keep changes small, reuse local patterns, verify, and report risk.
- The ordering matches a practical engineering loop from discovery through final reporting.
- The guidance avoids examples for now, which keeps the core skill lightweight.
- The language is mostly tool-agnostic while still naming `rg` as a practical Codex workflow hint.

## 2. Weaknesses

- The description is accurate but long; it may be harder to scan in skill lists.
- "Senior-engineer discipline" is expressive but slightly subjective compared with the rest of the procedural wording.
- "Concrete commands" is useful but underspecified; it does not say how to discover the right commands from the repository.
- The skill does not explicitly warn Codex to preserve user changes in a dirty worktree.
- The verification step mentions tests, typecheck, lint, and build, but not CI configuration, package scripts, or existing task runners.
- The reporting step is good but could be more explicit about distinguishing completed work from residual risk.
- The skill is broad enough that future additions could make it generic unless strict scope is maintained.

## 3. Missing topics

- Dirty worktree handling:
  - inspect `git status`;
  - do not revert unrelated user changes;
  - avoid staging or committing unless asked.
- Command discovery:
  - inspect `package.json`, `pyproject.toml`, `Makefile`, CI files, or repo docs for canonical commands.
- Safe editing:
  - prefer minimal patches;
  - avoid destructive filesystem or Git operations.
- Dependency discipline:
  - do not add new dependencies unless the task clearly requires them and the project pattern supports it.
- Failure handling:
  - when tests fail for unrelated reasons, report that separately from the change.
- Public skill maintainability:
  - keep the core skill general;
  - move future examples or detailed checklists into references rather than growing `SKILL.md`.
- Codex-specific interaction:
  - use short progress updates for longer work;
  - summarize final verification clearly;
  - ask for clarification only when blocked or when choices materially change the result.

## 4. Suggested improvements

- Shorten the frontmatter description while keeping trigger coverage.
- Replace subjective wording with direct procedural wording.
- Add one bullet under inspection about checking repository status and canonical commands.
- Add one bullet under focused changes about preserving unrelated user work.
- Add one bullet under verification about using project-defined scripts and CI configuration when available.
- Add one bullet under reporting about separating assumptions, failed checks, and residual risk.
- Keep this as one core playbook for now; split review/debug/testing skills only after the core wording stabilizes.

## 5. Priority

High:
- Add dirty worktree and user-change preservation guidance.
- Add command discovery guidance for tests, build, lint, and typecheck.
- Clarify reporting of failed or skipped verification.

Medium:
- Shorten the frontmatter description.
- Replace subjective phrasing with more direct procedural language.
- Add dependency discipline and safe-editing constraints.

Low:
- Add references later for examples and detailed checklists.
- Split specialized skills later if the core playbook becomes too broad.
