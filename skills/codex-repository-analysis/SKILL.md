---
name: codex-repository-analysis
description: Repository discovery workflow for Codex. Use when Codex needs to understand an unfamiliar codebase before planning or making changes by identifying structure, entry points, package managers, configuration, documentation, CI/CD, dependencies, conventions, and task-relevant areas.
---

# Codex Repository Analysis

Use this skill to build a concise map of an unfamiliar repository before deciding what to change.

## Discovery Workflow

1. Identify the project type.
   - Look for language, framework, runtime, and application shape.
   - Note whether the repository is a library, service, app, CLI, monorepo, package, plugin, or documentation project.

2. Inspect repository structure.
   - List top-level directories and major source, test, docs, config, and tooling areas.
   - Identify generated, vendored, build, cache, and local-only directories to ignore.

3. Locate entry points.
   - Find application starts, exported packages, CLI commands, routes, main modules, plugin manifests, or public APIs.
   - Distinguish primary entry points from examples, tests, and generated outputs.

4. Identify package and dependency management.
   - Locate package manager files, lockfiles, dependency manifests, workspace files, and version files.
   - Note how dependencies are grouped, pinned, or shared across packages.

5. Identify build, test, and task systems.
   - Locate scripts, task runners, Makefiles, project configs, and CI commands.
   - Record canonical commands without designing a testing strategy.

6. Locate configuration and documentation.
   - Find project docs, contributor notes, environment templates, lint or format configs, type configs, and deployment configs.
   - Prefer repository documentation over assumptions.

7. Identify coding conventions.
   - Observe naming, file organization, module boundaries, error handling, formatting, and test layout.
   - Treat existing conventions as stronger evidence than generic best practices.

8. Identify CI/CD and release workflow.
   - Inspect workflow files, pipeline configs, release scripts, deployment manifests, and required checks.
   - Note what automation exists and what parts of the repo it touches.

9. Map task-relevant areas.
   - Search for symbols, strings, routes, configs, docs, and tests connected to the user's request.
   - Summarize likely affected files and uncertain areas before moving to planning or implementation.

## Output

- Summarize the repository type, major directories, entry points, tooling, documentation, conventions, automation, and task-relevant areas.
- Separate confirmed findings from assumptions.
- Keep the analysis brief enough to guide the next step.
