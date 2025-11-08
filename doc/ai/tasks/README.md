# Task Index & Numbering

Use this file to catalog every task in your project. Keep it updated so collaborators can find the
active work without digging through branches.

## Numbering Scheme
- Tasks use identifiers `T###` (e.g., `T001`, `T002`).
- Folder naming pattern: `doc/ai/tasks/T###_<slug>/`.
- The task description **lives inside each folder’s `README.md`** and may include extra helper files for that task only.
  Task READMEs define scope/instructions—planning and execution details belong in the task’s `plan/` folder.
- Every `README.md` must link to:
    - Its plan folder under `doc/ai/tasks/T###_<slug>/plan/` (and related subtask checklists) for execution detail.
    - Relevant commits, research notes, or supporting artifacts.
    - A Feedback section with open problems, outstanding questions, and learnings.

## Task Overview
| Task ID | Title | Status | Plan Folder | GitHub Issue | Notes |
|---------|-------|--------|-------------|--------------|-------|
| T000 | Replace this row with your first real task | Proposed | _(Plan pending)_ | — | Remove once T001 is created |

Guidance:
- Mark exactly one row as **Active** so the current focus is obvious.
- Keep the GitHub issue link synchronized with its current `status:*` label.
- Append new rows at the bottom to preserve chronology.

## Plan Usage
- Planning artifacts live inside each task’s `plan/` directory (see the table above for quick links).
- Keep those plan files up to date; never overwrite another task’s plan when starting a new effort.
- Reference `AGENTS.md` for repository-wide workflow expectations.
- Keep this index/table in sync so future agents can immediately locate the active plan.

## Creating a New Task
1. Copy `doc/ai/templates/task_plan_README.template.md` to `doc/ai/tasks/T###_<slug>/plan/README.md` and
   fill in the placeholders.
2. For each subtask, copy `doc/ai/templates/subtask_plan_README.template.md` into `plan/subtask_S###_<slug>/README.md`.
   Keep the commit + feedback checklist items intact.
3. Open a GitHub issue via `.github/ISSUE_TEMPLATE/task.yml`, apply the `task` label and a single
   `status:*` label, then create a draft PR from `task/T###_<slug>` → `development` with "Closes
   #<issue>" in the body.
4. Update this table whenever statuses change or new tasks spin up.
