---
name: studio-test-setup
description: "Game studio: Scaffold the test framework and CI — tests/ directory, engine test runner, GitHub Actions workflow. Once, before the first sprint."
---

## Rakazo compatibility

This is an instruction-only adaptation of the upstream Claude Code workflow. Use available Rakazo tools instead of Claude-specific tools. Hooks, rules, automatic agent delegation, local MCP servers, bundled scripts and model selections do not automatically run or apply in Rakazo. Never claim they ran. If a required check or tool is unavailable, explain what was skipped. When this workflow refers to another /command, use the corresponding /studio-<command> skill if available.

Paths such as .claude/docs, .claude/agents, .claude/scripts, project.yaml, and project documents refer to a separately cloned game project, not installed plugin files. Ask for the project location if necessary; do not assume it exists. Read relevant agent instructions and use run_subagent only when available and appropriate; do not claim a persistent team was created. References beside this skill are installed as text. Do not assume that importing this skill executes bundled scripts.

!`bash "${CLAUDE_SKILL_DIR}/../../hooks/yaml-helper.sh" resolve_config --keys automation,workflow,qa.level`

**Automation mode**: Resolve `modes.automation` (`project.local.yaml` →
`project.yaml` → default `collaborative`). Every `AskUserQuestion` call and
every file write follows `.claude/docs/automation-modes.md`
(collaborative asks always · guided major-only · autonomous logs and proceeds;
`automation_always_ask` categories always prompt).

# Test Setup

This skill scaffolds the automated testing infrastructure for the project.
It detects the configured engine, generates the appropriate test runner
configuration, creates the standard directory layout, and wires up CI/CD
so tests run on every push.

Run this once during the Technical Setup phase, before any implementation
begins. A test framework installed at sprint start costs 30 minutes.
A test framework installed at sprint four costs 3 sprints.

**Output:** `tests/` directory structure + `.github/workflows/tests.yml`

---

## Phase 1: Detect Engine and Existing State

**Read `references/1-detect.md` now and follow it** — this phase's steps are in that file, not here. Read it again if the conversation was compacted or resumed during this phase.

## Phase 2: Present Plan

**Read `references/2-plan.md` now and follow it** — this phase's steps are in that file, not here. Read it again if the conversation was compacted or resumed during this phase.

## Phase 3: Create Directory Structure

**Read `references/3-directories.md` now and follow it** — this phase's steps are in that file, not here. Read it again if the conversation was compacted or resumed during this phase.

## Phase 4: Create CI/CD Workflow

**Read `references/4-ci.md` now and follow it** — this phase's steps are in that file, not here. Read it again if the conversation was compacted or resumed during this phase.

## Phase 5: Create Smoke Test Seed

**Read `references/5-smoke-seed.md` now and follow it** — this phase's steps are in that file, not here. Read it again if the conversation was compacted or resumed during this phase.

## Phase 6: Post-Setup Summary

**Read `references/6-summary.md` now and follow it** — this phase's steps are in that file, not here. Read it again if the conversation was compacted or resumed during this phase.

## Collaborative Protocol

- **Never overwrite existing test files** — only create files that are missing.
  If a test runner file exists, leave it as-is.
- **Always ask before creating files** — Phase 2 requires explicit approval.
- **Engine detection is non-negotiable** — if the engine is not configured,
  stop and redirect to `/setup-engine`. Do not guess.
- **`force` flag skips the "already exists" early-exit but never overwrites.**
  It means "create any missing files even if the directory already exists."
- For Unity CI, note that the `UNITY_LICENSE` secret must be configured
  manually. Do not attempt to automate license management.
