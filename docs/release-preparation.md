# Release Preparation

## Repository Status

Ali Codex Skills has evolved from the original fork into a Codex-native engineering skills repository. The core public shape is now present: a project README, a Codex entrypoint, a skills index, and five focused Codex skills.

The repository still contains legacy Claude and Cursor artifacts from the source project. These are useful during transition but should not define the v0.1 identity.

## Top-Level Classification

| Path | Classification | Notes |
|------|----------------|-------|
| `.claude-plugin/` | Deprecate | Legacy Claude plugin packaging; keep temporarily until Codex distribution is settled. |
| `.cursor/` | Deprecate | Legacy Cursor rule support; keep temporarily for compatibility. |
| `.git/` | Keep | Local Git metadata, not release content. |
| `.gitignore` | Keep | Required to keep editor, cache, and local files out of commits. |
| `.idea/` | Remove | Local IDE metadata; ignored and should not be part of the public repository. |
| `docs/` | Keep | Release and migration documentation belongs here. |
| `skills/` | Keep | Core product of the repository. |
| `CLAUDE.md` | Deprecate | Legacy Claude instruction file; keep until compatibility decision is finalized. |
| `CODEX.md` | Keep | Codex entrypoint that connects the repository purpose, workflow, skills, and principles. |
| `CURSOR.md` | Deprecate | Legacy Cursor usage documentation; keep until Cursor support is removed or rewritten. |
| `EXAMPLES.md` | Move | Useful inherited examples, but should move into skill references when examples are introduced. |
| `MIGRATION_PLAN.md` | Move | Planning artifact should live under `docs/`. |
| `README.md` | Keep | Public project homepage. |
| `REVIEW.md` | Move | Review artifact should live under `docs/` or be folded into issue tracking. |

## Keep

- `README.md`: Keep as the public GitHub homepage for v0.1.
- `CODEX.md`: Keep as the concise Codex user entrypoint.
- `skills/`: Keep as the primary repository content.
- `skills/README.md`: Keep as the skills index.
- `skills/codex-engineering-playbook/`: Keep as the core implementation workflow.
- `skills/codex-repository-analysis/`: Keep as the repository discovery workflow.
- `skills/codex-debugging/`: Keep as the debugging workflow.
- `skills/codex-testing-verification/`: Keep as the verification workflow.
- `skills/codex-code-review/`: Keep as the code review workflow.
- `.gitignore`: Keep to prevent local/editor artifacts from entering the repository.
- `docs/`: Keep as the home for release preparation, migration notes, and future project documentation.

## Move

- `MIGRATION_PLAN.md` -> `docs/migration.md`: Move after v0.1 or before release if the migration plan remains useful as project history.
- `REVIEW.md` -> `docs/core-skill-review.md`: Move if the review remains useful; otherwise convert findings into issues and remove the file.
- `EXAMPLES.md` -> `skills/codex-engineering-playbook/references/examples.md`: Move when examples and references are added to skills.

## Deprecate

- `CLAUDE.md`: Keep temporarily for users who still rely on the inherited Claude workflow, but mark as legacy once Codex-native docs are complete.
- `CURSOR.md`: Keep temporarily while `.cursor/` remains in the repository, but do not expand it.
- `.cursor/`: Keep temporarily for compatibility with existing Cursor users.
- `.claude-plugin/`: Keep temporarily because it still points at the renamed core skill, but it is not part of the Codex-native target.

## Remove After v0.1

- `CLAUDE.md`: Remove after Codex-native entrypoints and skills fully replace root Claude instructions.
- `CURSOR.md`: Remove after Cursor compatibility is retired or moved to external documentation.
- `.cursor/`: Remove after the project stops shipping Cursor rules.
- `.claude-plugin/`: Remove after the project decides not to distribute as a Claude plugin.
- `.idea/`: Remove from local working trees if present; it is ignored and should never be published.

Only remove legacy support after the replacement path is clear and documented.

## Missing Files

- `LICENSE`: Important now. The repository needs an explicit license before v0.1.
- `CHANGELOG.md`: Important now. v0.1 should have a short initial changelog.
- `CONTRIBUTING.md`: Useful soon. Can wait if the first release is maintainer-only, but should exist before inviting contributions.
- `.github/`: Useful soon. Issue templates, pull request templates, and workflows can wait until contribution volume justifies them.
- `SECURITY.md`: Can wait unless the repository begins accepting integrations, scripts, or security-sensitive automation.
- `CODE_OF_CONDUCT.md`: Can wait, but should be added before actively soliciting community contributions.

## Release Checklist

- [ ] README complete and aligned with v0.1 scope.
- [ ] CODEX.md complete and concise.
- [ ] Skills indexed in `skills/README.md`.
- [ ] All five initial skills reviewed for concise frontmatter and focused scope.
- [ ] `LICENSE` added.
- [ ] `CHANGELOG.md` added with v0.1 notes.
- [ ] Legacy Claude and Cursor files reviewed and marked as transitional.
- [ ] Migration and review artifacts moved under `docs/` or converted into issues.
- [ ] Repository status clean before release.
- [ ] Initial GitHub release created.
- [ ] `v0.1.0` tag pushed.
