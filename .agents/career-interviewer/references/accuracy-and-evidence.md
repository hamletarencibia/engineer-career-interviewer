# Evidence, attribution, conflict resolution, and privacy

## Safe extraction protocol

- Store only what the user actually says or what an authorized source explicitly states. You may paraphrase for clarity, but not increase scope or certainty.
- Keep useful raw nuance. E.g. "helped the CTO brainstorm architecture, then built large parts of the system" must not become "solely architected".
- Source files (resumes, social profiles, earlier drafts) may contain errors. Imported assertions are `unconfirmed` until user reviews them; a user's current explicit correction takes precedence.
- A user-reported statement can be `user-confirmed` without external documents. It is an assertion of professional experience, not third-party verification.
- A hypothesis such as "maybe they designed retries" must only appear in Interview State as a proposed question, not in project facts.

## Personal vs team work

When an answer uses "we", ask one neutral question: "Which parts were yours versus shared or handled by teammates?" Do not demand exact task-level ownership on every line if already clear. Explicit boundaries outrank generic statements.

For technical work distinguish **proposed**, **co-designed**, **implemented**, **reviewed**, **operated**, **maintained**, and **observed**. For leadership distinguish **mentored/reviewed/assigned technical work**, **tech lead**, and **formal manager with direct reports**. Titles alone do not establish scope.

## Quantification

- Separate **scale** ("system processes 1M requests/day") from **impact** ("I reduced latency by 30%"). The first does not imply the second.
- If the user estimates, retain "approximately", range, unit, and uncertainty. Do not reverse-calculate a more precise figure.
- "Faster" or "more reliable" requires evidence or qualifying user observation; don't invent before/after baselines.
- If a result was team-wide or causality uncertain, say so. If user can't recall a number, mark `cannot-recall` once and move on.
- Never imply a system, architecture, or rollout succeeded if the user describes only a proposal, experiment, failed attempt, or unshipped work.

## Conflicts and changing facts

On contradictions: cite previously stored wording and the new answer briefly, ask a single clarifying question; until resolved mark affected claim `disputed`. On explicit correction, update the factual entry and (where relevant) downstream links, add a short dated Change History note. Do not create duplicate competing facts. Preserve a meaningful restriction if the correction prevents overclaiming.

## Privacy and shareability

**Follow [privacy-and-publication.md](privacy-and-publication.md) as the authoritative privacy and release policy.** The canonical `career.md` is private regardless of per-claim classifications. Do not solicit private code, credentials, customer records, personal IDs, unapproved metrics, or confidential organization details. Capture the general engineering lesson without privileged details.

Allowed claim visibility values are exactly `public`, `review_required` (default for missing/unclear labels), and `private`. Use per-paragraph restrictions if a project combines safe and internal facts; the most restrictive applicable classification wins. Only an explicitly approved claim or already public wording confirmed by the user may be marked `public`. Never convert anonymity into implicit permission, and never automatically publish any output.

## Honest uncertainty example

User: "I worked on the front end of an AI email feature; the other team owned the AI workflow."

Acceptable: "Implemented React frontend flows for an AI-assisted email feature; backend AI orchestration was handled by another team."

Not acceptable: "Designed and built an end-to-end AI email automation system."

The second wording violates contribution boundaries even if it sounds attractive on a resume.
