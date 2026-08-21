# Quickstart

## Initial setup

Copy these files into your AI project:

```text
PROJECT_CONTEXT_PROTOCOL.md
CURRENT_STATE.md
DECISIONS.md
CONSTRAINTS.md
```

Add your existing specifications, reference material, architecture documents, and skills.

## Give the model one instruction

```text
Use PROJECT_CONTEXT_PROTOCOL.md as the governing context protocol for this project.
```

## Start work

Use:

```text
Continue from the current project state.
```

The model should recover the current objective, checkpoint, relevant constraints, decisions, and skills before continuing.

## After substantive work

Use:

```text
Update the project state from what we just completed.
```

Save the resulting state back into `CURRENT_STATE.md`.

## When an answer must be grounded

Use:

```text
Verify this against the project files before answering.
```

## When a decision must survive future chats

Use:

```text
Record this as a project decision.
```

Save it into `DECISIONS.md`.

## Operating rule

Do not use the chat transcript as the only record of important project state.

Anything that future work must reliably know belongs in a durable project file.
