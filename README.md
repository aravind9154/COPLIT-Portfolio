<div align="center">

# COPLIT

**Website diagnostics, practical guidance and verification**

AI-powered SEO intelligence

</div>

COPLIT brings technical website inspection and guided problem resolution into one workspace. Its central design decision is to keep observed website evidence separate from AI-generated explanations and to check corrections independently.

## Product experience

| Stage | What the user needs | System responsibility |
|---|---|---|
| Connect | Identify the website to inspect | Establish website scope and initiate inspection |
| Understand | Know what is wrong and why | Collect observations, group findings and explain their impact |
| Act | Decide what to change | Prioritize findings and provide relevant guidance |
| Verify | Know whether the change worked | Reinspect supported conditions and record the result |
| Return | Continue without starting over | Retain audit history and restore context |

## Reading the portfolio

Start with product research for the problem and requirements, then follow the architecture and AI design to understand how the solution is organized. The engineering investigations and validation records distinguish documented outcomes from design requirements. Each document can also be read independently.

## Explore the product and its engineering

| Area | Questions answered |
|---|---|
| [Product research and design](PRODUCT-CASE-STUDY.md) | Why this problem? Who needs the solution? How were product decisions made? |
| [System architecture](ARCHITECTURE.md) | How do the interface, APIs, crawler, database and services communicate? |
| [AI intelligence](AI-INTELLIGENCE.md) | How does retrieval connect website evidence to language-model explanations? |
| [Engineering investigations](ENGINEERING-CASE-STUDIES.md) | How were reliability problems investigated and corrections evaluated? |
| [Validation and reliability](VALIDATION-AND-LIMITATIONS.md) | What behavior has been checked, and what remains unverified? |

## A documented engineering outcome

In a recorded local audit, reinspection confirmed corrections to missing main headings (H1) and missing meta descriptions. Both findings were marked fixed and the workflow moved to the next finding. [Read the verification investigation](ENGINEERING-CASE-STUDIES.md#3-checking-whether-a-fix-worked) for the workflow and evidence boundaries.

## Product and engineering ownership

I define product requirements and system responsibilities, coordinate AI-assisted development, investigate failures and review test outcomes.

## Design principles

- Findings originate from website observations, not language-model guesses.
- Guidance explains the evidence; the website owner controls changes.
- Verification checks observable conditions rather than accepting a claim that a fix worked.
- Website and account boundaries are required for access to stored information.

The portfolio documents product decisions, architecture and recorded engineering work. Application source is private. Detailed implementation and validation boundaries are described in the linked documents.

---
**Next:** [Product research & design](PRODUCT-CASE-STUDY.md) · [Portfolio home](README.md) · [Professional profile](https://github.com/aravind9154)
