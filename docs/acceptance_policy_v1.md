# Task Acceptance Policy — Version 1 (SUPERSEDED)

> **DEPRECATED.** This draft was replaced by `acceptance_policy_v2.md` on 2026-10-24.
> It is kept in the repository for audit history only. Do NOT use it for the current
> sprint review.

## 1. Sprint window

Commits since **2026-10-10** count for review.

## 2. Completeness score (v1 weights)

| Component file            | Points |
|---------------------------|--------|
| `docs/task.md`            | 30     |
| `evaluation/main.py`      | 30     |
| `solution/main.py`        | 30     |
| `README.md`               | 10     |

## 3. Tracker status

- Total score **>= 60** -> status `implemented`
- Total score **< 60**  -> status `implementing`

## 4. Release pool

All `implemented` entries enter the pool (no incubator exception). Pool branch: `finalpool`,
pool path `tasks/finalpool`.
