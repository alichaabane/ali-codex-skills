# Migration Plan: Ali Codex Skills

## Repository overview

This repository is currently a small fork of `andrej-karpathy-skills` with an updated `README.md` that names the project "Ali Codex Skills". The tracked repository contains:

- `README.md`: short Ali Codex Skills project description and goals.
- `CLAUDE.md`: root-level Claude-style behavioral instruction file.
- `CURSOR.md`: usage notes for Cursor rules and Claude plugin distribution.
- `EXAMPLES.md`: long example catalog illustrating four behavioral principles.
- `.claude-plugin/plugin.json`: Claude plugin manifest pointing at `skills/karpathy-guidelines`.
- `.claude-plugin/marketplace.json`: Claude plugin marketplace metadata.
- `.cursor/rules/karpathy-guidelines.mdc`: Cursor project rule with the same behavioral guidance.
- `skills/karpathy-guidelines/SKILL.md`: one reusable skill containing the four inherited principles.

Untracked local IDE files also exist under `.idea/`. They are workspace metadata, not playbook content.

## Current architecture

The current architecture is inherited from a multi-tool distribution model:

- A single source idea is duplicated across `CLAUDE.md`, `.cursor/rules/karpathy-guidelines.mdc`, and `skills/karpathy-guidelines/SKILL.md`.
- The repo primarily packages one behavioral guideline set for Claude Code and Cursor.
- The only skill is named `karpathy-guidelines`, and its framing is explicitly derived from Andrej Karpathy's observations.
- The repo has no Codex-specific skill metadata such as `agents/openai.yaml`.
- The repo has no Codex-focused skill taxonomy, no references directory, no scripts, and no validation workflow.
- The examples are useful but live as one large human-facing document rather than progressively loaded skill reference material.

## Strengths

- The core principles are practical and worth preserving:
  - surface assumptions before coding,
  - prefer simple implementations,
  - make surgical edits,
  - define verifiable success criteria.
- `EXAMPLES.md` contains concrete before/after examples that can become useful reference material.
- The repository is small, easy to migrate incrementally, and has little technical debt beyond duplicated content and tool-specific packaging.
- The current `README.md` already states the intended direction: ChatGPT Codex, engineering workflows, debugging, review, testing, and verification.
- The existing skill gives a starting point for Codex skill structure, even though it needs renaming and frontmatter cleanup.

## Weaknesses

- The repo still centers Claude and Cursor more than Codex.
- `CLAUDE.md`, `CURSOR.md`, `.claude-plugin/`, and `.cursor/` are distribution artifacts for other tools, not the target architecture.
- The `karpathy-guidelines` name makes the project feel like a renamed fork rather than an Ali Codex engineering playbook.
- Skill frontmatter includes `license`, but Codex skills should keep frontmatter focused on `name` and `description`.
- The same guidance is duplicated in multiple files, creating sync risk.
- `EXAMPLES.md` is too large and broad for a core `SKILL.md`; it should become a reference file or be split by workflow.
- There is no root `.gitignore`, and untracked `.idea/` files are present.
- There is no clear contribution path, validation command, release checklist, or skill quality checklist.

## File classification

### Reusable

- `EXAMPLES.md`: reuse the examples, but move or split them into skill references.
- The four principles in `CLAUDE.md`, `.cursor/rules/karpathy-guidelines.mdc`, and `skills/karpathy-guidelines/SKILL.md`: preserve the substance.

### Should be adapted

- `README.md`: expand from placeholder status into a Codex-native project overview, installation notes, and skill catalog.
- `skills/karpathy-guidelines/SKILL.md`: rename and rewrite as a Codex engineering skill with concise instructions and Codex-style frontmatter.
- `EXAMPLES.md`: convert from a standalone examples document into focused reference material loaded only when needed.

### Should be replaced

- `CLAUDE.md`: replace with Codex-oriented repository guidance only if the repo needs a root instruction file; otherwise move the durable ideas into skills.
- `CURSOR.md`: replace with Codex usage documentation or remove once `README.md` covers usage.
- `.claude-plugin/plugin.json`: replace with Codex plugin/skill packaging only if this repo is intended to ship as a Codex plugin.
- `.claude-plugin/marketplace.json`: replace only if a Codex marketplace/plugin manifest is needed.
- `.cursor/rules/karpathy-guidelines.mdc`: replace with Codex skill metadata and references; keep Cursor support only if it remains an explicit secondary target.

### Should eventually be removed

- `.claude-plugin/`: remove after Codex-native packaging exists or the project decides it is skills-only.
- `.cursor/`: remove after Codex-native skills are in place unless maintaining Cursor compatibility is an explicit goal.
- `CURSOR.md`: remove after Cursor support is retired.
- `CLAUDE.md`: remove or rename after its content is absorbed into Codex skills.
- `.idea/`: do not commit; add root ignore rules and remove from working tree if it is accidentally tracked later.

## Recommended directory structure

Keep the repository simple and skill-first:

```text
ali-codex-skills/
├── README.md
├── MIGRATION_PLAN.md
├── LICENSE
├── .gitignore
├── skills/
│   ├── codex-engineering-playbook/
│   │   ├── SKILL.md
│   │   ├── agents/
│   │   │   └── openai.yaml
│   │   └── references/
│   │       └── examples.md
│   ├── codex-code-review/
│   │   ├── SKILL.md
│   │   └── agents/
│   │       └── openai.yaml
│   ├── codex-debugging/
│   │   ├── SKILL.md
│   │   └── agents/
│   │       └── openai.yaml
│   └── codex-testing-verification/
│       ├── SKILL.md
│       └── agents/
│           └── openai.yaml
└── docs/
    ├── authoring-principles.md
    └── migration-notes.md
```

Notes:

- Start with one high-quality skill before splitting into many skills.
- Keep each `SKILL.md` concise and procedural.
- Put detailed examples in `references/`, not in the main skill body.
- Add `agents/openai.yaml` once each skill has stable scope and naming.
- Add scripts only when a workflow needs deterministic automation. Do not add scripts just to make the repo look fuller.

## Step-by-step migration plan

### Phase 1: Stabilize the repository identity

1. Update `README.md` so it clearly states that Ali Codex Skills is a Codex-native engineering playbook, not a renamed Karpathy fork.
2. Add a root `.gitignore` that ignores `.idea/`, OS files, local caches, and generated artifacts.
3. Decide whether the repo keeps any secondary support for Claude or Cursor. Default recommendation: retire those artifacts after Codex-native replacements exist.
4. Add or confirm `LICENSE`, preserving attribution to the source project where required.

### Phase 2: Create the first Codex-native skill

1. Rename `skills/karpathy-guidelines/` to `skills/codex-engineering-playbook/`.
2. Rewrite `SKILL.md` with Codex-oriented language:
   - use `name: codex-engineering-playbook`,
   - use a trigger-focused `description`,
   - remove nonessential frontmatter fields,
   - keep the body short and action-oriented.
3. Preserve the four inherited principles, but reframe them around Codex execution:
   - inspect the repo first,
   - scope changes tightly,
   - verify with tests or commands,
   - report blockers and residual risk clearly.
4. Add `agents/openai.yaml` after the skill scope is stable.
5. Move detailed examples from `EXAMPLES.md` into `skills/codex-engineering-playbook/references/examples.md`.

### Phase 3: Reduce duplication

1. Remove duplicated principle text from root-level tool-specific files after the Codex skill exists.
2. Replace `CLAUDE.md` with a short note only if there is a real need to support Claude users.
3. Replace or remove `CURSOR.md` depending on whether Cursor remains supported.
4. Remove `.cursor/rules/karpathy-guidelines.mdc` unless Cursor support is explicitly retained.
5. Remove `.claude-plugin/` unless Claude plugin distribution is explicitly retained.

### Phase 4: Split workflow-specific skills only when useful

Create separate skills only when the core playbook becomes too broad:

1. `codex-code-review`: code review stance, severity ordering, line references, test gaps, and risk reporting.
2. `codex-debugging`: reproduce, localize, instrument, patch, and verify.
3. `codex-testing-verification`: test selection, regression checks, and verification reporting.
4. `codex-repo-migration`: repository audit, migration planning, file classification, and incremental commit strategy.

Each split should happen in a small commit and only after the source content is stable.

### Phase 5: Add quality controls

1. Add a lightweight validation checklist for every skill:
   - frontmatter has only required fields,
   - description explains when the skill should trigger,
   - body is concise,
   - references are linked from `SKILL.md`,
   - examples are concrete and not generic prompt advice.
2. Validate each skill manually at first.
3. Add scripts only if repeated validation becomes error-prone.
4. Add contribution guidance after the first complete skill is merged.

## Priority order for changes

1. Add `.gitignore` and keep `.idea/` out of the repository.
2. Rewrite `README.md` around the Codex-native mission and current skill catalog.
3. Rename and adapt `skills/karpathy-guidelines` into `skills/codex-engineering-playbook`.
4. Move `EXAMPLES.md` content into skill references and trim the top-level document.
5. Add `agents/openai.yaml` for the core skill.
6. Remove or quarantine Claude/Cursor packaging after Codex equivalents exist.
7. Add workflow-specific skills one at a time.
8. Add validation and contribution documentation only after the skill shape has settled.

## Incremental commit plan

1. `docs: add migration plan`
2. `chore: ignore local editor files`
3. `docs: rewrite readme for ali codex skills`
4. `refactor: rename karpathy guidelines skill`
5. `docs: move examples into codex skill references`
6. `feat: add codex skill metadata`
7. `chore: remove legacy claude and cursor packaging`
8. `feat: add codex review skill`
9. `feat: add codex debugging skill`
10. `feat: add codex testing verification skill`

## Open decisions before implementation

- Should this repository support only ChatGPT Codex, or keep secondary Claude/Cursor compatibility?
- Should Ali Codex Skills be distributed as a Codex plugin, a plain skills repository, or both?
- Should the first release include one consolidated playbook skill or multiple workflow-specific skills?
- What attribution language is required for the original fork beyond the existing README inspiration link?
