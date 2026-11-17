# Show Derived Project Status

Answer where the project stands and what can happen next. This workflow is always read-only; never create or update project notes while deriving status.

## Load current context

Read the README, optional brief and plan, complete active progress log, current decision ledger, relevant legacy decisions, and discovery when unresolved questions affect the requested focus. The first handoff block in `progress-log.md` is the latest session record.

## With a task-board plan

Group tasks by status in this order:

1. In Progress
2. In Review
3. Blocked
4. Ready
5. Deferred
6. Completed
7. Cancelled

Within each group, preserve delivery order for phase identifiers and document order for maintenance work. Surface unknown status values explicitly rather than dropping those tasks.

Identify the next eligible task as the earliest `Ready` task whose listed dependencies are `Completed`. Do not claim that a task with unknown or unmet dependencies is ready. Summarize the latest handoff's next move, active blockers, relevant decisions, and overlap with work already in progress.

When the plan records a delivery strategy, also report the current or next increment's observable outcome, review boundary, validation surface, and highest integration boundary actually verified by current evidence. Distinguish completed layer work from integrated progress. Surface a material mismatch between task decomposition and the recorded strategy rather than describing the plan by its labels alone.

## With a narrative plan or no plan

Do not invent tasks or statuses. Show:

- Goal and current operating mode
- Current narrative milestones when present
- Latest material handoff and next move
- Known blockers and open questions
- Decisions relevant to the requested focus
- The clearest evidence-backed next outcome, or state that no next outcome is recorded

When a narrative plan records a delivery strategy, include its next observable increment and validation boundary without inventing task state.

When discovery is active and no task-board plan exists, also derive one planning-readiness outcome using [the discovery criteria](discover-project.md): `Ready to plan`, `Ready to plan with explicit blocked tasks`, or `Not ready to plan`. Name the exact questions supporting that outcome. Treat a consequential unclassified question conservatively rather than using total question count as the signal.

An optional invocation focus narrows which decisions, questions, and source material to load; it never mutates the project or claims ownership of the focus.
