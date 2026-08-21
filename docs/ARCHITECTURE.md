# Architecture

## Four context classes

```text
                    PROJECT CONTEXT
                          |
       +------------------+------------------+
       |                  |                  |
 Instructions         Knowledge           Skills
       |                  |                  |
       +------------------+------------------+
                          |
                        State
                          |
             +------------+------------+
             |            |            |
        Checkpoint     Decisions    Constraints
                          |
                      Next action
```

## Authority order

When information conflicts:

1. Current explicit user instruction
2. Persistent project instructions
3. Latest verified current state
4. Approved specifications and architecture
5. Approved skills and procedures
6. Reference/source material
7. Prior conversations
8. Unverified assumptions

A material contradiction should be surfaced rather than silently reconciled.

## Retrieval depth

PCP uses a simple three-depth model:

### L0 — Orientation
Use titles, summaries, current state, and short abstracts to determine what is relevant.

### L1 — Working context
Read the specific decision, specification section, skill, or overview required for the task.

### L2 — Detail
Read full code, source material, logs, reports, or detailed documents only when required.

## State transition

```text
Existing verified state
        |
     Work session
        |
      Verify
        |
Durable change occurred?
        |
       yes
        |
Update CURRENT_STATE / DECISIONS / CONSTRAINTS
```

The conversation is not the state transition record. The durable project files are.
