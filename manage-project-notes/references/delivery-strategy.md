# Select a Delivery Strategy

Choose how work becomes reviewable, testable progress before decomposing a substantial plan. Apply this workflow when the work spans multiple layers, systems, review units, or releases, or when integration risk makes task order consequential. A small independent outcome and an interrupt-driven maintenance queue do not require a separate strategy decision unless their delivery or review boundary is genuinely ambiguous.

Do not infer a delivery strategy from words such as `slice`, `phase`, `milestone`, or `task`. Define what those units mean for this project.

## Inspect the delivery context

Use available evidence to identify:

- the earliest surface where intended behavior can be observed;
- the layers, systems, people, or artifacts that must participate for that behavior to be real;
- the review mechanism, such as a pull request, change set, deployment, document, or approval packet;
- the validation available at each increment, including manual, automated, operational, migration, or performance evidence;
- rollout, compatibility, sequencing, or safety constraints that prevent a thin integrated path;
- whether the work is primarily product delivery, a capability or API, an experiment, infrastructure, a migration, maintenance, or one bounded result.

Investigate these facts before asking the user. Ask only where intent, risk tolerance, review preference, or another human choice materially changes the decomposition.

## Decide the independent axes

Present a recommended strategy and viable alternatives when the choice is material. Settle these axes without turning them into a fixed taxonomy:

1. **Increment shape:** the coherent outcome produced by each increment. Examples include a vertical user journey, an API or CLI capability, an operable infrastructure checkpoint, an evidence-producing experiment, a reversible migration stage, a maintenance item, or one bounded delivery.
2. **Review unit:** what reviewers evaluate together. An increment may equal one pull request or may require a short sequence of reviewable changes; make that relationship explicit.
3. **Validation surface:** the highest meaningful boundary exercised at increment completion, such as browser to persistence, public interface to backing behavior, deployment to health evidence, or hypothesis to benchmark result.
4. **Integration rule:** what must remain coherent and working after every increment, including feature-flag, compatibility, rollout, and incomplete-state behavior.
5. **Enabling-work policy:** which foundations may precede an observable increment and what makes each one independently valuable, necessary, bounded, and verifiable.

Treat release readiness as separate from increment completion. An internally demoable or reviewable increment does not imply that it is safe for customer or production release.

## Use context-sensitive recommendations

- For an interactive feature spanning UI and backend layers, recommend the thinnest coherent path from the user surface through its real backing behavior. Prefer adding depth or breadth in later increments over building every backend layer before exposing any integrated UI.
- For an API, CLI, library, or automation, slice from its public interface through the behavior or artifact that proves the capability works.
- For infrastructure and data migrations, prefer operable or reversible checkpoints with production-shaped verification and explicit compatibility boundaries.
- For a POC or spike, organize increments around questions answered, risks retired, and durable evidence rather than simulated product completeness.
- For a small or personal project, allow one bounded implementation when additional phases or review units would add ceremony without useful feedback.
- For maintenance and support, preserve the interrupt-driven queue; decide delivery strategy per item only when its integration or review path is non-obvious.

These are recommendations, not automatic choices. Follow the user's explicit strategy after surfacing material tradeoffs and infeasible or unsafe implications.

## Record a durable choice

When the strategy materially governs multiple tasks or future sessions, record it through [the decision workflow](record-decision.md). Capture the chosen axes, rationale, affected plan area, and any explicit exceptions. Do not duplicate the full decision in discovery and the plan; link the decision and summarize only the operational fields needed to use it.

When the choice affects only one small focus and is unlikely to matter after the current session, keep it in the conversation or task scope rather than creating unnecessary project structure.

## Audit the proposed decomposition

Before presenting or approving detailed tasks, verify:

- Every increment has an observable outcome or independent evidence boundary.
- The named validation exercises that outcome at the promised boundary.
- Reviewers can evaluate the increment without mentally assembling a much larger unfinished change.
- The repository, product, system, or artifact remains coherent after the increment.
- Integration is not deferred to the final task merely because files are organized by layer.
- Layer-specific tasks are either part of a near-term integrated increment or qualify under the enabling-work policy.
- Pull-request or review boundaries match the chosen review unit instead of being inferred from task count.
- Feature flags and scaffolding do not substitute for an exercised path; identify what is actually runnable or testable.

If the decomposition contradicts the recorded strategy, revise the decomposition or obtain an explicit exception. Do not silently reinterpret the strategy or describe a layer-first sequence as vertical because its final phase eventually connects the layers.
