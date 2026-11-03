# `career.md` data contract — schema v1.2

**Purpose:** A single long-lived **private** human-readable Markdown source of truth. It is not a resume, autobiographical essay, or job-application-specific document. Other skills should be able to select relevant experience without changing source facts.

## Document and parsing rules

1. One `career.md`, UTF-8. Top YAML frontmatter contains `schema_version`, `last_updated`, `interview_status`, `document_classification: private`. Use ISO dates: `YYYY-MM-DD` for update stamps; `YYYY-MM` for known month/year; `YYYY` for year-only; `unknown` when unknown; `present` only for an ongoing position. Mark approximate dates explicitly (e.g. `Start date: ~2022-06`). Do not invent a day.
2. Canonical H2 sections **in this order**: `Professional Profile`, `Work Experience`, `Projects`, `Achievements`, `Skills and Competencies`, `Education and Additional Experience`, `Career Preferences`, `Interview State`, `Change History`.
3. Stable entity headings use `### EXP-001 — ...`, `### PROJ-001 — ...`, `### ACH-001 — ...`, `### SK-001 — ...`, `### COMP-001 — ...`, and `#### Q-001 — ...` (open questions nested under Interview State > Open Questions). IDs do not depend on ordering; never reuse deleted IDs or renumber when a new role is added. Assign next available monotonically increasing ID in that namespace.
4. Under an entity use short, parseable fields as `- Field: value`; free-text narratives under named `####` subheadings. Empty optional sections may be omitted, but explicit unknown/declined facts remain as such. Multiple references: comma-separated IDs, or `none`; don't use dangling references.
5. Prefer Markdown bullets and paragraphs over nested YAML/table structures. Add domain-specific fields sparingly; do not rename canonical fields unnecessarily.
6. For every material claim, preserve source/verification/precision/visibility context at the entity level, **and annotate more restrictive or differently sourced claims locally**. An unmarked claim defaults to `review_required`, not `public`. `career.md` remains private regardless of claim labels. Confirmation of a user-reported fact is not third-party verification.
7. Additive upgrades: a file using schema v1.1 can be read and updated to v1.2 without creating new files, renumbering IDs, or manufacturing missing engineering fields. Preserve existing privacy classifications and all user corrections. The new engineering footprint/lifecycle subsection is optional.
8. Do not make every role a project: experience stores job context/responsibilities; projects are meaningful bodies of work; achievements are reusable results or contributions; skills/competencies reference evidence.

## Frontmatter

```yaml
---
schema_version: "1.2"
last_updated: 2026-11-02
interview_status: in_progress # not_started | in_progress | paused | coverage_complete
document_classification: private # entire source-of-truth file; never publish
---
```

Date is illustrative; use the actual date at creation. `coverage_complete` does **not** imply all projects have Deep Dive depth.

## `## Professional Profile`

- `Visibility`: classify any profile statements separately; personal restrictions, salary and contact details are `private` unless specifically approved for external use. Avoid unnecessary personal identifiers.

- `Name` (optional; don't force personal identity or legal name)
- `Professional focus` (factual areas/roles, not marketing copy)
- `Career timeline summary` (high-level; no artificial total-years count)
- `Core domains` (e.g. frontend engineering, data operations, design)
- `Industry experience` (optional)
- `Professional languages` (or also under education; avoid duplicated details)

Never infer years of experience from title alone. Concurrent jobs, study, freelancing, and part-time work must be represented honestly.

## `## Work Experience`

One **EXP** for each materially distinct position/contract (title, responsibilities, employment relationship, or dates), even if employer is the same. If title changed but responsibilities did not, clarify before splitting. Roles can overlap; do not merge them.

```markdown
### EXP-001 — Northstar Systems | Software Engineer
- Employer: Northstar Systems
- Title: Software Engineer
- Employment type: contractor
- Start date: 2022-06
- End date: present
- Location / arrangement: remote
- Industry / product context: [user-reported context]
- Verification: user-confirmed
- Source: user-interview
- Visibility: review_required
- Linked projects: PROJ-001, PROJ-002
- Linked achievements: ACH-003

#### Role scope and responsibilities
[What the role actually involved; ownership and routine work.]

#### Leadership and collaboration
[Specific duties, people relationships; formal management only if established.]

#### Contribution boundaries
[Explicit not-built/not-owned/not-involved statements; or "none documented".]

#### Notes
[Constraints, organizational context, open caveats.]
```

Prefer direct/indirect project references; do not duplicate every project's story here. Independent work can be an EXP with employment type `freelance`/`self-employed`, and a PROJ can be standalone with `Experience links: none`.

## `## Projects`

A PROJ is a meaningful initiative, product, subsystem or sustained body of work. Hybrid granularity: large parent project plus child PROJ only when an independently meaningful subsystem warrants distinct evidence. A feature/ticket doesn't automatically qualify for its own PROJ.

```markdown
### PROJ-001 — Customer Synchronization System
- Experience links: EXP-001
- Parent project: none
- Child projects: PROJ-002
- Project type: professional
- Lifecycle / status: deployed-to-production
- Period: 2023–2024 (approximate)
- Technologies: TypeScript, Node.js, message broker
- Competency links: COMP-001
- Achievement links: ACH-001
- Verification: user-confirmed
- Source: user-interview
- Visibility: review_required

#### Context and initial problem
[Stakeholders, constraints, before-state.]

#### Solution and system description
[Architecture and what actually shipped; distinguish proposals/prototypes/production.]

#### Personal contributions
[Tasks personally performed, exact design vs implementation responsibilities.]

#### Collaborative contributions
[What was co-designed/co-implemented; who owned final decisions if known.]

#### Technical knowledge and reasoning
[Demonstrated engineering knowledge, real implementation details, data flow, constraints and invariants. Use appropriate domain-specific context (frontend, backend, infrastructure, data, AI, mobile/game, etc.); do not turn the record into a generic technology tutorial. See `engineering-lenses.md`.]

#### Engineering footprint and lifecycle (optional)
[Stage: proposed/prototype/production/maintained/rolled back/retired; what the user personally designed, coded, tested, deployed, reviewed and/or operated; release/maintenance ownership; legacy work. Do not infer unmentioned stages.]

#### Alternatives, failed approaches and trade-offs
[Describe actual decisions and failures, not hypothetical trivia. Preserve whether an alternative was **considered**, **attempted**, **rejected**, **inherited**, or **rolled back**. Include constraints, decision authority, observed consequence and learning where known. Do not create success narratives out of failures. Optional short decision records can live here; no extra ID namespace required.]

#### Challenges and incidents
[Real debugging, testing, reliability, migration, accessibility, releases, security/operational incidents, and maintenance challenges; the user's actual role. Treat these as substantive evidence even without a greenfield system or measured outcome. Never capture confidential logs or exploit details.]

#### Outcomes and supporting evidence
[Measured or qualitatively observed outcomes. Separate system scale from improvement caused by the user.]

#### Lessons and retrospective
[What the user learned; what they would change.]

#### Contribution boundaries
[Systems, decisions or backends not personally owned.]

#### Remaining questions
[References Q-IDs if useful.]
```

Dates/technologies/outcomes may be unknown. Only record justified facts. In particular **don't automatically invent** retry behavior, idempotency, throughput, revenue or design rationale simply because a message broker was used.

## `## Achievements`

ACH are independently reusable claims, improvements, deliveries, interventions, or important decision-making experiences. They may link to a PROJ and/or an EXP; one project can have multiple ACH and one achievement may relate to multiple experiences. **Not every ACH needs a numeric result.**

```markdown
### ACH-001 — Implemented distributed background work
- Experience links: EXP-001
- Project links: PROJ-001
- Tags: architecture, reliability
- Verification: user-confirmed
- Precision: qualitative
- Source: user-interview
- Visibility: review_required

#### Situation
[Problem or constraint.]
#### Personal contribution and collaborators
[Specific personally performed work; shared ownership and boundaries.]
#### Result
[What shipped or changed; no invented causality.]
#### Evidence and limitations
[User statement, document or measurement; unmeasured impacts explicitly marked.]
```

Distinguish *work delivered* from *outcome achieved*; a user can have an achievement in one without evidence of the other.

## `## Skills and Competencies`

### Technology entries (`SK-###`)

```markdown
### SK-001 — React
- Visibility: review_required
- Category: frontend framework
- First used: 2021 (user-reported)
- Last used: 2026 (user-reported)
- Usage: production-professional
- Current comfort: comfortable # comfortable | working-knowledge | refresher-needed | unknown
- Evidence links: EXP-002, PROJ-003
- Verification: user-confirmed

#### Demonstrated practice
[Exactly what user did with it; don't claim expert level on keyword alone.]
```

Allowed usage descriptions include `production-professional`, `professional-nonproduction`, `freelance`, `independent`, `academic`, `conceptual-only`, `historical`, and multiple where relevant. Don't equate last-used date with current proficiency. Don't manufacture a numeric skill score.

### Capability entries (`COMP-###`)

```markdown
### COMP-001 — Distributed background processing
- Visibility: review_required
- Category: architecture
- Evidence links: PROJ-001, ACH-001
- Verification: user-confirmed

#### Demonstrated practice and limits
[What the user can demonstrate and the boundaries of that demonstration.]
```

Other categories: technical leadership, stakeholder communication, debugging, integration, testing, reliability, accessibility, mentorship, operations, product strategy, etc.

## `## Education and Additional Experience`

Education: institution, program/degree, years, status (completed/in progress/not completed), verification. Certifications: issuer, issued/expiry, status. Professional languages: language, work-communication context, self-assessed level if volunteered; don't invent CEFR or native-speaker labels. Independent work belongs in EXP/PROJ if substantial; this section can link rather than duplicate. Publications and community contributions optional.

## `## Career Preferences`

- All personal preferences default to `private`; do not include in externally shared outputs.

Mutable personal preferences separate from facts: target roles, arrangements, geography/time zone, industries, salary objectives (optional, often sensitive), restrictions and exclusions. Mark `last confirmed` if known, avoid presenting time-bound preferences as eternal truths. A resume builder should not include private preferences in output by default.

## `## Interview State`

- Treat interview-state material and private doubts as `private`; never use the question log as public-facing copy.

```markdown
### Current session
- Depth: standard
- Pace: rapid-fire
- Current focus: EXP-001
- Next suggested focus: PROJ-002
- Last checkpoint: 2026-11-02

### Coverage
- Timeline: complete (quick)
- Work experience: partial (standard)
- Projects: partial (mixed)
- Skills: partial (quick)
- Leadership: not_started
- Education: not_started
- Preferences: optional_unasked

### Open Questions
#### Q-001 — Ownership of deployment
- Related IDs: PROJ-001
- Priority: high
- Status: not-asked # not-asked | asked-unanswered | cannot-recall | deferred-by-user | not-applicable | conflicted | resolved
- Question: Did you manage deployment yourself or did another team own it?
- Last asked: unknown

### Engineering lens progress (optional)
- PROJ-001: Primary lens: distributed systems; explored: implementation and message flow (standard); pending: actual failure modes (not asked); secondary lens: backend integration.

### Deferred Deep Dives
- PROJ-001: User declined reliability deep dive on 2026-11-02; revisit only on request or genuinely changed context.
```

Coverage dimensions: timeline, roles, major projects, outcomes, technical understanding, leadership, education, skills, preferences. Keep **coverage** (`not_started`, `partial`, `complete`, `not_applicable`) distinct from **depth** (`none`, `quick`, `standard`, `deep`). `complete` means adequately mapped at chosen scope, not omniscience. Questions from skipped/unknown responses must not be asked again automatically.

## `## Change History`

- Keep changes minimally descriptive, avoiding sensitive verbatim phrases and personal identifiers. This section is `private`.

Append concise entries only for meaningful source-of-truth modifications, e.g. `- 2026-11-02: Corrected EXP-002 title after user clarification; superseded imported resume wording.` Do not keep sensitive verbatim transcripts in change history.

## Claim metadata and privacy

Recommended fields (at project/achievement level and locally if mixed):

- `Verification`: `user-confirmed` (user explicitly said this), `document-supported` (source file asserts it), `unconfirmed` (imported or unclear; must review), `disputed` (conflicting sources). **Neither user-confirmed nor document-supported means independently verified.**
- `Source`: `user-interview`, `imported-resume`, `profile`, `supporting-document`, or similar; optionally file name/source note where available.
- `Precision`: `exact`, `approximate`, `qualitative`, `unknown` (especially for metrics and dates).
- `Visibility`: exactly `public`, `review_required`, or `private`. Use `review_required` when missing/unclear, including default employer-internal details. `public` requires the person to clear the exact wording for professional sharing or confirm that it is already public, but it never authorizes publishing files automatically. `private` is excluded from any public output. `Anonymize` is a proposed editing method, not a visibility value or release permission.
- `Contribution boundaries`: human-readable negative assertions; apply them as hard restrictions when summarizing the entity.

Read [privacy-and-publication.md](privacy-and-publication.md) for storage and export gates. For mixed visibility, annotate specific subheadings or statements with `- Visibility: public`, `- Visibility: review_required`, or `- Visibility: private` near the affected text. An entity-level label is the **default** for otherwise unlabeled claims; an explicitly user-approved local `public` label can override inherited `review_required` *for that particular statement*, but never an explicit entity-wide `private` embargo. If several explicit restrictions apply to the same claim, use the most restrictive one. If a statement cannot be partitioned safely, treat it as `review_required` or stricter.

Example for a mixed project (approved high-level claim, uncleared internal reasoning):

```markdown
### PROJ-004 — Internal platform
- Visibility: review_required

#### Publicly approved contribution
- Visibility: public
- Statement: Implemented frontend components for a production platform.

#### Internal technical decisions
- Visibility: review_required
- Notes: Generalized explanation of rejected approaches and trade-offs; no secrets.
```
 Legacy `shareable` and `anonymize` must become `review_required` and `review-required` becomes `review_required`, **not** automatically `public`.

Use the narrowest accurate scope for qualifiers: one verified date doesn't verify an entire project; one estimate doesn't make every outcome approximate. If no external evidence exists, preserve truthful user-reported experience with the correct source; do not demand proof from every user.

## Engineering-specific interpretation contract

- Distinguish **code written**, **architecture decided**, **production operated**, **release owned**, **code reviewed**, and **team led**; none is implied by the others. Record overlapping responsibilities without claiming sole ownership.
- For reported scale, explicitly distinguish **platform/company-level traffic**, the **component's scope**, and **the user's attributable result**. Do not turn existing scale into a claimed improvement.
- Treat debugging, long-term maintenance, integration hardening, test automation, accessibility and incident recovery as substantive evidence, even without "launched new platform" achievements.
- If a user worked on an AI-branded feature, record the actual layer built. Frontend interaction with an AI backend does not establish model/prompt/retrieval/orchestration implementation.
- For engineering trade-offs, preserve options **actually tried**, **only considered**, **inherited from others**, and **not chosen**, plus user decision authority. Do not fill empty fields with plausible technology details.
- Technical implementation or failure descriptions should remain privacy-safe and generalized. Do not request code, company diagrams, sensitive logs, unreleased metrics or vulnerability specifics; record only what the user is authorized to describe.

## Interoperability contract for future Resume Builder

- Read `career.md` as **read-only** unless asked to correct career facts.
- Select by evidence links and effective visibility. Only `public` facts can be used in an external resume by default; `review_required` needs specific approval; `private` is blocked. Missing labels block external use. Never treat unconfirmed/inferred claims as definite.
- Never promote conceptual/historical skill to production expertise, collaborative influence to sole ownership, team scope to direct management, scale metric to proven improvement, or planned work to delivered work.
- Preserve qualifying language for estimates, uncertainty, contribution boundaries, and confidentiality.
- Ask for clarification when an essential claim is contradictory or weakly sourced.
- Resume output is a separately reviewed derivative artifact, not a replacement for the knowledge base. Do not publish or send it without a separate explicit user instruction.
- This canonical file is `private` even if it contains only `public` claims. Keep it outside public Git repositories. Refer to [privacy-and-publication.md](privacy-and-publication.md).
