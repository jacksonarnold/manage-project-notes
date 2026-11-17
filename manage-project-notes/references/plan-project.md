# Create, Approve, or Revise a Project Plan

Use `plan.md` only when multiple outcomes need durable sequencing or the project needs a persistent work queue. A small independent focus can proceed without a plan.

## Load the settled context

Read the README and any existing brief, discovery, decisions, plan, and recent handoffs. Inspect the relevant implementation surface before proposing task scope. Open questions may produce blocked or contingent tasks; they do not prevent planning.

Respect discovery planning-impact tags when present. Preserve an unresolved `[planning-blocker]` as an exact blocked prerequisite and warn that it may reshape the draft. Convert `[plan-time]` questions into bounded investigations, dependencies, or blocked tasks. Keep `[deferred]` questions outside the current plan unless the user explicitly brings them back into scope. If discovery is `Not ready to plan`, explain why before drafting, but do not refuse an explicit planning request.

If the project has one independent outcome and no sequencing or queue problem, explain that a plan is optional. Create one only when the user still wants persistent task state.

## Resolve the delivery strategy before decomposition

For work spanning multiple layers, systems, review units, or releases, read [delivery-strategy.md](delivery-strategy.md). Find the current durable delivery-strategy decision, if one exists, and verify that it still fits the requested scope and current evidence.

When the choice is missing or materially stale, inspect the implementation and validation surfaces, present a recommended strategy plus viable alternatives, and obtain the user's explicit choice before writing the detailed task board. A preliminary map or comparison is allowed; do not create detailed tasks whose boundaries presume an unsettled strategy. Do not infer vertical delivery, pull-request size, release readiness, or validation scope from the word `slice`.

Summarize the operative strategy in `plan.md` and link its durable decision when present. Include:

- increment shape;
- review unit;
- validation surface;
- integration rule;
- permitted enabling work or explicit exceptions.

If an existing plan's decomposition conflicts with its recorded strategy, propose a substantive revision instead of silently relabeling the existing tasks. Preserve completed history and current work unless the user explicitly approves changing it.

## Preserve existing plan shapes

If `plan.md` is a milestone table or narrative plan without task status fields, keep that shape. Do not convert it into a task board until the user explicitly approves the proposed conversion. Status and start workflows continue to treat it as a narrative plan until then.

For a new task-board plan, choose the shape that reflects current work:

- **Delivery:** adapt [the delivery plan template](../assets/templates/plan-delivery.md) for work with phases or meaningful dependency order.
- **Maintenance:** adapt [the maintenance plan template](../assets/templates/plan-maintenance.md) for an interrupt-driven active list and queue.

The README's prose operating mode may change over time. Update it narrowly when the user explicitly changes how the project is being run.

## Define increments before tasks

For a delivery plan, define each increment's observable outcome, end-to-end or evidence path, review boundary, validation surface, and incomplete or rollout behavior before splitting it into tasks. Tasks may concentrate on one layer, but the surrounding increment must preserve the selected integration rule. A layer-specific foundation outside an integrated increment must satisfy the recorded enabling-work policy.

When vertical delivery is selected, do not place all backend, interface, and UI integration into successive layers that become usable only in the final task. Prefer the thinnest real path first, then deepen behavior in later increments. When another strategy is selected, use its actual completion boundary rather than forcing a UI-shaped plan.

Run the decomposition audit in [delivery-strategy.md](delivery-strategy.md) before presenting or approving the plan.

## Define task state

Use exactly these task statuses for new task-board plans:

- `Ready`
- `In Progress`
- `In Review`
- `Blocked`
- `Completed`
- `Deferred`
- `Cancelled`

Each task needs a stable identifier, scope, acceptance criteria, next move, dependencies, and blocker state. When the selected review unit is smaller than its parent increment, also name the task's review boundary and validation contribution. Delivery tasks use `<increment>.<order>` identifiers; existing phase-based identifiers remain valid. Maintenance tasks reuse an external ticket identifier or assign the next unused `M-NNN` identifier.

Delivery tasks should be independently reviewable contributions to their parent increment. Increment completion must satisfy the recorded observable outcome and validation surface. Increments run in sequence unless the plan explicitly permits parallel work; tasks within an increment may run in parallel when their dependencies allow it. A task depending on an unresolved question remains in its intended order with `Status: Blocked` and the exact question in `Blocked on`.

In a maintenance plan, section placement is part of the current view:

- `Active Work`: `In Progress`, `In Review`, and `Blocked`
- `Queue`: `Ready` and `Deferred`
- `Completed`: `Completed` and `Cancelled`

When a task changes between those groups, move its complete task block to the end of the matching section after re-reading the plan. Delivery plans retain tasks under their original increments or phases and change only status fields.

## Draft and approval behavior

New plans start with `> Status: draft`. Draft status does not prevent explicit task starts. Change it to `approved` only when the user approves the plan.

A substantive revision to approved scope, delivery strategy, increment boundaries, review units, dependencies, or sequencing returns the plan to `draft` until the user approves the revision. Routine task-state changes do not change plan approval.

Re-read `plan.md` immediately before changing it. Preserve unrelated tasks and parallel-session edits. Link a durable sequencing decision from the plan when it explains a non-obvious change. Never add a progress entry while creating, approving, or revising a plan.
