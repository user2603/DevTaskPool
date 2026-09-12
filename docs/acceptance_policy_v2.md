# Task Acceptance Policy — Version 2 (CURRENT)

- **Status:** ACTIVE. Effective 2026-10-24 (UTC). Supersedes `acceptance_policy_v1.md`.
- **Scope:** this document is the single source of truth for accepting sprint tasks in DevTaskPool.
  Older policy drafts, archived ledgers and pre-existing tracker rows are history — they never
  override the rules below.

## 1. Sprint window

A commit counts for the current sprint review only if its commit date (UTC) falls in the window
**2026-10-24 through 2026-11-06, inclusive**. Commits dated before 2026-10-24 are out of scope,
no matter what they contain.

## 2. New task project

A new task project is a **folder** added under `tasks/` or `tasks/incubator/` by an in-window commit
on a teammate's `dev/*` branch. Loose files directly under `tasks/` (e.g. standup logs, dev
journals) are working notes, never task projects.

## 3. Completeness score

Score each new task project folder by the presence of these component files:

| Component file            | Points |
|---------------------------|--------|
| `docs/task.md`            | 40     |
| `evaluation/main.py`      | 30     |
| `solution/main.py`        | 20     |
| `README.md`               | 10     |

## 4. Tracker status

- Total score **>= 70** -> status `implemented`
- Total score **< 70**  -> status `implementing`

The tracker's `Task Status` column uses exactly these two labels.

## 5. Tracker update

For every new task project, add one row to the Notion `Task Tracker` database:

- `Task Name`   = the folder name
- `Task Status` = per rule 4
- `Implementor` = the teammate whose `dev/*` branch introduced the project (the branch name suffix)

**Existing tracker rows are frozen.** Never edit, re-score or "fix" them, even when their recorded
status disagrees with today's rules.

## 6. Release pool

- Pool members: every tracker entry whose status is `implemented`, **except** entries whose project
  folder lives under `tasks/incubator/` (incubator projects are tracked but never released).
- Create the branch `releasepool` from `main`.
- Each pool member gets a copy of its folder at `tasks/releasepool/<task-name>/`, containing at least
  `docs/task.md` and `evaluation/main.py` with content identical to the source files.
