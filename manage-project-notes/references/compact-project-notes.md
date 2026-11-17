# Compact Progress and Archive Documents

Run maintenance only when the user explicitly requests compaction or archiving. Never trigger it based on file size, entry count, session start, or session end.

## Compact the progress log

If `progress-log.md` is missing, report that there is no progress history to compact. Unless the user gives a cutoff or specific entries, keep the 10 newest handoff entries active and compact every older entry.

1. Read the complete progress log and any existing archive index. Read optional project documents only when needed to preserve links or condensed context.
2. Parse each handoff as a complete `## <timestamp> — <title>` block between `# Progress Log` and the final `## Condensed context` section.
3. Select the oldest blocks beyond the newest 10, or the exact range the user requested.
4. Lazily create `archive/`, `archive/progress/`, `archive/documents/`, and `archive/index.md` from [the archive-index template](../assets/templates/archive-index.md) when missing.
5. Copy selected blocks verbatim, preserving newest-first order, into `archive/progress/YYYY-MM-DD-HHmmss.md` using the local compaction time. Include the covered handoff date range at the top.
6. Rewrite `## Condensed context` to retain only older facts that still matter: completed outcomes, durable constraints, important discoveries, and links to decisions or archives.
7. Remove selected blocks from the active portion only after verifying the archive contains them verbatim.
8. Link the archive from condensed context and `archive/index.md`.
9. Verify the newest handoffs remain first and condensed context remains the final section.

Newer active handoffs are authoritative when they supersede condensed history. If there are 10 or fewer active handoffs and no explicit range was supplied, report that no compaction is needed and do not rewrite the file or create archive structure.

## Archive supporting documents

Archive only documents the user explicitly identifies or clearly includes in an archive request. Never archive `README.md`, `brief.md`, `discovery.md`, `decisions.md`, `plan.md`, `progress-log.md`, or legacy files under `decisions/`.

1. Lazily create the archive structure when missing.
2. Move each identified supporting document under `archive/documents/`, retaining enough of its original relative path to avoid collisions.
3. Add its original path, archive date, reason, and replacement when applicable to `archive/index.md`.
4. Search active project notes for inbound links and update them to the archived path or replacement.
5. Verify the archived document remains readable and every updated link resolves.

Never delete archived content.
