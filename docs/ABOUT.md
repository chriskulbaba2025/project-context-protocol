# About Project Context Protocol

Project Context Protocol is a lightweight, model-agnostic method for maintaining reliable context across long-running AI work.

Most AI workflows treat conversation history as memory. That works until a project becomes large, changes over time, contains conflicting instructions, or moves between models.

PCP separates project context into four explicit classes:

1. **Instructions** — rules the model must follow.
2. **Knowledge** — source material the model may reason from.
3. **Skills** — reusable methods for how particular work should be performed.
4. **State** — the project's latest verified truth.

This creates a simple operating boundary:

**Conversation is temporary. Project state is durable.**

The protocol does not attempt to replace an LLM's native memory or retrieval system. It gives that system a better structure to retrieve from and a clear authority order when information conflicts.

## Intended users

PCP is useful for:

- product and software projects
- research
- consulting and client work
- governed AI workflows
- content systems
- operations
- long-running analysis
- multi-model workflows
- any project where repeated context reconstruction is becoming expensive or unreliable

## Design goals

PCP is designed to be:

- LLM-agnostic
- human-readable
- portable
- inspectable
- low-overhead
- easy to adopt incrementally
- useful without API access
- compatible with project/file-based AI products
