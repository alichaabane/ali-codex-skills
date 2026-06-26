# Migration Notes

## Summary

Ali Codex Skills started as a fork of `andrej-karpathy-skills` and has been reshaped into a Codex-native engineering skills repository.

The migration moved the project away from a single inherited guideline set and toward focused, reusable Codex skills. The current repository now centers on modular workflows for repository analysis, implementation discipline, debugging, verification, and code review.

## Completed

- Established the Ali Codex Skills project identity.
- Added a root `README.md` suitable for a public open-source project.
- Added `CODEX.md` as the entry point for ChatGPT Codex users.
- Added `skills/README.md` as the skills index.
- Renamed and adapted the original core skill into `codex-engineering-playbook`.
- Added focused skills for:
  - repository analysis,
  - debugging,
  - testing and verification,
  - code review.
- Moved migration and review history under `docs/`.
- Removed legacy non-Codex distribution artifacts from the release tree.

## Current Architecture

```text
ali-codex-skills/
├── README.md
├── CODEX.md
├── docs/
│   ├── core-skill-review.md
│   ├── migration.md
│   └── release-preparation.md
└── skills/
    ├── README.md
    ├── codex-engineering-playbook/
    ├── codex-repository-analysis/
    ├── codex-debugging/
    ├── codex-testing-verification/
    └── codex-code-review/
```

## Remaining Work

- Add a project license before publishing v0.1.0.
- Add a changelog for the first release.
- Add OpenAI agent metadata when the skill scope and naming are stable.
- Move useful examples into skill references when examples are ready.
- Add contribution guidance before actively inviting external contributions.

## Release Direction

The v0.1.0 release should present Ali Codex Skills as a Codex-native project with a small, coherent initial skill set. Historical migration details should stay in `docs/`, while the root should remain focused on public project orientation.
