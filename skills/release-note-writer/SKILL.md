---
name: release-note-writer
description: Generate concise, user-focused release notes on release day for Jira tickets labelled "rnw" (release note worthy), categorised by journey, written back to the ticket's Release Notes field with alternative drafts offered in a comment. Use whenever the user mentions release notes, a release or fixVersion going out, rnw-labelled tickets, or asks what to tell customers about what shipped.
---

# Release Note Writer

Generate release notes for tickets labelled `rnw` (release note worthy) on release day. Always use British English spelling and grammar.

## Process

**1. For each ticket with label `rnw`, `fixVersion = "{version}"`, and type in (bug, story):**

- Write a 1–2 sentence release note in natural, jargon-free language. Explain any acronyms you use — the audience for a release note is not the team that built it.
- Focus on the value to the user persona or the job to be done, not on what was implemented.
- Categorise each note into one of your product's journeys, e.g.:
  - **Journey A** — onboarding, account servicing, public API changes
  - **Journey B** — core product usage
  - **Other** — anything else
- Begin each note with the relevant journey, e.g. `Journey A: ...`

Swap the journey names for whatever your own product's journeys are called.

**2.** Add the release note to the **Release Notes** field on the ticket.

**3.** Add a comment to the ticket containing the release note plus **three additional draft suggestions** for alternative wording. Automatically select the most relevant one and use that for the Release Notes field — the alternatives are there for the user to swap in, not a decision to hand back to them.

**4.** Be clear, concise and professional throughout.

## Rules

- Maintain clarity and formatting in your responses.
- Use British English spelling and grammar at all times.