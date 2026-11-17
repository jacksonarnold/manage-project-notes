# Record or Propagate a Project Decision

Record an explicit durable choice that affects project scope, architecture, sequencing, constraints, or future work. Routine implementation choices, guesses, and discarded ideas do not belong in the decision ledger.

## Record the decision

1. Search both `decisions.md` and legacy `decisions/` records for the same topic.
2. Reuse an existing accepted decision when it already represents the choice.
3. If `decisions.md` is missing, adapt [the decisions template](../assets/templates/decisions.md) and add its link to `README.md`.
4. If a legacy `decisions/` directory exists, add this line below the ledger title without copying its contents:

   ```markdown
   > Earlier decision records remain in [decisions/](decisions/).
   ```

5. Prepend the new entry immediately below the title and optional legacy pointer:

   ```markdown
   ## 2026-08-28 — Decision title
   - Decision: <what was decided>
   - Rationale: <why>
   - Supersedes: <prior title/date or link>  <!-- omit when unused -->
   - Affects: <tasks or areas>              <!-- omit when unused -->
   ```

State uncertainty as an open question rather than inventing rationale. If the new decision supersedes a legacy document, the explicit decision workflow may mark only that document `Superseded` and link the new ledger entry; never rewrite unrelated legacy records.

Recording a decision never adds a progress entry.

## Determine whether propagation is needed

If there is no task-board plan or the decision stays within the current focus, finish after recording it and make only directly requested local updates.

When the decision changes other planned tasks or invalidates discovery, read the current plan and discovery, then present the complete proposed impact set before changing either file. Include each affected task's current status, the needed change, any follow-up work, and each question to reopen. Wait for confirmation of that set.

## Propagate after confirmation

Re-read each shared file immediately before changing it:

- `Ready`, `Blocked`, or `Deferred`: update the task scope, acceptance criteria, dependencies, or blocker state to match the decision.
- `In Progress` or `In Review`: preserve the original spec and add a clearly labeled decision-impact note. Surface that existing work may need revision.
- `Completed`: never rewrite the completed task. Create a follow-up task only when the confirmed impact set explicitly includes it.
- `Cancelled`: leave it unchanged unless the user explicitly reopens it.
- Invalidated discovery: restore each question under Open Questions with `[investigate]` or `[ask]`.

Update the decision entry's `Affects` line to match what was actually confirmed and changed. Report recorded, updated, flagged, deferred, and reopened items separately.
