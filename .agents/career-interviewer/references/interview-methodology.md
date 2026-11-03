# Adaptive questioning method

## Objectives

Maximize **verified, distinctive and reusable career information per unit of user effort**. Build a faithful record of the person's actual contribution and understanding. Resist both naive checklists and aimless technical rabbit holes.

## Per-turn decision process

1. **Parse answer:** Extract factual assertions verbatim enough to retain nuance. Identify role/date, technology, project, contribution, decision, failure, consequence, evidence, estimate, explicit exclusions, privacy.
2. **Connect:** Link assertions to existing EXP/PROJ/ACH/SK/COMP. If no fit, create candidate entity or place in open questions. Record claims once, reference by ID elsewhere.
3. **Resolve high-stakes gaps first:** Especially ambiguous "we" vs "I", claimed outcome without basis, dates affecting seniority, imported-document conflicts, security/privacy issues.
4. **Identify signals:** Work at scale; migration; system design; incident recovery; difficult debugging; subtle UX; integration; team lead; mentorship; customer impact; unusual cross-functional work; failed approach; decision under constraints.
5. **Rank follow-up opportunities** qualitatively:
   - Critical: conflict, attribution, correctness, confidentiality, or necessary context.
   - High: missing distinctive evidence, major accomplishment/engineering decision, large unexplored role, career timeline gap.
   - Medium: relevant technical detail, outcomes, important pattern across roles.
   - Low: routine repeated details, theoretical trivia, weakly supported assumptions, marginal metric recall.
   For ties favor novelty, evidence gain, user interest and low effort.
6. **Check current depth:** Continue within mode, or propose a *specific optional deep dive*, with reason and return point. Never auto-escalate because something sounds impressive.
7. **Ask the smallest high-value set:** Match pace, group questions by project/theme. Prefer an open question followed by a precise probe; avoid leading phrasing such as "How much faster did you make it?" when improvement isn't established.
8. **Update and reconsider:** If answers become repetitive, vague despite attempts, unavailable, or the user wants a shift, stop; record coverage/depth and move on.

## Engineering-specific routing

For software developers, use [engineering-lenses.md](engineering-lenses.md) **after** establishing the actual project and contribution scope:

1. Identify primary domain from *work described*, not job title (e.g. frontend, backend, data/search, distributed systems, platform, AI integration, mobile/game).
2. Choose a small number of relevant lens probes. Cross-cutting maintenance, incident recovery, testing, and technical leadership are valuable in their own right.
3. Distinguish **lifecycle** (proposed, prototype, production, operated, retired/failed), **personal action** (designed, coded, tested, deployed, reviewed, operated), **decision authority** (proposed, co-decided, implemented another's choice), and **outcome evidence**.
4. Ask about a real technical decision or failed approach when the user actually encountered one; capture attempted vs considered vs inherited options.
5. Avoid exam-style prompts or assuming an engineer has worked on every aspect of their stack. Do not force a devops/security lens on frontend work, or AI orchestration on an AI feature's UI.

Only offer a **separate deeper branch** when it increases useful evidence and the user opts in. If no distinctive engineering challenge is known, ask for one example of a tricky debugging/maintenance task before switching projects.

## Follow-up ladder (not compulsory order)

- **Discover:** What was built, shipped, operated, changed or maintained? Why did the work exist? What is the timeline?
- **Attribute:** What did *you* personally do, vs contribute to, vs observe? What decisions were yours?
- **Explain:** Architecture/implementation; actual release/production responsibility if relevant; constraints; dependencies; concepts used in practice.
- **Evaluate:** Options rejected, failed attempts, trade-offs, operational consequences, incidents, lessons.
- **Validate impact:** Users, adoption, measurable evidence, qualitative outcome; estimated or unknown clearly marked.

Quick typically focuses on Discover + Attribute. Standard covers Explain and significant impact. Deep Dive pursues Evaluate in depth. Always ask accuracy-critical questions regardless of mode.

## Permission and scope control

Do not ask permission for an ordinary 1–2 clarifying follow-ups. Before broadening a Standard or Quick topic into a long investigation (e.g., a new subproject, architecture, deep incident analysis), explain value succinctly and ask:

"This may show useful reliability and systems-design experience. Want to dig into the retry/idempotency decisions, or move to the next project?"

If the user agrees, record scope and return when the subtopic reaches diminishing returns. If declined, mark `deferred_by_user`, do not repeatedly solicit it. If "just ask everything", accept explicit blanket permission until revoked, while still monitoring fatigue and relevance.

## Stop rules

Stop a branch when (a) critical fields for selected depth are covered, (b) last probes add nothing material, (c) user doesn't know, declines, or changes topic, (d) higher-value uncovered experiences need attention, or (e) it would expose confidential detail. "Not remembered" is a valid answer; mark it as such.

Do not confuse *technical sophistication of the topic* with *user's level of responsibility*. The ability to explain a technology is different from having shipped or operated it. Capture architectural trade-offs and failed approaches **without rewriting failures into claimed successes**.

## Conflicts and revisions

- If new answer conflicts with recorded facts, cite both in conversation and ask which should control; mark disputed until clarified.
- A direct user correction supersedes older claims; record a terse dated change note and retain important claim boundaries.
- Don't create new IDs for simple corrections, title updates, or expanded details; create a new EXP only when the actual role/titles or contracts differ, and a new PROJ only for independently meaningful work.
- If user states a future task or career plan, don't record it as an accomplishment.

## Cross-role synthesis

When roles share a skill, don't merely count repeated technology names. Probe whether responsibility progressed: implementation -> design -> mentoring -> ownership. Do not infer people-management from task delegation or a title. Avoid double-counting concurrent employment time when discussing experience duration.
