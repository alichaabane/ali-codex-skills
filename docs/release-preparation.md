# Release Preparation

## Repository Status

Ali Codex Skills is close to a first public Codex-native release. The root documentation, Codex entrypoint, skills index, and five focused skills are present.

The release tree has been simplified around Codex. Historical migration and review notes now live under `docs/`.

## Top-Level Classification

| Path | Classification | Notes |
|------|----------------|-------|
| `.git/` | Keep | Local Git metadata, not release content. |
| `.gitignore` | Keep | Keeps editor, cache, and local files out of commits. |
| `.idea/` | Remove | Local IDE metadata; ignored and should not be published. |
| `CODEX.md` | Keep | Entry point for ChatGPT Codex users. |
| `EXAMPLES.md` | Move | Useful inherited examples; move into skill references when examples are introduced. |
| `README.md` | Keep | Public project homepage. |
| `docs/` | Keep | Project history, release preparation, and future documentation. |
| `skills/` | Keep | Core product of the repository. |

## Keep

- `README.md`: Public GitHub homepage for v0.1.
- `CODEX.md`: Concise Codex user entrypoint.
- `skills/`: Primary repository content.
- `skills/README.md`: Skills index.
- `skills/codex-engineering-playbook/`: Core implementation workflow.
- `skills/codex-repository-analysis/`: Repository discovery workflow.
- `skills/codex-debugging/`: Debugging workflow.
- `skills/codex-testing-verification/`: Verification workflow.
- `skills/codex-code-review/`: Code review workflow.
- `docs/`: Home for release preparation, migration notes, and project history.
- `.gitignore`: Required for clean public commits.

## Move

- `EXAMPLES.md` -> `skills/codex-engineering-playbook/references/examples.md`: Move when examples and references are added to skills.

## Deprecate

- No transitional compatibility files remain in the release tree.

## Remove After v0.1

- `.idea/`: Remove from local working trees if present; it is ignored and should never be published.

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
- [ ] Project history moved under `docs/`.
- [ ] Legacy non-Codex distribution artifacts removed.
- [ ] Repository status clean before release.
- [ ] Initial GitHub release created.
- [ ] `v0.1.0` tag pushed.
