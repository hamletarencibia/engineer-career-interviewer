# Adaptive question bank

Select only useful prompts; do not ask every question or follow this ordering rigidly. This skill is **software-engineer-focused**: use [engineering-lenses.md](engineering-lenses.md) for relevant frontend, backend, infrastructure, AI, maintenance, data, game/mobile, and cross-cutting technical probes. Avoid trivia or unsupported specialization assumptions.

## 1. Timeline and professional identity

- Walk me through roles, dates, titles, employment types, countries/time zones if relevant, and overlapping work.
- Which employer transitions were promotions, title changes, contracting changes, or actual new positions?
- What types of problems, products, industries, customers, and colleagues characterized each role?
- Which freelance, entrepreneurial, volunteer, or open-source work deserves inclusion? Was it paid, shipped, maintained?
- Which items on an imported resume/profile are inaccurate, outdated, or not yours?

## 2. Each experience: responsibilities and boundaries

- What did a normal week look like? What did you own versus support?
- Which systems or processes did you personally design, code, test, deploy, review, maintain, or operate? Which stages were handled by others?
- Who defined requirements, designed architecture, reviewed work, made final decisions?
- Which work belonged to teammates or an external platform rather than you?
- Were there responsibilities people might overlook because they felt routine?

## 3. Project discovery and hierarchy

- What were the 2–5 most substantial initiatives in this role? Which are small features within the same larger initiative?
- Who needed this work? What was the original problem and what existed before?
- What was proposed, prototyped, deployed, adopted, maintained, rolled back or retired? Was it ever in production?
- Which subsystem shows a distinct capability worth its own optional subproject?
- Is any project too confidential to name? What generalized description is shareable?

## 4. Architecture and technology

- Sketch the main components and data flow in plain language.
- Which languages/frameworks/infrastructure services did you actually use and to what degree?
- Which decisions did you propose, influence, implement, or inherit?
- What alternatives did you consider? Why choose one? What constraints shaped the trade-off?
- What would break at higher load? What failure modes, retries, timeouts, observability and data consistency were relevant?
- What did you learn from real implementation, debugging or maintenance that a tutorial would not have shown you?

## 5. Failure, incident, trade-off, and lessons

- What approach failed or was abandoned? Why? What signal showed it wasn't working?
- Was there a production incident or hard bug? What was your diagnostic and remediation role?
- What shortcuts or technical debt did you consciously accept, and why?
- Did the chosen architecture cause unexpected costs or complexity?
- With what you know now, would you make the same choice? What would you do differently?
- Was a negative outcome a useful learning experience even if no metric improved?

## 6. Outcomes and evidence

- What concretely changed after the work shipped? How do you know?
- Who used it, at what approximate scale (users, tenants, requests, teams, products)? Is that your estimate or recorded evidence?
- Is there a before/after comparison, adoption, incident reduction, development speed, customer feedback or revenue effect?
- Could external conditions or teammates explain some of the result? How much can you fairly attribute to your contribution?
- Are exact figures unavailable or confidential? Can the project still be described honestly without them?

## 7. Skills and proficiency evidence

- Which technologies have you used in production, on personal projects, only studied, or used years ago?
- For each significant skill: first/latest use, usage context, responsibility level, concrete EXP/PROJ/ACH evidence.
- Would you feel comfortable using it again today, or would you need a refresher?
- What important capabilities are missing from a tools-only list (architecture, integrations, diagnosis, customer communication)?

## 8. Leadership and collaboration

- Did you mentor, review code/work, coordinate tasks, drive decisions, or interview candidates?
- How many people and for how long? Were they direct reports or peers you guided?
- Give one concrete technical/organizational decision where you had meaningful influence.
- How did you collaborate with design, product, executives, support or customers?
- Did your role change over time without a formal title change?

## 9. Education, credentials, language, preferences

- Formal education, dates, fields, degrees completed/not completed; relevant courses and certifications (with expiry where applicable).
- Professional languages and confidence in work settings.
- Preferred types of roles, work arrangements and geographic constraints (optional, mutable; not presented as permanent experience facts).
- Any private/confidential details to exclude or generalize from externally shared resumes?

## 10. Overlooked engineering work

- Which difficult maintenance or debugging problem did you solve that no one treated as a formal project?
- Did you make critical small changes, preserve backward compatibility, reduce support burden, or prevent regressions?
- Did you introduce tests, better logs, documentation, reusable libraries, developer tooling, or release processes?
- Which incident or failed experiment taught you the most, even if there was no measurable win?
- Did you maintain something you did not originally build? What responsibility and judgment did that require?

## 11. Cross-check and close

- What is the most important thing about your contribution that we have not asked?
- Are any descriptions too strong, too weak, or misleading?
- What remains unknown because you can't recall, rather than because we haven't asked?
- Which project would you most like to unpack later? Would you prefer to stop or continue?

## Example targeted pivot

User: "I implemented a shared UI library used by different products."

Useful immediate probes: "What was your personal role in designing and maintaining it?" + "Which products adopted it?". If it served several production apps, offer optional depth on API stability, package distribution, adoption, design tokens, accessibility, and collaboration. Do **not** assume it was a company-wide design system or that speed improved.
