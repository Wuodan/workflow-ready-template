# Workflow-Ready Template

This repository copies the workflow guardrails from `llm-agent-dock` so you can drop them into any
project without recreating the planning/PR discipline by hand.

## How to Use It
1. **Clone or fork this repository** (or click “Use this template” on GitHub) and point it at your
   new or existing project.
2. **Starting a new project?** Replace this `README.md` with a rough description of what you are
   building, then ask your AI assistant “help me improve README” (or “assist in describing the
   project initially in README”). Iterate until the README matches your launch goals.
3. **Already have a project?** Keep your existing README exactly as it is and copy the remaining files
   from this repo into the project so the workflow docs, templates, and issue form come along for the
   ride.
4. **Follow `AGENTS.md`** to run the planning workflow (task catalog, subtasks, GitHub issue/PR
   mirroring). Update the task index as soon as you start T001 so future collaborators land on the
   right folder.

## Files Included
| Path | Purpose |
|------|---------|
| `README.md` | This setup guide for humans adopting the template. |
| `AGENTS.md` | Full workflow guardrails (checklists, branching rules, progress-log mirroring). |
| `.github/ISSUE_TEMPLATE/task.yml` | GitHub issue form that mirrors the task plan structure. |
| `.gitignore` | Basic ignores for common local artifacts. |
| `doc/ai/tasks/README.md` | Task index scaffold with instructions for maintaining `T###` rows. |
| `doc/ai/templates/task_plan_README.template.md` | Task planning template (estimate snapshot + retro). |
| `doc/ai/templates/subtask_plan_README.template.md` | Subtask planning template (checklists + retro). |

## After Copying
- Add your first task folder (`doc/ai/tasks/T001_<slug>/`) using the included templates.
- Open the matching GitHub issue via `.github/ISSUE_TEMPLATE/task.yml`, then create the draft PR from
  `task/T001_<slug>` to your development branch with “Closes #<issue>” in the body.
- Mirror every Progress Log entry from the plan into the draft PR comments so async reviewers stay in
  sync.

## License
Apache 2.0 – see `LICENSE` for details.
