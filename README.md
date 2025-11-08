# Workflow-Ready Template

This repository packages the AGENTS-first workflow from `llm-agent-dock` so you can add it to a brand-new
project or retrofit an existing one without rewriting the guardrails.

## Prerequisites
- Provide a Python virtual environment at `.venv/` (POSIX) or `.venv\\Scripts` (Windows). Commit hooks
  and helper scripts assume they can call `.venv/bin/python`.
- Decide whether you are starting a **new project** or enhancing an **existing project** and follow the
  matching flow below. Both paths end with planning your first task.

## Flow A — New Project
1. **Get the code**: fork the repo, click “Use this template,” or download the latest release tarball
   (`workflow-ready-template.tar.gz`) and extract it into an empty directory.
2. **Rough in your README**: replace `README.md` with a plain-language description of what you are
   building (audience, problem, constraints).
3. **AI assist**: prompt your coding assistant with “help me improve README” (or “assist in describing
   the project initially in README”) and iterate until it matches your launch goals.
4. **AGENTS tune-up**: once the basics are captured, prompt “help me update and complete AGENTS.md” so
   the workflow file reflects your tooling, branching strategy, and test expectations.
5. **Plan a task**: copy `doc/ai/templates/task_plan_README.template.md` into
   `doc/ai/tasks/T001_<slug>/plan/README.md`, add at least one subtask plan, then follow the shared
   steps in “After Both Flows.”

## Flow B — Existing Project (Keep Your README)
You are not cloning this repo. Instead, download the latest release archive and copy everything except
`README.md` into your project.

### Linux / macOS
```bash
curl -L https://github.com/Wuodan/workflow-ready-template/archive/refs/tags/latest.tar.gz \
  -o /tmp/workflow-ready-template.tar.gz
mkdir -p /tmp/workflow-ready-template
tar --strip-components=1 -xzf /tmp/workflow-ready-template.tar.gz \
  -C /tmp/workflow-ready-template
rm -f /tmp/workflow-ready-template/README.md
rsync -av --ignore-existing /tmp/workflow-ready-template/ ./
```

### Windows (PowerShell)
```powershell
$zip = "$env:TEMP\workflow-ready-template.zip"
Invoke-WebRequest -Uri "https://github.com/Wuodan/workflow-ready-template/archive/refs/tags/latest.zip" -OutFile $zip
$extract = "$env:TEMP\workflow-ready-template"
if (Test-Path $extract) { Remove-Item $extract -Recurse -Force }
Expand-Archive -LiteralPath $zip -DestinationPath $extract -Force
$content = Get-ChildItem $extract | Select-Object -First 1
Remove-Item "$($content.FullName)\README.md"
robocopy "$($content.FullName)" . /E /NFL /NDL /NJH /NJS /XO
```

1. **Keep your README**: leave your existing README untouched; the copied files add workflow docs,
   templates, `.gitignore`, and the issue form.
2. **AI assist**: still run “help me improve README” so the assistant can spot gaps without deleting
   your current content.
3. **AGENTS tune-up**: prompt “help me update and complete AGENTS.md” to merge the template guardrails
   with your project’s process.
4. **Plan a task**: scaffold `doc/ai/tasks/T001_<slug>/plan/README.md` using the templates before moving
   on to the shared steps.

## After Both Flows
1. Update `doc/ai/tasks/README.md` with your first task row and mark it **Active**.
2. Open the GitHub issue via `.github/ISSUE_TEMPLATE/task.yml`, then create a draft PR from
   `task/T001_<slug>` → `development` (or your main branch) that says “Closes #<issue>.”
3. Mirror every Progress Log entry from the task plan into the draft PR comments so reviewers stay in
   sync.
4. Keep the `.venv/` Python environment healthy so commit hooks (e.g., `devtools/check_commit_message.py`)
   run locally.

## Files Included
| Path | Purpose |
|------|---------|
| `README.md` | This setup guide with the two adoption flows. |
| `AGENTS.md` | Workflow guardrails (planning, branching, mirroring). |
| `.github/ISSUE_TEMPLATE/task.yml` | Issue form aligned with the task plan template. |
| `.gitignore` | Baseline ignores for editors, Python, Node, etc. |
| `doc/ai/tasks/README.md` | Task index scaffold explaining statuses and links. |
| `doc/ai/templates/task_plan_README.template.md` | Task planning template (estimate snapshot + retro). |
| `doc/ai/templates/subtask_plan_README.template.md` | Subtask planning template (checklists + retro). |
| `devtools/check_commit_message.py` | Optional helper for enforcing `T###/S###` commit subjects. |

## License
Apache 2.0 – see `LICENSE` for details.
