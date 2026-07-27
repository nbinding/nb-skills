# nb-skills

A set of Claude Code skills for product management and delivery work. Most of them operate on Jira, Confluence and related tooling. All of them write in British English.

Written by [Nathan Binding](https://www.nathanbinding.co.uk/). Product manager and design consultant.

---

## Install

Skills are folders containing a `SKILL.md` file. Claude Code loads them from two places.

**For one project:**

```bash
git clone https://github.com/nbinding/nb-skills.git
cp -r nb-skills/skills/* /path/to/your-project/.claude/skills/
```

**For every project on your machine:**

```bash
cp -r nb-skills/skills/* ~/.claude/skills/
```

Claude picks a skill automatically when the request matches its `description`. You can also call one by name, for example `/pdd-prd-generator`.

## Requirements

Most of these skills read and write Jira and Confluence. You need the Atlassian MCP server connected before they can do anything. Run `/mcp` in Claude Code to check. They can also be tweaked for the equivalent tools needed.

The skills that only transform text you paste in need nothing extra: `meeting-notes-organiser`, `technical-ticket-translator` (output only), `ste-writing-skill`.

---

## The skills

| Skill | Does | Needs Jira/Confluence |
|---|---|---|
| [pdd-prd-generator](skills/pdd-prd-generator/SKILL.md) | Scrappy notes into a Product Definition Document | Optional |
| [product-to-design-brief](skills/product-to-design-brief/SKILL.md) | PDD into a 12-section UX/UI design brief | Optional |
| [ticket-sharkitect](skills/ticket-sharkitect/SKILL.md) | Build and refine Jira Epics, Stories and Spikes | Yes |
| [acceptance-criteria-organiser](skills/acceptance-criteria-organiser/SKILL.md) | Move ACs out of the description into the AC field | Yes |
| [uno-reverse](skills/uno-reverse/SKILL.md) | Redraft a ticket to raise its compliance score | Yes |
| [technical-ticket-translator](skills/technical-ticket-translator/SKILL.md) | Technical tickets into plain English for stakeholders | Yes |
| [rag-syncer-bot](skills/rag-syncer-bot/SKILL.md) | Sync RAG status between JPD Ideas and Software Epics | Yes |
| [release-note-writer](skills/release-note-writer/SKILL.md) | Customer-facing release notes from `rnw` tickets | Yes |
| [meeting-notes-organiser](skills/meeting-notes-organiser/SKILL.md) | Raw notes into a fixed six-heading write-up | No |
| [ste-writing-skill](skills/ste-writing-skill/) | Rewrite prose into Simplified Technical English | No |

### Writing and documents

**[pdd-prd-generator](skills/pdd-prd-generator/SKILL.md)** — `pdd-generator`. Takes chat messages, meeting notes or Jira issues and produces a Product Definition Document: required change, background and problem statement, OKRs, a MoSCoW requirements table, out of scope, and dependencies and assumptions. Gaps get flagged in place as `[NEEDS CLARIFICATION: ...]` rather than guessed at. Outputs to a Confluence page or to chat.

**[product-to-design-brief](skills/product-to-design-brief/SKILL.md)** — `product-to-design-brief`. Turns a PDD or PRD into a 12-section design brief covering screens, states and edge cases, interactions, accessibility, copy guidance and user flows. It asks first whether the brief is for a human designer or for an AI design tool, because that changes the detail and the tone. For AI tools, section 12 is a copy-paste-ready prompt.

**[meeting-notes-organiser](skills/meeting-notes-organiser/SKILL.md)** — `meeting-notes-organizer`. Restructures scrappy notes under six fixed headings: context, key decisions, new scope, risks, next steps, and questions asked and answered. It reorganises, it does not invent. Empty sections stay in place, because an empty "Risks and Concerns" heading tells the reader nobody raised any.

**[ste-writing-skill](skills/ste-writing-skill/)** — `ste-writing`. Rewrites documentation, READMEs, PR text, error messages and release notes into ASD-STE100 Simplified Technical English. Short sentences, active voice, one name per thing, no marketing adjectives, no semicolons, no em dashes. Two modes: strict for procedures and safety text, STE-flavoured for general prose. Not for anything that needs a voice. It strips voice on purpose.

### Ticket work

**[ticket-sharkitect](skills/ticket-sharkitect/SKILL.md)** — `ticket-sharkitect`. Builds Epics, Stories and Spikes that are clear enough to deliver without a follow-up conversation. Applies the team template, then walks you through Ask and Context, Tech Implementation and Acceptance Criteria one section at a time. Pulls supporting context from related tickets, Confluence, Miro and GitHub. Checks what is still missing before the ticket progresses.

**[acceptance-criteria-organiser](skills/acceptance-criteria-organiser/SKILL.md)** — `acceptance-criteria-organizer`. Finds acceptance criteria buried in a ticket description, moves them into the dedicated AC field, and deletes the leftover heading and duplicated text. Does nothing at all if there are no ACs in the description, so it does not add noise to the ticket history.

**[uno-reverse](skills/uno-reverse/SKILL.md)** — `uno-reverse`. Reads the compliance-check comments on a ticket, works out which flagged gaps are content and which are structural, and produces a full redraft under Ask, Context, Design / Tech Approach and Acceptance Criteria. It suggests rather than silently rewrites, so you can see whether the meaning survived. Leaves low-severity bug templates alone.

**[technical-ticket-translator](skills/technical-ticket-translator/SKILL.md)** — `technical-ticket-translator`. Takes a sprint name or a list of ticket IDs and produces plain-English summaries for Product Owners and non-technical stakeholders: the problem, the impact, and what success looks like. Keeps the original summary next to each translation so the reader can match it back to Jira.

### Status and reporting

**[rag-syncer-bot](skills/rag-syncer-bot/SKILL.md)** — `rag-syncer-bot`. Keeps RAG status and commentary in step between linked Jira Product Discovery Ideas and Jira Software Epics, re-toning the commentary for each audience. Delivery detail goes up to the Epic, executive summary goes out to the Idea. Synthesises commentary from the latest comment when the field is empty. Output is a strict single-line `status=...; comment=...` string with an ISO date prefix, so a downstream parser can read it. Touches the RAG fields and nothing else.

**[release-note-writer](skills/release-note-writer/SKILL.md)** — `release-note-writer`. On release day, finds tickets labelled `rnw` in the target `fixVersion` and writes a one or two sentence customer-facing note for each, categorised by journey. Writes the best one to the Release Notes field and puts three alternative drafts in a comment. Focuses on the job to be done, not on what was implemented.

---

## Conventions

Every skill in here follows the same three rules:

1. **British English** spelling and grammar, always.
2. **Do the narrow thing.** Skills that write to Jira name the exact fields they may touch and leave everything else alone.
3. **Flag gaps, do not fill them.** A named gap is more useful to a stakeholder than a confident guess.

---

## Generic and portable

Every skill here is written against generic tooling, not a named client, team or product. Where a skill originally referenced a specific compliance tool, internal template page, or product journey taxonomy, that has been replaced with a placeholder description (e.g. "your organisation's compliance/risk-review tooling", "Journey A / Journey B"). Swap those placeholders for your own team's names before use.

## Publishing

Once you have made that call:

```bash
cd /Users/nathanbinding/Projects/nb-blog

# 1. Start the repo
git init
git add .
git commit -m "feat: initial set of product and delivery skills"

# 2. Check what you are about to publish, one more time
git show --stat HEAD

# 3. Create it on GitHub and push
gh repo create nb-skills --public --source=. --remote=origin --push
```

`.gitignore` already excludes `.claude/settings.local.json`. That file holds local machine paths rather than secrets, but it is per-machine and does not belong in a shared repo.

To publish under a different name, change `nb-skills` in the `gh repo create` line. To go private first and flip later, use `--private` now, then `gh repo edit --visibility public --accept-visibility-change-consequences` when you are ready.

## Licence

There is no licence file yet. Without one nobody has permission to reuse these, which defeats the point of publishing. Add MIT if you want people to take them.