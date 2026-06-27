# Ali Codex Skills

Focused engineering skills for the Skills ecosystem.

Ali Codex Skills is a modular set of software engineering workflows for agentic coding tools. The skills help an agent inspect unfamiliar repositories, make focused changes, debug defects, verify work, and review code with evidence.

Skills page: <https://www.skills.sh/alichaabane/ali-codex-skills>

---

## Install

Install the full skill collection:

```bash
npx skills add alichaabane/ali-codex-skills
```

Install an individual skill:

```bash
npx skills add alichaabane/ali-codex-skills@codex-debugging
```

You can replace `codex-debugging` with any skill directory name from `skills/`.

---

## Quick Start

1. Install the full repository or a specific skill with `npx skills add`.
2. Open a software project in your agent.
3. Ask for the engineering task naturally:

```text
Use repository analysis to map this codebase before planning changes.
```

```text
Use codex-debugging to reproduce and fix the failing login test.
```

```text
Review this diff with codex-code-review and focus on correctness, regressions, and missing tests.
```

The skills are designed to be selected automatically when the task matches their descriptions, and they can also be named directly when you want a specific workflow.

---

## Supported Agents

These skills are written for the Skills ecosystem and are intended to work across compatible coding agents, including Codex, Claude Code, Cursor, GitHub Copilot, OpenCode, Gemini, Windsurf, and other tools that support Skills-style `SKILL.md` workflows.

Agent behavior can vary by implementation. The repository keeps each skill small, explicit, and self-contained so agents can load only the guidance relevant to the current task.

---

## Available Skills

| Skill | Purpose | Use When |
|-------|---------|----------|
| `codex-engineering-playbook` | Core implementation workflow | Making focused code changes, refactors, migrations, or feature updates |
| `codex-repository-analysis` | Repository discovery workflow | Understanding an unfamiliar codebase before planning or editing |
| `codex-debugging` | Defect investigation workflow | Diagnosing, reproducing, isolating, fixing, and verifying bugs |
| `codex-testing-verification` | Verification workflow | Choosing, running, interpreting, and reporting tests, builds, lint, or manual checks |
| `codex-code-review` | Code review workflow | Reviewing diffs, pull requests, patches, or proposed changes |

See [skills/README.md](skills/README.md) for a more detailed index.

---

## Repository Philosophy

- Modular engineering workflows: each skill captures a repeatable engineering behavior.
- One responsibility per skill: skills stay focused so agents can choose the right workflow without loading unrelated guidance.
- Evidence-driven engineering: workflows favor repository facts, reproduction steps, test output, diffs, and concrete verification over assumptions.
- Minimal context loading: small `SKILL.md` files reduce noise and make automatic skill selection easier.
- Reusable across repositories: the guidance is procedural rather than project-specific, so it can apply to many languages, frameworks, and codebases.

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

- `README.md`: public project overview and installation guide.
- `CODEX.md`: concise entry point for Codex users.
- `skills/README.md`: index of available skills and when to use them.
- `skills/*/SKILL.md`: focused procedural workflows with skill metadata.

---

## Design Principles

- Understand before changing.
- Keep changes focused.
- Reuse existing project patterns.
- Verify with evidence.
- Report assumptions and remaining risk.
- Keep skills modular and avoid duplicated guidance.

---

## Attribution

Ali Codex Skills was inspired by the original `andrej-karpathy-skills` repository and has evolved into a modular engineering workflow collection.

Original project: <https://github.com/multica-ai/andrej-karpathy-skills>
