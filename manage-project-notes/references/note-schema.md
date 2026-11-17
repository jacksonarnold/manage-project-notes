# Progressive Project Note Schema

Every project starts with only the baseline files. Add an optional document when the project actually needs the responsibility it owns.

```text
project-notes/<project-slug>/
├── README.md
├── progress-log.md
├── brief.md              optional stable scope
├── discovery.md          optional unresolved design work
├── decisions.md          optional current decision ledger
├── plan.md               optional sequencing or work queue
├── decisions/            supported legacy decision records
└── archive/              created only by explicit maintenance
    ├── index.md
    ├── progress/
    └── documents/
```

## File ownership

- `README.md`: stable entrypoint, overview, source links, current operating mode, and links only to documents that exist.
- `progress-log.md`: explicitly requested session handoffs in reverse chronological order, followed by condensed context derived from archived handoffs.
- `brief.md`: stable goal, scope, non-goals, constraints, success criteria, and dependencies when that material is too substantial for the README.
- `discovery.md`: active constraints, tagged open questions, partial investigation findings, and lean approach notes.
- `decisions.md`: current reverse-chronological decision ledger.
- `plan.md`: optional delivery sequence, delivery strategy and increment boundaries when material, maintenance queue, or an existing narrative milestone plan.
- `decisions/`: legacy decision documents. Continue reading them; do not migrate them automatically.
- `archive/`: verbatim historical material created only by an explicit compaction or archive request.

When creating an optional document, adapt its template and add one link to it under `README.md`'s project-documents section. Never add links to files that do not exist.

Create `brief.md` only when the user explicitly asks to capture stable scope or when stable scope has clearly outgrown the README. Creating or updating a brief never adds a progress entry.

## Read order

Read only files that exist:

1. `README.md`
2. `brief.md`
3. `plan.md`
4. All of `progress-log.md`
5. `decisions.md`
6. Relevant records under `decisions/`
7. `discovery.md` when the request involves unresolved questions or approach work

Read archived material only when an active document links to it, the request needs historical reasoning, or the user explicitly asks.

Newer handoffs and newer accepted decisions take precedence over older or condensed statements when they conflict. Surface unresolved conflicts instead of silently choosing between equally current sources.

## Plan compatibility

A task-board plan contains task headings with stable identifiers and explicit `Status` fields. A milestone table or prose sequence without those fields is a valid narrative plan.

- Status may summarize either plan shape.
- Starting work changes task state only in a task-board plan.
- Do not convert a narrative plan into a task board unless the user explicitly approves that conversion.

## Naming

- Project directory: stable kebab-case slug, such as `call-center-routing`.
- Delivery task: `<increment>.<order>`, such as `1.2`; existing phase-based identifiers remain valid.
- Maintenance task: an existing external identifier, or a stable local identifier such as `M-001`.
- Compacted progress archive: `YYYY-MM-DD-HHmmss.md`, using the local compaction time.
