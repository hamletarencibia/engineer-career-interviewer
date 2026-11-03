# Career Interviewer — Agent Skill v1.2

A portable, instruction-only [Agent Skill](https://agentskills.io/) for **software developers and engineers** to build and maintain a single factual `career.md` source of truth through adaptive interviews. It covers shipped systems, maintenance, technical judgment, production reality and failed approaches—not just shiny projects and technology keywords.

## What's included

- `SKILL.md`: agent trigger and end-to-end workflow.
- `references/interview-methodology.md`: adaptive follow-up and stopping decisions.
- `references/depth-and-pacing.md`: Quick / Standard / Deep Dive and Rapid Fire / Conversational modes.
- `references/question-bank.md`: targeted prompts, not a mandatory questionnaire.
- `references/engineering-lenses.md`: discipline-specific routes for frontend, backend, distributed systems, data/search, infrastructure, AI integrations, game/mobile and cross-cutting work.
- `references/career-schema.md`: canonical single-file data contract and ID rules.
- `references/accuracy-and-evidence.md`: verification, collaboration, metrics, correction.
- `references/privacy-and-publication.md`: mandatory data minimization, private storage checks, claim visibility and public-release rules.
- `references/quality-checks.md`: acceptance tests and export checklist.
- `assets/career-template.md`: empty career file template; never a populated user profile.
- `.gitignore`: defense-in-depth ignore rules for a public repo **when located at the repo root**.
- `agents/openai.yaml`: optional ChatGPT/Codex display metadata.

## Install

Place the **entire `career-interviewer` folder** in the agent's skills directory, preserving `SKILL.md` and its relative `references/` and `assets/` paths. For Codex, use a project-level `.agents/skills/career-interviewer/` or user-level `~/.agents/skills/career-interviewer/`. Restart the agent if the new skill isn't discovered. In ChatGPT products that accept standalone skills, follow your client's local skill installation flow.

The zip is a portable skill package; it is **not** automatically installed by downloading it.

## Privacy: public skill, private career data

**Safe to publish:** This skill package contains only reusable instructions and an empty template. The generated **`career.md` is a private source of truth**, not a shareable resume. Keep it in a separate **private** Git repo or outside a public workspace even if some career statements are marked `public`.

The included `.gitignore` helps when placed in the **root of your public repository**; if the skill lives in `.agents/skills/career-interviewer/` it cannot ignore `career.md` in the parent repository. Put equivalent rules in the actual repository root. Never rely on `.gitignore` alone: tracked files, force-adds and Git history can still expose data.

Claim labels: `public` (explicitly approved statement), `review_required` (default / potentially confidential), `private` (never use in public output). The Resume Builder should use only approved `public` facts. Detailed internal architecture, third-party confidentiality, compensation and personal notes must not slip into public exports. Anonymizing a statement does not automatically approve it for publication. See [privacy-and-publication.md](references/privacy-and-publication.md).

**Before pushing a public repo:** review `git status --short`, `git ls-files` and the staged diff (`git diff --cached`); confirm no populated career record, private notes, secrets, or internal employer details are tracked. If sensitive data was committed before, deleting the file in a later commit does not erase Git history or existing copies. The skill never commits or pushes without a separate explicit request.

## Try it

- `Use career-interviewer to start building my career.md. Standard depth, rapid-fire questions.`
- `Continue my career interview from the attached career.md.`
- `Deep dive into PROJ-003, conversational pace. Focus on technical decisions and failed approaches.`
- `Check my career.md for unverified claims and gaps.`
- `Correct EXP-002: I only implemented the frontend, not the backend; preserve that limit.`

The skill only documents career facts. A future, separate Resume Builder can consume `career.md` read-only to tailor applications.

### From v1.1

Version 1.2 is additive: it preserves one Markdown file, existing identifiers, depth/pace controls and public/private safeguards. It adds **selective engineering-domain questioning**, stronger distinctions between code/design/operations ownership, and structured optional documentation for production lifecycle and engineering decisions. Existing `career.md` files can be updated in place to schema v1.2; the interviewer must not invent information for new optional fields.

## Testing

Use the behavior scenarios in `references/quality-checks.md`. No scripts or external dependencies are required by v1.2.
