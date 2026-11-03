# Privacy, confidentiality, storage, and publication safeguards

**Required reference:** Follow this policy before requesting personal details, persisting `career.md`, exporting material, or using Git. This policy overrides convenience-oriented interview/export instructions. It applies regardless of interview depth, pace, or whether the person explicitly wants a public resume.

## Two different artifacts; two different boundaries

1. **The canonical `career.md` is private by design.** It may contain technical investigations, mistakes, career preferences, personal constraints and uncertain claims. Never intentionally commit, upload, push, post, or place it in a public repository. A public-facing resume or excerpt is a separately reviewed derivative, not the canonical file.
2. **The skill package may be public.** Ship only general instructions, empty templates and synthetic examples. Never include interview transcripts, user-filled `career.md`, personal profiles, secrets, employer-specific findings or locally generated resume files in a skill release.
3. **Visibility labels classify *individual claims*, not the file's repository visibility.** Even if every known claim is `public`, `career.md` itself remains private.

## Claim-level visibility: exactly three values

- **`public`:** Person explicitly approves the specific statement (or an adequately specific set of statements) for external professional use, or confirms the statement is already public in the form recorded. Allows a downstream builder to *consider* the claim; it does not authorize publishing or pushing anything automatically.
- **`review_required`:** Default for any claim without a visibility flag and for company-internal details, technical architecture, incidents, unannounced products, nonpublic metrics, vendor/customer information, uncertain rights, and material copied from documents not clearly cleared for sharing. Do not externally include until user reviews the proposed wording and explicitly authorizes it; approval can apply to one output only or to the persistent claim label as the user chooses.
- **`private`:** Personal salary/negotiation information, sensitive restrictions, private notes, nonpublic contact details, confidential personal situations, and any content the person explicitly wants private. Never include in a public-facing extract or resume while still classified `private`. Ask the person to create a new generalized statement and approve it independently if a publishable version would be useful.

**Release gate:** For all external-use outputs, use only `public` claims. Missing/invalid labels mean `review_required`, not `public`. Classifications apply to **specific claims**, not automatically all statements in a project. An entity-level `Visibility` is the default for unannotated content; an explicitly approved subheading/claim labeled `public` may override an inherited `review_required` default for *that claim only*. An entity explicitly marked `private` is a blanket embargo on all its contents. If two explicit restrictions apply to the same claim, the more restrictive wins (`private` > `review_required` > `public`). A project can therefore contain public high-level facts and restricted technical paragraphs without clearing the whole project. If granular annotations are ambiguous or unavailable, treat the affected content as `review_required` or more restrictive. `Anonymize` is an editing operation, **not** an approval or a visibility state: proposed sanitized wording still requires the user's review.

**Legacy v1 migration:** Convert `review-required` to `review_required`. Convert `shareable` and `anonymize` to `review_required` (old labels were not an affirmative publishing approval). Preserve `private`. Unknown values also become `review_required`. Never silently upgrade a previous claim to `public`.

## Collect less, not more

- The interview should ask about **roles, architecture decisions, trade-offs and lessons**, but use abstracted system diagrams, generic company/customer labels, approximate non-sensitive scale ranges where appropriate, and descriptions at a level safe for personal documentation.
- Never solicit or copy credentials, API keys, access tokens, keys in URLs, internal source code, unreleased security vulnerabilities, customer records, protected personal data, internal dashboards/log dumps, private colleague performance, or the identities of individual customers. When the person volunteers such material, avoid echoing it; ask for a generalized, non-identifying summary or omit the details.
- A private repository is **not** permission to record an employer's proprietary secrets. Respect confidentiality and employer obligations; when unsure, generalize or record only the technical concept/lesson as `review_required`.
- Ask about metrics without pressure. If a number may be nonpublic, ask for a permitted qualitative description instead; record unavailable numbers as unknown, not reconstructed guesses.
- Do not store home address, IDs, phone, birth date, immigration/health/financial information, or family information merely for career documentation. If the user needs a contact method for a separate resume, keep that outside `career.md` or restrict it to a deliberately approved public professional contact channel.
- Do not save detailed interview transcripts by default. Summarize minimal necessary facts in the source of truth. Keep Change History free of confidential statements.

## Workspace classification before the first write

When a writable workspace is available, determine where `career.md` would live **before creating or updating it**:

1. Check its repo/workspace context. A Git remote URL does **not** prove the repo is private. If a trusted capability can check visibility, use it; otherwise treat visibility as **unknown / potentially public**.
2. If known public, do **not** create or modify private `career.md` anywhere within that public repo, even with `.gitignore`. Suggest a separate private repo or directory outside it. Continue interviewing in conversation if the safe destination is not ready.
3. If unknown, ask for one-time confirmation that the destination is private before the first persistent write. Do not repeatedly ask after safe destination is established for the session; reassess if the destination changes.
4. If known private or outside a public/shared workspace and authorized, write `career.md` there. Still avoid secrets and follow claim-level classifications.
5. If no safe location can be established, keep a temporary in-conversation draft and offer an explicitly labeled **private download** rather than writing into the potentially public repo. Do not pretend a protected destination exists.

Do not run `git add`, `git commit`, `git push`, open a pull request, change repository visibility, or upload the career file unless the user explicitly requests the action. If they ask to commit/push private `career.md` to a known public repo, explain the risk and decline that destination; offer an approved public derivative instead. An ignore rule is defense in depth, not a publication guarantee: tracked files, force-add, Git history, forks and clones can still expose the contents.

## External sharing approval workflow

If a user asks to produce public-facing career material:

1. Identify candidate facts and their effective visibility, including restrictive inline annotations and contribution boundaries.
2. Exclude `private`; set aside `review_required` facts. Provide short **proposed paraphrases** for review only when needed, omitting underlying confidential specifics.
3. Ask for the user's explicit approval of the exact generalization/claim(s) to include; if unknown rights or employer confidentiality remain, prefer exclusion instead of promising that anonymization eliminates risk.
4. Generate the derivative only from eligible `public` claims or explicitly approved wording; flag estimates, limitations and attribution appropriately.
5. Do not publish the derivative to GitHub, send it, or share it with a third party without a separate explicit publishing/send request.

**Important:** The Career Interviewer documents career facts. It does not automatically author or publish tailored resumes; these rules are also a contract for a future Resume Builder.

## Quick threat-model scenarios

| Situation | Required behavior |
|---|---|
| Public GitHub project containing this skill | Allowed; distribute only skill files and synthetic templates. |
| User launches interview within public skill repo | Interview conversationally; do not save populated `career.md` in that repo. |
| Public status of current workspace can't be checked | Treat as potentially public; get one-time confirmation or choose private output. |
| User mentions exact internal API endpoint or customer data | Do not capture identifying detail; generalize or omit. |
| User provides an internal performance number | Mark `review_required` unless explicitly cleared; consider qualitative version. |
| User wants to add personal salary expectations | Mark `private`, if essential at all; never put in public outputs. |
| User says 'make everything public' | Do not blanket-clear employer-internal, third-party or sensitive material; propose a reviewed subset instead. |
| A future Resume Builder needs an unapproved claim | Omit it or request specific approval; do not silently promote its status. |
