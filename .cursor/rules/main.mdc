<!-- generated from AGENTS.md by scripts/sync-instructions.sh — do not edit -->

# Agent instructions

This file is the single source of truth for every coding agent working in this
repository. `CLAUDE.md`, `.cursor/rules/main.mdc` and
`.github/copilot-instructions.md` are generated from this file — never edit them
directly. Run `scripts/sync-instructions.sh` after changing anything here.

## Ground rules

1. You are running as exactly one role. Read your role file in `factory/roles/`
   and do only what it describes. Do not perform another role's job because it
   seems convenient.
2. The specification wins. If the code and `factory/product/acceptance.md`
   disagree, the code is wrong. If the spec is ambiguous, stop and escalate —
   do not choose an interpretation and proceed.
3. Never edit acceptance criteria, task definitions, gate configuration, or
   anything under `.github/workflows/` to make your work pass. Doing so is the
   single most serious failure mode in this system. (The tech lead writes new
   task files; that is its job.)
4. Stay inside `files_allowed` for your task. When you finish, the factory
   checks every file you changed. If any file is outside that list, or is one
   of the protected files (gate config, `bin/`, `scripts/`, `adapters/`,
   roles, tasks, approvals, `factory/runs/`, `tests/gates/`), nothing you did is
   committed. A developer may not change anything under `tests/`.
5. `factory/product/acceptance.md` has one owner per part: product writes the
   criteria, QA changes only the `**Verified by:**` lines, and every other
   role leaves the file alone.
6. You run in a temporary copy of the repo with no secrets. If your task needs
   one, it is listed under `secrets:` in the task file and is already in your
   environment. Do not look for `.env`.
7. Two attempts maximum. The factory counts failed runs and, after the second,
   writes `factory/escalations/<task-id>.md` itself and stops retrying. If you
   can see the task cannot be done as written (for example the spec is
   ambiguous), write that file yourself and stop.

## What is never agent-owned

Human-authored or reviewed line by line, no exceptions:

- authentication, session handling, password and token flows
- payment and billing logic
- anything crossing a tenant boundary in multi-tenant code
- production database migrations
- IAM policy, network policy, secret management
- `factory/learning/` (root-cause log; humans close and promote monthly)

If a task would touch any of these, stop and escalate.

## Repository map

| Path | Contents |
|---|---|
| `factory/product/` | PRD and acceptance criteria |
| `factory/architecture/` | ADRs, OpenAPI contract, data model, state machines |
| `factory/design/` | Optional UI spec (tokens, layout, states) |
| `factory/roles/` | One prompt file per role |
| `factory/tasks/` | One YAML file per unit of work |
| `factory/runs/` | Append-only run telemetry (JSONL) |
| `factory/escalations/` | Failures raised to the human; close with a root-cause tag |
| `factory/learning/` | Append-only close log + monthly CURRENT.md (human) |
| `factory/intake/escapes/` | Post-handover defects tagged to an AC |
| `src/`, `tests/` | The product |

## Definition of done, all roles

- The task's `acceptance` criteria are satisfied and demonstrably tested
- No new lint, type, or security findings
- The diff is under the task's `max_diff_lines`
- Nothing written to `factory/runs/`: the factory records each run itself
  (a reviewer writes only its own review file there)
