# Create a Project Handoff

Run this workflow only when the user explicitly requests a handoff or explicitly asks to record the current session in the project progress log. Never infer a handoff from task completion, a context switch, or conversational context.

## Resolve the session focus

Use the project established in the current conversation. If none is established or more than one project has been discussed, ask which project should receive the handoff.

Review this session and corroborate material outcomes with available workspace evidence. Capture this session only. If a task-board plan exists, resolve the active task from an explicit reference, the session context, or a single matching `In Progress` task. Ask when the task remains ambiguous.

## Record local decisions first

For each explicit durable decision whose impact stays within the current task or focus, follow [record-decision.md](record-decision.md) and link the ledger entry from the handoff.

Do not propagate a cross-cutting decision during handoff. Link it if `$project-decision` already recorded it; otherwise identify it as pending and direct the user to `$project-decision` so the affected set can be confirmed.

## Update optional task state

If a task-board task is active, determine its resulting state from the user's request and corroborating evidence:

- unfinished work: `In Progress`
- ready for review: `In Review`
- unable to proceed: `Blocked`, with the blocker recorded
- finished outcome: `Completed`

Do not infer `Completed` merely because a session ended. Ask when the intended state is ambiguous. Re-read `plan.md` immediately before writing and change only the active task's status, next move, and blocker fields that the handoff establishes. In a maintenance plan, move the complete task block to Active Work or Completed when its new status changes section groups; do not move delivery tasks out of their phases.

With no task-board plan, record the focus normally and create no task state or plan.

## Prepend exactly one handoff

If `progress-log.md` is missing in an existing project, adapt [the progress-log template](../assets/templates/progress-log.md). Use the current local date, time, and timezone:

```markdown
## 2026-08-28 14:32 CDT — Routing contract
- Focus: 1.1 — Implement routing contract
- Done: <material outcome>
- Verified: <highest meaningful integration or evidence boundary actually exercised>
- Decisions: [Decision title](decisions.md#decision-title)
- Next: <single concrete continuation step>
- Blockers: None
```

Use `Focus: <untracked issue or workstream>` when no task exists. Include `Verified` when meaningful validation occurred, and distinguish isolated checks from an end-to-end, operational, migration, or evidence boundary. Omit it when nothing material was verified. Never claim the plan's promised integration boundary merely because component or layer tests passed. Omit the Decisions line when none were recorded. Use `Blockers: None` only when that is supported; otherwise name the blocker or open question.

Immediately before writing, re-read all of `progress-log.md`. Insert one block immediately after `# Progress Log`, above every prior handoff. Keep `## Condensed context` as the final section. If the file changed or the edit conflicts, re-read and retry without replacing another session's entry.

Keep the entry high-level. Do not list routine commands, every changed file, conversation history, or investigation that produced no durable result. Creating a handoff does not authorize unrelated plan, scope, or archive changes.

Return a concise handoff summary with current state, next move, blockers, and open questions.
