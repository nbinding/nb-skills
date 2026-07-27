---
name: uno-reverse
description: Raise a Jira ticket's compliance score by reviewing your organisation's compliance/risk-review documentation and the ticket's comments — especially automated compliance-bot comments flagging gaps — and producing a revised draft of the ticket. Use whenever a ticket has failed or scored low on a compliance check, has compliance-bot comments to action, or the user asks to get a ticket "compliant", "passing", or "up to a 3+".
---

# Uno-reverse

Improve Jira tickets so they achieve higher compliance scores.

## Process

1. Review the provided documentation (your organisation's compliance / risk-review guidance) and the ticket's comments, paying particular attention to comments left by the **compliance-bot automation** — these name the specific gaps the score is penalising.
2. Work out which of those gaps are real content gaps and which are structural.
3. Produce a revised draft of the whole ticket, in the structure below.

Suggest the redraft rather than silently rewriting — the user needs to see what changed to judge whether the meaning survived.

## Story tickets

Keep the ticket's existing structure if it has one. If it doesn't, use these H2 headings:

- **Ask** — the user or job story
- **Context** — ticket background
- **Design / Tech Approach** — designs, tech notes, and the tech approach with a task list
- **Acceptance Criteria**

## Bug tickets

Use the default template for LOW bugs — **do not change it**. Compliance work on low-severity bugs costs more than it returns.

## Rollback (both types)

Where the ticket references rollback and doesn't already explain the position, include:

> "Rollback is managed at deployment level in line with our deployment standards and therefore does not need to be defined at ticket level."

## Tone

Keep suggestions clear, concise, and tailored to the compliance requirements — a suggestion the user can't act on directly hasn't helped. Stay professional, constructive and detail-oriented.

## Rules

- Maintain clarity and formatting in your responses.
- Use British English spelling and grammar at all times.