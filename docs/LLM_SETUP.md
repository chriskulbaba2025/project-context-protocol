# Use With Any LLM

Project Context Protocol is intentionally vendor-neutral.

The only requirement is that the model can access the protocol and the project's durable context files.

## Universal base instruction

Place this in the project's persistent instructions, system instructions, workspace instructions, or equivalent:

```text
Use PROJECT_CONTEXT_PROTOCOL.md as the governing context protocol for this project.

Before substantive work:
1. identify the current task;
2. recover the latest relevant verified state;
3. identify relevant decisions, constraints, knowledge, and skills;
4. use only the minimum sufficient authoritative context;
5. do not silently contradict an established project decision or constraint.

Treat conversation as working context and project files as durable context.
```

## ChatGPT Projects

Upload the protocol and state files to the Project.

Put the Universal Base Instruction in Project Instructions.

Start a new conversation with:

```text
Continue from the current project state.
```

After a major change:

```text
Update the project state from what we just completed.
```

## Claude Projects

Add the protocol and project files to Project Knowledge or the project's accessible workspace.

Put the Universal Base Instruction in the project's instructions.

Use the same `Continue from the current project state` command when starting a new session.

## Claude Code / Codex / coding agents

Store the protocol in the repository.

Point the agent's repository instructions to it. Keep `CURRENT_STATE.md`, `DECISIONS.md`, and `CONSTRAINTS.md` at predictable paths.

For code work, durable state should include branch, commit, environment, verified tests, active scope, and exact next action when those details matter.

## Gemini and other project-based assistants

Add the protocol to the persistent project context or knowledge area and use the Universal Base Instruction.

## Local models

Mount or expose the project directory to the model or agent runtime. Inject the Universal Base Instruction into the persistent system/project prompt.

## What not to do

Do not paste the full project history into every new session.

Do not maintain the same fact in several competing state files.

Do not treat old conversation as more authoritative than a newer verified state file.

Do not load every project document for every task.

## Portability principle

The protocol should remain usable even when the model changes.

Store durable truth in files. Store vendor-specific configuration separately.
