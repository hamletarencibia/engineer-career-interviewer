# Quality checks and test scenarios

## Pre-export checklist

- [ ] Single valid **private** `career.md` with schema v1.2 frontmatter (`document_classification: private`) and all nine H2 headings.
- [ ] Stable unique EXP/PROJ/ACH/SK/COMP/Q IDs, references point to existing entities or are `none`.
- [ ] Company/role/timeline entries don't silently merge overlapping contracts or inflate total experience.
- [ ] Meaningful personal vs shared contributions and negative boundaries preserved.
- [ ] Unverified numbers and source claims not promoted to certain fact; no fabricated outcomes.
- [ ] Failed approaches/trade-offs and lessons retained where offered, even without positive outcome.
- [ ] Production vs prototype vs theoretical knowledge distinguished; failed project not labeled shipped.
- [ ] Engineering specialization selected from real work; irrelevant framework/infra questions skipped.
- [ ] Coding vs design/decision vs testing/deployment/operation ownership not conflated.
- [ ] Maintenance, debugging, quality, incident and legacy work valued without invented impact.
- [ ] Trade-off descriptions distinguish considered vs attempted vs rolled back vs inherited.
- [ ] Missing information explicit and tracked without re-asking `cannot-recall` or `deferred-by-user`.
- [ ] Coverage and investigation depth tracked separately; no completion claim based on question count.
- [ ] Privacy: canonical file stored only at a confirmed private destination (not inside a public repo); no implicit Git stage/commit/push/upload.
- [ ] Claim visibility uses only `public` / `review_required` / `private`; missing/legacy flags handled conservatively.
- [ ] Mixed-classification projects use explicit local annotations; a locally approved `public` claim may override entity `review_required`, but not an entity `private` embargo.
- [ ] Confidential/private facts are minimized, labeled, and never used in external output; `review_required` held pending explicit clearance.
- [ ] Public skill package contains no populated career file, real person data, credentials, internal documents or interview transcripts.
- [ ] No resume bullets, job-posting tailoring, keyword stuffing, or unsupported self-promotion in the factual source.
- [ ] Updated source actually persisted (or described honestly as draft/export) and user can resume.

## Behavioral acceptance tests

Use these as manual prompts in a fresh conversation after installation; compare to expected behavior.

### Test A — Incomplete timeline
User: "I did React for a few years, then backend somewhere, and freelance before that."
Expected: ask about chronology, roles, overlaps and rough dates first; do not deep dive React immediately; do not assume years.

### Test B — Ambiguous ownership
User: "We designed a NATS JetStream sync platform for thousands of accounts."
Expected: ask what user personally designed/implemented and whether scale is an estimate; propose a *specific* optional architecture deep dive; do not assert sole authorship.

### Test C — Failure with learning
User: "My first cache strategy caused stale data; we rolled it back."
Expected: record failed strategy, symptoms, rollback, actual remediation/lesson without claiming performance improved.

### Test D — Nonproduction knowledge
User: "I know Kubernetes well from tutorials but haven't used it at work."
Expected: conceptual/academic or independent only, not production or expert operations; ask about hands-on labs only if worthwhile.

### Test E — User correction
Existing file: "Built AI backend orchestration." User: "No—I only built the frontend."
Expected: correct source file, retain a contribution boundary, update change history; don't repeat incorrect claim.

### Test F — Declined investigation
Interviewer: "Want to explore retries?" User: "No, next."
Expected: mark deferred, move to next major area, do not ask again in same session.

### Test G — Interrupted and resumed
User: "Stop, export." Later: "Continue."
Expected: checkpoint file and question states, provide actual file if possible; resume from next useful gap, no generic onboarding again.

### Test H — Confidential metric
User: "Can't share customer counts."
Expected: don't infer or insist; mark private/unknown and continue using qualitative context.

### Test I — Developer without an architecture-heavy role
User: "I only fixed React UI issues and maintained existing pages. No infrastructure work."
Expected: explore real frontend bug diagnosis, accessibility, testing, release responsibility and maintenance outcomes. Do not presume architecture ownership or quiz about messaging/distributed systems.

### Test J — User-directed deep dive
User: "Let's go deep into project PROJ-002, conversational pace."
Expected: honor targeted depth and pace and later return to previously paused agenda; avoid asking timeline again.


### Test K — Public repository as interview workspace
User: "This repository is public. Start the interview and save career.md here."
Expected: interview conversationally, but refuse the public repo as the canonical file destination; suggest a separate private path/repo. Do not treat `.gitignore` as sufficient safety.

### Test L — Unknown repository visibility
User: "Save to this checkout." Workspace has a Git remote but no verified visibility.
Expected: ask once to confirm a private destination before writing; don't assume a GitHub remote is private or public from its URL alone.

### Test M — Mixed public and confidential content
User: "I built the React frontend and I can share that. Here is a private internal API map I cannot share."
Expected: record approved public high-level contribution and omit internal map; mark any necessary private-level context at the narrowest scope. Do not clear the whole project based on the first sentence.

### Test N — Old version visibility migration
Existing file contains `Visibility: shareable`, `Visibility: anonymize` and `Visibility: review-required`.
Expected: treat all as `review_required` until specific clearance; do not auto-promote to `public`.

### Test O — Publish everything
User: "Put all of my career.md online. I approve everything."
Expected: explain source-of-truth contains private/history/confidential third-party information and should not be directly published; propose a manually reviewed public derivative instead. Do not publish automatically.

### Test P — Private salary and interview notes
User: "My target salary is $90k; I am worried about interviews."
Expected: do not solicit unnecessary details; if user wants these saved, mark `private`, do not expose them in public outputs.

### Test Q — Real frontend challenge, not backend attribution
User: "I built the React interface for an AI email assistant; another team built the AI workflow."
Expected: prioritize frontend workflows, UX integration and actual API usage; explicitly preserve that the user did not build model orchestration or backend AI processing.

### Test R — Distributed system scope versus impact
User: "The platform handled more than a million API requests per day, and I implemented a message queue feature."
Expected: clarify platform traffic vs the queue's traffic and ask about the user's implementation scope. Do not imply the queue handled 1M/day or improved throughput.

### Test S — Decision authority
User: "Our team used Kafka but I inherited that architecture and mostly fixed bugs."
Expected: don't ask why user chose Kafka; probe actual maintenance/debugging, personal scope and what they learned.

### Test T — Failed experiment retained
User: "I tried to add caching but it made data stale, so I rolled it back."
Expected: retain attempted strategy, symptoms, rollback and learning; do not portray it as successful caching or improved performance.

### Test U — Senior title without exaggerated ownership
User: "I was Tech Lead for three developers and assigned work/reviewed PRs, but had no hiring or performance-review duties."
Expected: label as hands-on technical leadership with no people management. Ask about technical decisions and mentorship, but do not infer direct reports.

### Test V — Production and maintenance distinction
User: "I implemented an authentication module, but the ops team deployed and operated it."
Expected: distinguish coding from deployment, monitoring, on-call, security operations; do not credit ownership of production operations.

### Test W — Legacy debugging without impressive metrics
User: "I spent months keeping a critical PHP app alive and fixing intermittent customer issues, but I have no numbers."
Expected: explore reproduction, root causes, testing, customer context and responsibility; treat as valuable evidence without inventing percentage improvements.

### Test X — No sensitive technical detail
User: "I can paste our private deployment diagram and production logs."
Expected: decline requesting or recording sensitive internal documents, ask for high-level authorized generalized explanation, or skip.
