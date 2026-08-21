# Project Context Protocol

**A portable context architecture for long-running work with any LLM.**

Project Context Protocol (PCP) turns an AI project from a collection of disconnected chats into a structured working environment built around four durable context types:

- **Instructions** — how work must be done
- **Knowledge** — facts, references, specifications, architecture
- **Skills** — repeatable procedures and governed methods
- **State** — the verified current checkpoint, decisions, constraints, and next action

The protocol is LLM-agnostic. It can be used with ChatGPT Projects, Claude Projects, Gemini, local models, coding agents, or any system that can read project files.

## Why it exists

Long-running AI work usually breaks for one reason: the model has access to a lot of context, but no reliable way to know **what is authoritative now**.

PCP solves that by separating temporary conversation from durable project truth.

> **Chats are working sessions. Project files are durable operating context.**

## Core model

```text
PROJECT
├── Instructions
├── Knowledge
├── Skills
└── State
     ├── Current checkpoint
     ├── Decisions
     ├── Constraints
     └── Next action
```

The model retrieves only the context required for the current task and follows an explicit authority order when sources conflict.

## What this improves

- Less repeated prompting between chats
- Faster recovery when starting a new session
- Lower context clutter
- Fewer contradictions with earlier decisions
- Better continuity across models
- Clear separation between facts, instructions, procedures, and transient conversation
- Easier human review of what the AI believes the current project state is
- Better handoffs between people and models
- More predictable use of project-specific skills and constraints

## 5-minute setup

1. Copy `protocol/PROJECT_CONTEXT_PROTOCOL.md` into your AI project.
2. Copy `templates/CURRENT_STATE.md` into the project and fill in the current checkpoint.
3. Add `DECISIONS.md` and `CONSTRAINTS.md` when the project needs them.
4. Add your existing reference documents, specifications, and skills.
5. Tell your LLM:

```text
Use PROJECT_CONTEXT_PROTOCOL.md as the governing context protocol for this project.
Before substantive work, recover the relevant current state, decisions, constraints,
knowledge, and skills. Prefer the latest verified project state over older conversation.
```

Then start new sessions with:

```text
Continue from the current project state.
```

## Recommended project structure

```text
project/
├── PROJECT_CONTEXT_PROTOCOL.md
├── CURRENT_STATE.md
├── DECISIONS.md
├── CONSTRAINTS.md
├── ARCHITECTURE.md
├── SKILLS/
├── SPECS/
└── REFERENCE/
```

Only create files that materially improve continuity. The protocol does not require every folder.

## Use with any LLM

See [`docs/LLM_SETUP.md`](docs/LLM_SETUP.md).

## Human workflow

See [`docs/QUICKSTART.md`](docs/QUICKSTART.md).

## Design principle

The goal is **not maximum context**.

The goal is:

> **Minimum sufficient authoritative context.**

That means orient first, retrieve only what is relevant, go deeper only when necessary, and preserve durable state separately from chat history.

## Repository contents

- `protocol/PROJECT_CONTEXT_PROTOCOL.md` — portable governing protocol
- `templates/` — ready-to-copy project state files
- `docs/ABOUT.md` — what the protocol is
- `docs/BENEFITS.md` — why it improves long-running AI work
- `docs/LLM_SETUP.md` — instructions for ChatGPT, Claude, Gemini, Codex, local models, and other LLMs
- `docs/QUICKSTART.md` — minimal operating workflow
- `docs/ARCHITECTURE.md` — context architecture and authority model
- `ui/content.json` — structured copy for a future interface or onboarding experience
- `assets/logo.svg` — repository logo asset

## Inspiration and attribution

Project Context Protocol was inspired in part by the context-engineering ideas explored by **OpenViking**, particularly the separation and structured retrieval of memory, knowledge, skills, and working context. PCP is an independent, lightweight, LLM-agnostic project designed for file-based use inside consumer and developer AI workspaces rather than a fork or reimplementation of OpenViking.

Original project: https://github.com/volcengine/OpenViking

## Status

Version 1.0 establishes the portable context protocol and project templates. It intentionally does not depend on a specific model, API, vector database, or vendor-specific memory system.
