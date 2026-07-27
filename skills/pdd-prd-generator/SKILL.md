---
name: pdd-prd-generator
description: Turn scrappy notes, chat messages, meeting notes or Jira issues into a standardised Product Definition Document (PDD), or into the initial Idea template for a technical roadmap. Use whenever the user has raw product requirements to formalise, is starting a new roadmap item, mentions a PDD or PRD, or asks to write up an idea properly for stakeholders.
---

# PDD / PRD Generator

Create comprehensive Product Definition / Requirement Documents from whatever input is available.

## Process

**1. Analyse the provided input** — chat messages, existing documents, meeting notes, Jira issues, or other sources — to extract the relevant product information.

**2. Structure the content** into these sections:

- **Describe the required change** — a clear, concise summary of what needs to be built or modified
- **Background/Problem Statement** — detailed explanation of the problem being solved, how it aligns with organisational goals, and whether the work is strategic (long-term, foundational) or tactical (short-term, specific)
- **Objective & Key Results** — specific project goals and measurable success metrics, in OKR format
- **High Level Requirements** — a table with columns: Requirement | Why (what it will achieve) | MoSCoW (Must/Should/Could/Won't have) | Who, When, Where (source, how captured, when) | Notes
- **Out of Scope** — features or capabilities explicitly excluded from this phase but which may be considered later
- **Known key dependencies & assumptions** — technical constraints, user assumptions, business prerequisites, and dependencies on other systems or teams

**3. Apply British English** spelling and grammar throughout (e.g. "organisation" not "organization", "analyse" not "analyze", "prioritise" not "prioritize").

**4. Explain technical jargon** in plain language when first introduced, with brief definitions in parentheses or footnotes.

**5. Keep content detailed but concise** — include the necessary context without redundancy. Each section should be thorough but avoid unnecessary verbosity.

**6. Format professionally** — use appropriate headings, tables and bullet points for clarity. Ensure tables are properly formatted with clear column headers.

## Handling gaps

When requirements or details are unclear from the input, flag these gaps explicitly in the relevant section, e.g. `[NEEDS CLARIFICATION: Success metrics not specified]`. Naming the gap in place is more useful than quietly guessing — it tells stakeholders exactly what still needs defining.

Always maintain a professional, objective tone suitable for enterprise documentation.

## Output medium

If creating or updating a **Confluence page**, structure the page with clear headings for each section and use Confluence formatting (tables, panels, status macros) appropriately. If providing output **in chat**, format using markdown for readability.

## Rules

- Maintain clarity and formatting in your responses.
- Use British English spelling and grammar at all times.