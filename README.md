# Workflow-Ready Template

A minimal starter to drop the AGENTS-first workflow into any repo. No history rewrites, no ceremony.

## Prerequisite
- Keep a Python environment at `.venv/` (`.venv/bin/python` or `.venv\Scripts\python.exe`) so commit hooks can run.

## Flow A — Brand-New Project
1. Fork / “Use this template” / download the release archive and unpack it into an empty folder.
2. Replace `README.md` with a rough description of what you are building.
3. Prompt your coding assistant: **“Help me improve README.”** Iterate until it’s presentable.
4. Prompt: **“Help me update and complete AGENTS.md.”** Trim/add sections so it reflects your tools, CI, and branching rules.
5. Copy `doc/ai/templates/task_plan_README.template.md` into `doc/ai/tasks/T001_<slug>/plan/README.md`, spin up at least one subtask plan, and continue with “Shared Next Steps.”

## Flow B — Existing Project
1. Download the latest release archive (zip/tar). No need to clone this repo.
2. Copy every file into your project **except** the root `README.md`. (Use whatever archive/extract tooling you like; overwrite only if you mean it.)
3. Run **“Help me improve README”** so the assistant proposes additive edits without nuking your current content.
4. Run **“Help me update and complete AGENTS.md”** to weave the workflow guardrails into your existing process.
5. Create `doc/ai/tasks/T001_<slug>/plan/README.md` from the template just like Flow A before touching production code.

## Shared Next Steps
1. Update `doc/ai/tasks/README.md` with T001 and mark it **Active**.
2. Open the GitHub issue via `.github/ISSUE_TEMPLATE/task.yml`, then open a draft PR from `task/T001_<slug>` to your integration branch with “Closes #<issue>.”
3. Mirror every Progress Log entry from the plan into the draft PR comments.
4. Keep `.venv/` healthy so tools like `devtools/check_commit_message.py` don’t break mid-task.

## License
Apache 2.0 – see `LICENSE` for details.
