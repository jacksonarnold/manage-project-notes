# Start a Task or Focus

Load the context needed to work cold. Task state is optional, and starting work never creates a progress entry.

## Resolve the project and requested work

Use the project established in the conversation or an explicit project name. Treat remaining invocation text as a task identifier, title, issue, or focus.

Read the same active context used by [show-project-status.md](show-project-status.md), narrowed to the requested work.

When the plan records a delivery strategy, also resolve the selected task's parent increment, observable outcome, integration rule, review boundary, and validation surface. Treat a phase or slice label alone as insufficient evidence of those properties.

## With a task-board plan

When no task is supplied, propose the earliest `Ready` task whose dependencies are `Completed`. Ask when multiple tasks are equally eligible or the intended task remains ambiguous.

Before changing task state:

- A `Ready` task may move to `In Progress`.
- An already `In Progress` task needs no write.
- A `Blocked` task requires explicit resolution of its blocker or an explicit user override.
- A task in `In Review`, `Completed`, `Deferred`, or `Cancelled` requires explicit instruction to reopen or start it.

If the selected task materially contradicts the recorded delivery strategy or depends on an unrecorded exception, remain read-only and surface the mismatch before starting it. A `Ready` status does not silently override the strategy. Proceed only after the plan is revised or the user explicitly approves and records the exception.

Draft plan status does not block an explicit start.

Re-read `plan.md` immediately before writing and change only the selected task's status. In a maintenance plan, move that complete task block from Queue to the end of Active Work. Never mark other tasks inactive, assign global ownership, or create an active-task pointer.

## Without a task-board plan

For a missing plan or a narrative plan, establish the named issue or focus in the conversation and remain read-only. Do not create or convert `plan.md` merely to start work.

## Surface the working context

Return the scope or focus, its parent increment's observable outcome and validation boundary when present, acceptance criteria, relevant decisions, latest handoff, blockers or open questions, and the first concrete move. Explain what this task makes independently reviewable or how it contributes to the next integrated checkpoint. Do not claim the work is unblocked when the notes show unresolved dependencies.
