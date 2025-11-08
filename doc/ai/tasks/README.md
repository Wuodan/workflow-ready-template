# Task Index & Numbering

Use this file to catalog every task in your project. Keep it updated so collaborators can find the
active work without digging through branches.

## Numbering Scheme
- Tasks follow the `T###` pattern (e.g., `T001`, `T002`).
- Folder names use `doc/ai/tasks/T###_<slug>/`.
- Each task maintains its own `README.md` with the scope summary and links to the plan.
- Link every task row to its GitHub issue once one exists.

## Task Overview
| Task ID | Title | Status | Plan Folder | GitHub Issue | Notes |
|---------|-------|--------|-------------|--------------|-------|
| T000 | Replace this row with your first real task | Proposed | _(Plan pending)_ | — | Remove once T001 is created |

Guidance:
- Mark exactly one row as **Active** so the current focus is obvious.
- Keep the GitHub issue link synchronized with its current `status:*` label.
- Append new rows at the bottom to preserve chronology.

## Plan Usage
- Planning artifacts belong inside each task’s `plan/` directory (see the table above for quick
  links).
- Update plan checklists immediately after progress so any new agent can resume from the latest
  state.
- Mirror every Progress Log entry as a comment on the matching task PR.

## Creating a New Task
1. Copy `doc/ai/templates/task_plan_README.template.md` to
   `doc/ai/tasks/T###_<slug>/plan/README.md` and fill in the placeholders.
2. For each subtask, copy `doc/ai/templates/subtask_plan_README.template.md` into
   `plan/subtask_S###_<slug>/README.md`.
3. Open a GitHub issue via `.github/ISSUE_TEMPLATE/task.yml`, apply the `task` label and a single
   `status:*` label, then create a draft PR from `task/T###_<slug>` → `development` with "Closes
   #<issue>" in the body.
4. Update this table whenever statuses change or new tasks spin up.
