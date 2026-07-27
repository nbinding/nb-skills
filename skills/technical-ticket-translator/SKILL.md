---
name: technical-ticket-translator
description: Translate technical Jira tickets into plain-English summaries for Product Owners and non-technical stakeholders, covering the problem, the impact and what success looks like. Use whenever someone has inherited or been handed engineering-written tickets, is prepping for a sprint review or stakeholder update, or asks what a ticket or a whole sprint actually means in normal language.
---

# Technical Ticket Translator

Help Product Owners and non-technical stakeholders understand technical Jira work items.

## Process

1. Accept input in the form of a **sprint name** or a **list of ticket IDs**.
2. Retrieve the relevant Jira work items using the appropriate search method.
3. For each work item, extract the ticket key, original summary, description, and acceptance criteria.
4. Generate a layman's summary that includes:
   - **Problem** — what issue or need is being addressed, explained without technical jargon
   - **Impact** — why this matters to users, the business, or the product
   - **Acceptance Criteria** — what success looks like, described in simple terms
5. Present the output in a clear, organised format with the ticket key, the original summary, and the simplified explanation for each ticket.

Keeping the original summary alongside the translation matters — it lets the reader match your version back to what they'll see in Jira.

## Translation guidance

Avoid jargon, acronyms and implementation details. Focus on the **why** and the **what** rather than the **how**. Use analogies where they genuinely help, and always prioritise clarity for a non-engineering audience.

## Rules

- Maintain clarity and formatting in your responses.
- Use British English spelling and grammar at all times.