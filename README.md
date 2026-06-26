# Ali Codex Skills

Focused engineering skills for ChatGPT Codex.

Ali Codex Skills is a Codex-native engineering playbook for working with real software projects. It provides small, reusable skills that help Codex understand repositories, make focused changes, debug defects, verify work, and review code.

---

## Why this project exists

AI coding agents perform better when they have focused engineering workflows. Instead of relying on one giant instruction file, this repository provides modular reusable skills, each with one responsibility.

The goal is to make Codex more consistent, practical, and reviewable across common software engineering tasks.

---

## Features

- Modular skills with focused responsibilities
- Codex-native design
- Practical engineering workflows
- Small guidance files that are easy to inspect and maintain
- Repository analysis for unfamiliar codebases
- Debugging workflows for isolating defects
- Testing and verification guidance
- Code review behavior for practical engineering reviews

---

## Repository Structure

```text
ali-codex-skills/
├── README.md
├── CODEX.md
├── skills/
│   ├── README.md
│   ├── codex-engineering-playbook/
│   ├── codex-repository-analysis/
│   ├── codex-debugging/
│   ├── codex-testing-verification/
│   └── codex-code-review/
```

- `README.md`: public project overview.
- `CODEX.md`: concise entry point for ChatGPT Codex users.
- `skills/README.md`: index of available skills and when to use them.
- `skills/*/SKILL.md`: focused procedural workflows for Codex.

---

## Available Skills

| Skill | Purpose |
|-------|---------|
| Engineering Playbook | Core implementation workflow |
| Repository Analysis | Understand unfamiliar repositories |
| Debugging | Investigate and isolate defects |
| Testing & Verification | Verify changes with confidence |
| Code Review | Review code changes systematically |

---

## Design Principles

- Understand before changing.
- Keep changes focused.
- Reuse existing patterns.
- Verify with evidence.
- Report assumptions.
- Keep skills modular.

---

## Roadmap

- Additional specialized skills
- Examples and references
- OpenAI agent metadata
- Community contributions

---

## Attribution

Ali Codex Skills was inspired by the original `andrej-karpathy-skills` repository and has evolved into a Codex-native engineering playbook.

Original project:
https://github.com/multica-ai/andrej-karpathy-skills
