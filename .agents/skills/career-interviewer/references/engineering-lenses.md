# Software-engineering discovery lenses (v1.2)

## Purpose and activation

This skill primarily interviews **software developers and software engineers** (including specialists, technical leads, self-taught developers, freelancers, and people whose job title did not say "engineer"). Use these lenses to discover **demonstrated engineering work**, not to administer a technical exam.

1. First map career chronology, projects and the user's own contributions. Infer candidate lenses from concrete work; if uncertain, ask what kind of work they actually did rather than assigning a specialization based on title.
2. For each meaningful project select **one primary lens**, with at most one or two secondary lenses that are supported by the user's answers. Projects can span disciplines; one lens is not a label of the user's identity.
3. Ask the **common anchor questions** first, then pick 1–3 unanswered, high-value prompts from the relevant lenses. Expand only if the user is interested and the expected additional evidence justifies effort.
4. In Standard mode, concentrate on personal implementation, production reality, a significant decision/constraint and outcome. In Deep Dive, explore the actual failures/trade-offs and what they would change now. Quick should not expand into lens checklists.
5. **Do not assume** a mentioned technology implies operation, ownership, expertise, a choice of architecture, security responsibility, or a successful outcome. Avoid asking 'why did you choose X' before confirming that the user had a say in choosing X.
6. Preserve answers as factual project/achievement/skill information under the existing schema. These lenses **do not** create mandatory fields or separate files.

## Common anchors (for nearly any engineering project)

- **Problem & lifecycle:** What problem did this solve? Was it a proposal, prototype, production feature, internal tool, migration, ongoing maintenance, or abandoned effort?
- **Hands-on footprint:** What did you personally design, code, integrate, test, review, deploy, support, or maintain? What was done by teammates or a provider?
- **Technical shape & constraints:** What are the essential components and interfaces **at a safe, nonconfidential level**? Which requirements/constraints mattered, and who controlled them?
- **Hard part:** What was the most difficult real problem you solved, rejected approach, debugging episode or trade-off? How did you diagnose or decide?
- **Result & evidence:** What shipped or changed? What evidence supports it? Distinguish total system scale from attributable improvement.
- **Retrospective:** What would you keep or do differently now? Don't require a positive resolution for the story to be valuable.

## Primary technical lenses — choose, don't exhaust

### Frontend, UI and web applications

**Signals:** React/Vue/Angular, components, design systems, browsers, accessibility, SEO, UX flows, client state.

- What user workflow or product surface did you implement, and which portions were yours (UI, API contract, backend behavior)?
- What were the hardest state-management, rendering, responsive, caching, cross-browser, accessibility or interaction problems you actually encountered?
- If performance was relevant, what measurement or symptom drove the change (e.g. Web Vitals, render cost, bundle size)? Was improvement measured or only observed?
- Did you build/reuse a component library? Who defined its API, adoption, versioning and design rules? How many teams/products used it, if known?
- What did you test (unit, integration, E2E, manual), and what gaps or compromises remained?

### Backend services, APIs and integrations

**Signals:** API endpoints, business logic, third-party services, jobs, authentication, rate limits.

- Which endpoints, services, background workers or integration contracts did you implement versus merely consume?
- How did you handle validation, errors, pagination, authentication, rate limits, retries or versioning **if these were part of your work**?
- Did you choose the data model or service boundary, or implement an existing design?
- What was difficult about integrating with an external system (unreliable APIs, changing contracts, partial failures)?
- What observable result followed delivery, and what was someone else's responsibility?

### Distributed systems, messaging and concurrency

**Signals:** queues, brokers, fan-out workers, event-driven processing, multi-tenancy, synchronization, high request volume.

- At a conceptual level, how did work/data flow among services? Which components did you personally design and implement?
- What delivery semantics, ordering, duplication, idempotency, concurrency or consistency concerns **actually arose**?
- Did a real failure occur? What evidence pointed to the cause, and what did you do about it?
- Why were a queue, broker or worker arrangement selected—**only if you participated in that decision**? What alternatives were tested or considered?
- Was the quoted number scale of the whole platform, of this component, or an improvement directly attributable to your change?

### Data, storage and search

**Signals:** database schemas, query optimization, indexing, ETL, search, semantic retrieval, migrations, reporting.

- Which data structures, queries, schemas, indexes or retrieval logic did you implement, and at what scale (if known)?
- Did you own migrations, backups or data correctness, or did another team?
- What latency, consistency, accuracy, cost or correctness trade-offs surfaced? How were they measured or diagnosed?
- If ML/semantic search was involved, which parts were yours: ingestion, embeddings, retrieval, evaluation, ranking, interface, or orchestration?

### Platform, cloud, operations, reliability and security

**Signals:** deployments, CI/CD, infrastructure as code, containers, monitoring, incident response, cloud cost, authentication/security.

- What did you personally provision, deploy, monitor, maintain or troubleshoot, versus what the platform/ops team managed?
- How were releases, rollbacks and recovery handled **in your scope**? Did you participate in on-call or incident response?
- Which reliability/security requirements affected your work? Do not ask for sensitive topology, credentials, internal endpoints, vulnerability details, or unapproved incident reports.
- Did you change cost, uptime, observability, test automation or developer workflow? What evidence supports the outcome?

### AI-assisted software and machine learning integrations

**Signals:** LLM features, chatbots, AI email assistants, RAG, embeddings, prompt workflows, model evaluations.

- Which layers did you work on: user interface, API integration, retrieval, prompts, model selection, orchestration, evaluation, deployment?
- Did you build the AI processing pipeline, consume an existing AI endpoint, or collaborate with another team? **Make the boundary explicit.**
- Which latency, failure, quality, grounding, cost or privacy issues did you personally address?
- Was the system evaluated or deployed? If it worked in a demo only, record that honestly.

### Mobile, desktop, embedded and game development

**Signals:** mobile applications, native apps, desktop clients, device constraints, gameplay/network loops, asset pipelines.

- What platforms and runtime constraints shaped your implementation (device performance, offline, input, networking, distribution)?
- Which systems did you implement (UI, engine/gameplay, state, persistence, networking, integration), and which were supplied by a framework or collaborators?
- How did you test across target environments and validate real user or production outcomes?

## Cross-cutting lenses — apply selectively

### Legacy maintenance, debugging and migrations

**Strong positive signal** even when there is no greenfield project or numeric metric.

- What inherited code or behavior was difficult to understand, stabilize or change? Which parts did you own?
- How did you isolate the failure or risk (logs, reproduction, profiling, tests, source tracing) **without recording confidential details**?
- What migration, refactor, rollback, compatibility change or stabilization did you carry out? What did you deliberately leave unchanged, and why?
- Was the work successful, partially successful, rolled back, or still uncertain?

### Testing, quality and developer experience

- Did you establish test coverage, release checks, tooling, documentation or coding conventions? What exactly was your contribution?
- Did other engineers adopt the change? Was adoption voluntary, required or only proposed?
- Did it reduce defects/effort, or is the benefit a reasonable expectation without measurement? Keep that distinction.

### Technical leadership and collaboration

- Did you mentor, review, coordinate, design, approve or manage? Separate hands-on technical leadership from hiring/performance management and direct reports.
- Who actually made final decisions? Did the user propose, influence, implement or own the outcome?
- Was there a disagreement, trade-off or cross-functional constraint? How was it resolved and what was learned?
- Did responsibility evolve over time even without a title change?

## Small engineering decision record (optional within `#### Alternatives, failed approaches and trade-offs`)

When a substantive decision or failure is discussed, capture a compact prose/bullet record (do **not** create a new entity or ask every item if not relevant):

- **Decision/problem:** What had to be decided or fixed?
- **Constraints & alternatives:** Actual constraints, options considered, attempted, rejected, or inherited (distinguish each).
- **Role:** Who decided? What did the user personally contribute?
- **What happened:** Result, including failure, rollback, partial success, uncertainty, or later cost.
- **Reasoning/lesson:** Evidence and what they would now do differently, if known.
- **Visibility:** Default `review_required`; generalize or omit employer-confidential specifics.

## What to avoid

- Do not conduct algorithm trivia, syntax quizzes, hypothetical system-design tests, or ask the user to prove seniority. This is **experience discovery**, not a technical assessment.
- Do not equate using a framework with designing the architecture, production code with release ownership, or a product's scale with the individual's impact.
- Do not over-focus on glamorous architecture: maintenance, bug fixing, accessibility, tests, integrations, incident recovery, and shipping small reliable changes can be strong evidence.
- Do not ask for private repositories, proprietary source code, logs, API keys, customer data or undisclosed internal diagrams. Record a generalized explanation, or skip if sensitive.
- Do not require the user to remember numerical baselines. Accept qualitative observations and unknowns.
