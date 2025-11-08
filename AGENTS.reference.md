# Workflow Guardrails Reference

Use this file as the source material for your real `AGENTS.md`. Copy it, keep the sections that fit
your project, and add product-specific guidance. The rules assume an AGENTS-first workflow with
numbered tasks (`T###`) and subtasks (`S###`).

## Workflow Hardening
- **Planning trail**: Every task `T###` lives under `doc/ai/tasks/T###_<slug>/` with a fully populated
  `plan/README.md` based on `doc/ai/templates/task_plan_README.template.md`. Each subtask has its own
  folder using `subtask_S###_<slug>/README.md` copied from the subtask template.
- **GitHub task issues**: Mirror each task using `.github/ISSUE_TEMPLATE/task.yml`. Apply the `task`
  label plus exactly one `status:*` label (`status:proposed`, `status:active`, `status:blocked`,
  `status:needs-review`, `status:completed`). Update the issue only for scope or status changes and
  link to it from every plan.
- **Task branches + PRs**: Create `task/T###_<slug>` from your main development branch. Open a draft PR
  immediately with the body “Closes #<issue>” plus a short scope summary. Keep the PR open throughout
  the task and never merge locally into the main branch.
- **Progress log mirroring**: Any Progress Log entry in a plan must be mirrored as a comment in the
  corresponding PR so reviewers stay up to date without digging into local docs.
- **Estimate snapshots & retro metrics**: Keep the template blocks up to date. If projected token use
  increases ≥1 bucket (≈≥5%), update the Estimate Snapshot, call it out in the Progress Log, and note
  it on the PR. Fill the Retro Metrics section within one session of finishing a task/subtask.
- **Research hygiene**: Capture URLs + summaries for any external research inside the relevant plan or
  `doc/ai/research/` folder. Avoid duplicating lookups; reference the existing note instead.
- **Documentation scope**: Product usage belongs in `README.md`. Process/workflow rules live in
  `AGENTS.md` or contributor docs. AI-only instructions stay under `doc/ai/**`.

## Branch & Commit Workflow
1. Start from the latest `development` (or your chosen main branch): `git checkout development &&
   git pull --ff-only origin development` before branching.
2. Create task branches as `task/T###_<slug>` and push them right away. For subtasks, branch from the
   task branch tip using `subtask/T###_S###_<slug>` and push immediately to keep remote history in
   sync.
3. Merge subtask branches back into the task branch with `git merge --no-ff subtask/...` once the
   subtask checklist is complete. Never merge the task branch directly into `development`; rely on the
   PR merge button after reviews/tests.
4. Commit subjects must follow `T###/S###: short summary` (use `S000` for task-wide commits). Run any
   provided commit hooks or lint scripts that enforce this format.
5. Force pushes are forbidden on shared branches. Only force-push a private, unpublished subtask
   branch to excise sensitive data, and document the reason in the plan Feedback section.

## Task Catalog & Status Visibility
- Maintain `doc/ai/tasks/README.md` as the single index of tasks. Exactly one row should be marked
  **Active** to show where contributors should focus.
- Ensure the GitHub issue’s `status:*` label matches the Active row. Update both the issue and the
  table when the task state changes.
- Before ending a session, push your branch, add a Progress Log entry, and leave the same note on the
  PR. A new agent should need only the latest log entry + checklist to resume.

## Testing & Tooling Expectations (Customize as Needed)
- Document the canonical build/test commands in `README.md` or `scripts/README.md`. If Docker images
  or CLIs are involved, include smoke tests under `tests/` (Bats is a good default for shell-based
  projects).
- Before running heavy build/test jobs, record the command + rationale in the active task plan so the
  cost stays visible. Capture relevant logs or summaries in the PR if reviewers need them.
- Keep `.gitignore` up to date to prevent local artifacts (`.venv/`, `.DS_Store`, editor folders) from
  leaking into commits.

## Security & Configuration Tips
- Keep secrets out of source control; inject via environment variables, CI secrets managers, or BuildKit
  secrets.
- Pin container base images or third-party dependencies to known-good versions. Revisit regularly for
  security advisories.
- Document telemetry or external service opt-outs directly in Dockerfiles/scripts so adopters know how
  to disable them.

## Feedback & Continuous Improvement
- Each plan (task + subtask) needs a Feedback section that lists open problems, questions, and
  learnings. Update it as you go so the next contributor has a clear starting point.
- When making workflow changes, perform a quick token-cost analysis. If the change is likely to add
  ≥5% overhead, pause and get approval from the project owner before proceeding.
- Retro metrics should highlight variance drivers. If confidence drops to Low or token usage jumps by a
  bucket, call it out immediately in both the Progress Log and task PR comment thread.

Copy this file into your real `AGENTS.md`, personalize the sections, and delete anything that doesn’t
apply. The goal is to keep instructions concise enough for humans while still being explicit for
agents.
