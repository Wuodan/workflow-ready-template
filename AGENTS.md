# Kickstart Instructions (Workflow-Ready Template)

This repo is a template. Before doing any heavy work, collaborate with the human owner to collect
project-specific context and replace this file with customized guidance. Treat the steps below as a
checklist for that onboarding conversation.

## Immediate Actions
1. **Confirm ownership + goals** – Ask the user what the new project should achieve and which
   repositories/branches already exist.
2. **Gather constraints** – Dependencies, required tools, token budgets, compliance needs, and any
   CI/CD expectations all belong in the real AGENTS file. Capture them now so you can tailor
   instructions.
3. **Plan the first task** – Copy `doc/ai/templates/task_plan_README.template.md` into
   `doc/ai/tasks/T001_<slug>/plan/README.md`, define subtasks, and set up the GitHub issue + draft PR.
4. **Customize docs** – Rename this file to reflect the project’s workflow. Use
   `AGENTS.reference.md` as your starting point and delete this kickstart notice once a real AGENTS
   exists.
5. **Document decisions** – Update `doc/ai/tasks/README.md` with the first task row, status, and issue
   link so future agents land on the same context.

## Working Agreements (Until Replaced)
- Follow the guardrails in `AGENTS.reference.md` for planning, branching, and commit naming.
- Mirror every Progress Log update into the matching task PR comment thread.
- Keep instructions human-readable: product docs stay in `README.md`; AI-specific process lives here
  and in `doc/ai/**`.
- If you need additional tooling (scripts, Dockerfiles, etc.), record the proposal in the task plan
  before adding files so costs stay visible.

## Hand-Off Expectations
- Do not start coding against “real” scopes until the owner confirms the customized README + AGENTS
  are ready.
- Leave a Feedback entry in the active task plan summarizing open questions or follow-ups for the
  next agent.
- Once the project-specific AGENTS is published, archive this file (rename or delete) so the repo no
  longer appears to be in kickstart mode.
