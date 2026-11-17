# Explore, Converge, or Reopen Project Questions

Use discovery whenever unresolved design, product, sequencing, or system questions would otherwise surface during implementation. Discovery is optional and may be opened, converged, or reopened at any stage.

## Load context

Read the existing project documents that bear on the requested focus and inspect relevant source material or code before asking questions answerable from available evidence.

If `discovery.md` exists, continue it without regenerating resolved questions. Surface an existing `> Resume:` pointer first. If unresolved design work exists and the file is missing, adapt [the discovery template](../assets/templates/discovery.md) and add its link to `README.md`.

## Choose behavior from the current state

- **Explore** when discovery is missing, evidence is thin, or the user opens a materially new focus. Build the smallest useful question map and gather evidence before proposing choices.
- **Converge** by default when `discovery.md` already contains substantive evidence and open questions. Drive the existing work toward durable choices and a planning-readiness outcome; do not require a special convergence prompt.
- **Reopen** when new evidence or an explicit scope change invalidates a settled assumption. Preserve the prior decision record and route any replacement through the decision workflow.

Follow an explicit user request to explore more broadly or focus on a particular question instead of inferring a mode from file presence alone.

## Classify open questions

Keep the first tag specific to how a question is resolved:

- `[investigate]`: answerable from code, documentation, data, or other available evidence.
- `[ask]`: requires human intent, priority, authority, or a meaningful tradeoff decision.

During convergence, add a second planning-impact tag to each question as it is assessed:

- `[planning-blocker]`: its answer could materially reshape the intended outcome, scope, security or data boundary, operating model, or acceptance criteria.
- `[plan-time]`: it can be resolved by a bounded investigation, dependency, or blocked task without invalidating the overall plan.
- `[deferred]`: it is outside the agreed current outcome or does not affect the near-term plan.

Existing unclassified questions remain valid. Classify them when working that area instead of mechanically rewriting the document. Treat a consequential unclassified question conservatively when assessing readiness.

## Explore efficiently

Investigate `[investigate]` items before asking the user. Keep partial findings with their question. Ask only about ambiguity that affects a real choice; do not create an exhaustive catalog of hypothetical edge cases.

As the approach firms up, record only working constraints and approach notes that help resolve remaining questions. Do not copy source documents into discovery.

## Resolve delivery strategy when it matters

When the expected work spans multiple layers, systems, review units, or releases, read [delivery-strategy.md](delivery-strategy.md). Investigate the available integration and validation surfaces, then present the highest-leverage delivery-strategy decision during convergence. Do not assume that `slice`, `phase`, `milestone`, or `task` means vertical, pull-request-sized, independently releasable, or independently testable.

Record an approved strategy as a durable decision when it governs multiple tasks or future sessions. If different choices would materially change the detailed task breakdown, treat the unresolved strategy as a planning blocker. Do not impose this checkpoint on one bounded outcome or routine maintenance work where it would add no useful distinction.

## Converge interactively

1. Collapse duplicate or downstream questions whose relevance depends on a more fundamental choice.
2. Finish available investigation that could materially change the next decision.
3. Present the highest-leverage human decision, or one tightly coupled decision bundle, with a recommended answer, viable alternatives, consequences, supporting evidence, and likely decision owner. Do not dump every `[ask]` question at once.
4. After the user answers, record the durable decision and update the affected questions before moving to the next decision.
5. Continue until the user pauses, no planning blockers remain, or progress requires an unavailable external owner or source.

When authority belongs elsewhere, produce a concise decision packet for that owner rather than treating uncertainty as a settled answer.

## Record durable choices

When a durable choice is settled, follow [record-decision.md](record-decision.md), then remove or mark the corresponding question resolved. Do not keep a second decisions section in `discovery.md`.

Discovery may update `discovery.md` and the decision ledger because the user explicitly invoked this workflow. It never creates a progress entry or starts implementation automatically.

## Report planning readiness

When the user asks whether to plan, pauses discovery, or no planning blockers remain, report one of these derived outcomes:

- **Ready to plan:** no unresolved planning blocker remains.
- **Ready to plan with explicit blocked tasks:** remaining uncertainty is bounded and can be represented by exact plan-time dependencies or blocked tasks without reshaping the overall plan.
- **Not ready to plan:** one or more unresolved questions could materially reshape the intended outcome, scope, security or data boundary, operating model, or acceptance criteria.

List the exact blockers, plan-time questions, and deferred questions supporting the outcome. Readiness depends on impact, not question count. Never create or approve a plan automatically.

For substantial delivery work, include an unresolved delivery strategy among the exact blockers when it would change increment, review, integration, or validation boundaries.

## Checkpoint only when asked

Never write a resume pointer merely because the session may end. When the user explicitly asks to checkpoint discovery:

1. Record any settled but unrecorded durable decisions.
2. Preserve partial findings under the active question.
3. Write exactly one `> Resume: <next investigation or decision>` line below the title, replacing any prior resume line.

At the user's stopping point, report decisions captured, remaining questions by planning impact, and the planning-readiness outcome. Do not create a plan unless requested.
