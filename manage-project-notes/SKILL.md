---
name: manage-project-notes
description: Manage a flexible local project workflow under a workspace's project-notes directory. Use when the user wants to initialize or adopt project notes, run discovery, choose a delivery strategy, create or revise a task plan, derive project status, start work, record a durable decision, create an explicit handoff, or explicitly compact or archive project context. Do not use for ordinary implementation plans or generic session summaries.
---

# Manage Project Notes

Maintain enough durable context for another session to resume the project without forcing every project through the same lifecycle or document set.

## Resolve the notes root

Resolve the notes root in this order:

1. An explicit path supplied by the user.
2. `<git-root>/project-notes` when the working directory is inside a Git repository.
3. `<current-working-directory>/project-notes` otherwise.

Follow a symlinked `project-notes` directory normally. If the environment requires permission to read or write the resolved target, request it instead of redirecting the work elsewhere.

Initialization may create a missing notes root and project directory. For every other action, report a missing resolved path rather than creating it. Match an exact project directory name first, then an unambiguous normalized title. Ask when multiple projects match.

Project identity belongs to the current conversation. Never create an active-project pointer, ownership marker, or session file.

## Route the request

Read only the references needed for the requested action:

- **Initialize or adopt a project:** [references/initialize-project.md](references/initialize-project.md)
- **Explore, converge, or reopen discovery:** [references/discover-project.md](references/discover-project.md)
- **Choose or revise how increments are delivered and reviewed:** [references/delivery-strategy.md](references/delivery-strategy.md)
- **Create, approve, or revise a plan:** [references/plan-project.md](references/plan-project.md)
- **Derive read-only project status:** [references/show-project-status.md](references/show-project-status.md)
- **Start a task or untracked focus:** [references/start-work.md](references/start-work.md)
- **Create an explicit handoff:** [references/create-handoff.md](references/create-handoff.md)
- **Record or propagate a durable decision:** [references/record-decision.md](references/record-decision.md)
- **Compact progress or archive documents:** [references/compact-project-notes.md](references/compact-project-notes.md)
- **Interpret the progressive layout or create an optional brief:** [references/note-schema.md](references/note-schema.md)

When the user requests several actions together, read each applicable reference and perform the work as one coherent update.

## Invariants

- Treat the workflow as a menu. Initialization, discovery, planning, status, start, handoff, and decision commands are independently usable.
- When a plan spans multiple layers, systems, review units, or releases, make its delivery strategy explicit before detailed task decomposition. Choose the strategy from the project's context; vertical slicing is not a universal requirement.
- `README.md` and `progress-log.md` are the minimum baseline. Missing optional documents and missing task state are valid.
- Never create a handoff because work ended, a change was submitted, context is running low, or a final response is being written. A handoff requires an explicit user request.
- Only a handoff may add an entry to `progress-log.md`.
- Never compact the progress log or archive documents automatically. Maintenance requires an explicit user request.
- Status is derived from current notes; never store a separate status file.
- Preserve unknown history as unknown when adopting work already in progress.
- Preserve raw history. Archiving moves content; it never deletes it.
- Re-read any shared file immediately before changing it and make the narrowest possible edit so parallel sessions are preserved.
- Keep facts in the smallest useful number of files. Do not create optional structure speculatively or duplicate the same state across documents.
