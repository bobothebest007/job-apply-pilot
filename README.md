# Job Apply Pilot

An [OpenClaw](https://openclaw.ai/) skill for assisted job applications: autofill where available, verify the actual form, submit, and log only confirmed submissions.

This is a **workflow skill**, not a standalone auto-apply service. It does not include a résumé, credentials, a tracker, or a browser extension. It works with the user's authorized browser and application profile; an autofill extension such as Simplify is optional.

## What it does

1. Checks the role and tracker for an existing application.
2. Uses available autofill once, then reviews the entire form and résumé attachment.
3. Resolves unknown facts with the user and drafts grounded open-ended answers.
4. Submits only after review and requires a visible confirmation.
5. Records the confirmed submission in the user's chosen tracker.

The instructions are in [SKILL.md](SKILL.md). They deliberately leave personal facts, consent preferences, and tracker details to each user's own configuration.

## Install

Copy `SKILL.md` into a directory under your OpenClaw workspace's `skills/` folder, for example:

```text
<workspace>/skills/job-apply-pilot/SKILL.md
```

OpenClaw discovers workspace skills by their `SKILL.md` frontmatter. Start a new session or refresh your skill snapshot after installation. Provide your own application profile and tracker instructions separately; never put private application data into this public repository.

## Use

Ask your agent to apply to a specific job URL. Ensure the browser session you authorize can reach the application, and provide or approve factual answers the agent cannot verify. If you use an autofill extension, make it available in that browser session. The skill requires confirmation from the application site before it records a submission.

## Limits

- Autofill results and extension completion counts can be stale or wrong; the application form is the source of truth.
- Browser drivers differ in extension, upload, iframe, and batching support.
- Employer-specific questions and factual certifications still require verified answers.
- The skill does not bypass captchas, login challenges, or access restrictions.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). This project is licensed under the [MIT License](LICENSE).
