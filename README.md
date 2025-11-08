# Workflow-Ready Template

This repository bootstraps new projects with the same AGENTS-first workflow used in `llm-agent-dock`.
It keeps the instructions lightweight so you (and your coding agent) can customize the docs as soon as
real project details exist.

## Quickstart Checklist
1. **Create your repo** – use "Use this template" on GitHub or clone and `git push` to a new remote.
2. **Fill in the blanks** – rename this README + `AGENTS.md` with your project name, goals, and any
   environment constraints. The included `AGENTS.reference.md` captures the reusable guardrails.
3. **Stand up planning** – copy `doc/ai/templates/task_plan_README.template.md` into your first task
   folder (`doc/ai/tasks/T001_<slug>/plan/README.md`) and add at least one subtask plan. Update the
   task index (`doc/ai/tasks/README.md`) so future collaborators can find the active work fast.
4. **Open the GitHub issue + draft PR** – use `.github/ISSUE_TEMPLATE/task.yml`, then immediately open
   a draft PR from `task/T001_<slug>` → `development` (or your default branch) that says
   "Closes #<issue>".
5. **Mirror progress** – every time you add a Progress Log entry to a plan, mirror it as a comment on
   the task PR so async reviewers stay in sync.

## Template Contents
| Path | Purpose |
|------|---------|
| `README.md` | Human-facing overview + onboarding steps (you are here). |
| `AGENTS.md` | Minimal kickstart guide that helps an agent collect project details and customize the real docs. |
| `AGENTS.reference.md` | Full set of workflow guardrails to copy/paste into your final AGENTS.md once tailored. |
| `.github/ISSUE_TEMPLATE/task.yml` | Issue form that keeps GitHub + local plans aligned. |
| `.gitignore` | Sensible defaults for Python/Node/editor artifacts. |
| `doc/ai/tasks/README.md` | Task index to track `T###` folders, statuses, and GitHub issue links. |
| `doc/ai/templates/task_plan_README.template.md` | Task planning template with estimate + retro sections. |
| `doc/ai/templates/subtask_plan_README.template.md` | Subtask planning template with guardrails + retro metrics. |

## How to Customize
- Replace `Workflow-Ready Template` with your actual project name in README + AGENTS documents.
- Copy relevant sections from `AGENTS.reference.md` into `AGENTS.md`, trimming anything you do not need.
- Decide whether the default branch should remain `development` or change; update the instructions if
  you use a different mainline.
- Keep instructions scoped to your project: product usage belongs in `README.md`, workflow rules stay
  in `AGENTS.md`, and AI-only notes live under `doc/ai/**`.

## Need a Place to Log Research?
Create `doc/ai/research/` and drop short markdown notes there. Reference them from your task plans so
future agents can reuse the findings without re-running searches.

## License
Apache 2.0 – see `LICENSE` for details.
