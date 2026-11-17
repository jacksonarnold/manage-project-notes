# Initialize or Adopt a Project

Use this workflow only when the user explicitly asks to initialize, adopt, or create project notes.

## Gather the minimum useful context

Determine the project title, preferred slug when supplied, intended outcome, current operating mode, and durable source links. Use supplied specifications, tickets, changes, code, and existing notes as evidence. Ask only when a missing answer materially changes project identity or would cause the wrong directory to be created.

Describe the operating mode in ordinary prose, not a rigid enum. Examples include a sequenced delivery, a small focused change, or maintenance and support with an interrupt-driven queue.

## Handle an existing project directory

If `<notes-root>/<slug>` already exists, inspect and manage it rather than overwriting it or creating a duplicate. Preserve every existing document.

If either baseline file is missing, create only the missing file when the invocation clearly asks to initialize or repair the project notes. Derive its content from evidence and leave uncertainty explicit.

## Create a new baseline

1. Create `<notes-root>/<slug>/`.
2. Adapt [the project README](../assets/templates/project-readme.md) with the known overview, source links, and current operating mode.
3. Add only the progress-log link to the README's project-documents section.
4. Adapt [the progress log](../assets/templates/progress-log.md).
5. Verify both files and their link.

Do not create a brief, discovery document, decision ledger, plan, task state, archive, empty directory, or initial handoff. Those artifacts appear later only when their workflows need them.

## Adopt work already in progress

Reconstruct only what available evidence supports:

- Current intended outcome and stable scope
- Verified completed outcomes
- Verified work in progress
- Known queued work, blockers, and source links

Put the durable overview and current operating mode in `README.md`. Do not invent dates, prior sessions, task transitions, rationales, or a completed-work narrative. Unknown history remains unknown, and adoption itself is not a handoff.

After initialization, report the created or repaired baseline and suggest the most relevant independent next command without requiring a lifecycle order.
