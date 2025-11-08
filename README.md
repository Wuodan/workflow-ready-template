# Workflow-Ready Template

A minimal starter to drop the AGENTS-first workflow into any repo.

## Prerequisite

- Keep a Python environment at `.venv/` so commit hooks can run.

## Usage

1. Download the [latest release archive](https://github.com/Wuodan/workflow-ready-template/releases/latest) (zip/tar).
2. Copy every file into your project except this `README.md`.
3. New projects only:
    - Add a `README.md` with a rough description of what you are building.
    - Prompt your coding assistant:
      ```
      Help me improve my README.
      ```
1. Add project-specific details to `AGENTS.md`with prompt:
   ```
   Help me complete my AGENTS.md by completing the <to be extended> sections.
   ```
2. Plan a task with:
   ```
   Help me plan a new task. Here's my idea/requirements.
   ```
3. Optionally restart your coding assistant after planning to empty the context window.
4. Then prompt:
   ```
   Read `doc/ai/tasks/README.md` and work on the first task that’s not active or completed.
   ```
