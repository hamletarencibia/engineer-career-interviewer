# Depth, pace, and session controls

## Independent settings

**Depth** sets expected breadth and investigation quality, not a hard number of questions:

| Depth | Typical budget | Required behavior | Escalation |
|---|---|---|---|
| Quick | ~15–25 core questions total | Timeline, recent/important roles, key skills, a few impactful accomplishments, basic attribution, obvious accuracy gaps. | Ask permission for deep projects; note remaining gaps. |
| Standard (default) | ~40–80 questions over multiple sessions | Map complete timeline and meaningful projects; establish responsibilities, personal contributions, technology evidence, selected outcomes, leadership and constraints. Pursue noteworthy signals. | Ask before converting one topic into an extended technical investigation. |
| Deep Dive | As many as yield useful evidence | Detailed project/subproject decisions, abandoned alternatives, failure modes, debugging, constraints, incident postmortems, operations, metrics, technical and organizational trade-offs, lessons and future choices. | Even here, ask before opening a distinct large subtopic, especially if the user has not prioritized it. |

Budgets are indicative, **never quotas**. A ten-year career cannot be made complete by a prescribed question count. The skill supports mixed depth: e.g. Standard career-wide, Deep Dive on EXP-002 and PROJ-007.

Engineering routing: at any depth, discover the developer's actual project/role first, then consult the matching [engineering lenses](engineering-lenses.md). In **Quick**, usually ask only common anchors. In **Standard**, investigate one meaningful production challenge or decision for significant projects. In **Deep Dive**, explore relevant failed approaches, trade-offs, debugging, operations and retrospective without turning it into a trivia interview. Don't escalate without permission, and don't force unapplicable questions.

**Pace** changes packaging, not standards:

- **Rapid Fire (default):** Ask ~5–8 clearly numbered, tightly related questions at a time when answers can be short. If a complex answer needs investigation, switch temporarily to 1–3 focused follow-ups. Accept numbered answers, freeform, or partial responses. Do not send five multipart questions that amount to 30 demands.
- **Conversational:** Ask one or two focused questions at a time; respond to details and follow naturally. Avoid praise and restating every answer. Use compact transitions.

## Good opening example

"I'll build a factual career knowledge base, not a resume. I'll start in Standard + Rapid Fire mode (change either any time). To map your career: (1) current/previous employers and approximate dates, (2) titles or types of work, (3) major independent/freelance work, (4) strongest technical domains, (5) any existing resume/profile to import? Short or partial answers are fine."

If some of these facts are already known from an attached file, **do not ask them again**. Instead ask the most relevant missing questions.

## In-session controls

- `quick`, `standard`, `deep dive`: change global depth, or apply to one EXP / PROJ.
- `rapid fire`, `conversational`: change pacing immediately.
- `continue`, `next`, `skip`, `don't remember`, `not applicable`, `stop`, `export`: respect immediately.
- `go deeper into PROJ-003` / `review gaps` / `correct EXP-002` / `update my current role`: continue without restarting.
- `not now`: mark postponed; only re-propose if context materially changes or user requests.

## Checkpoint behavior

- After timeline and after each substantial experience/project: update file if possible, otherwise maintain/export a complete draft at user request.
- On stop or interrupted session: checkpoint current topic, settings, answered/unknown/declined questions, and suggested next topic under Interview State; inform user how to resume.
- On resume: inspect interview state and file first; don't restart onboarding. Revalidate time-sensitive fields before representing them as current.
- Avoid claiming autosave when file access is unavailable.
