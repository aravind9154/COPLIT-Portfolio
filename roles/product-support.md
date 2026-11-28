# Product Support / Technical Support: COPLIT evidence

Reproduce a symptom, inspect evidence, explain next steps and escalate clearly.

I work as a Product Builder across software systems and applied AI. This page explains how my personal product work relates to this role; it does not claim that I have held this job.

## The decision a reviewer can assess

**Problem:** A reported fix can leave the user uncertain if the interface only shows before/after evidence without an explicit resolution indicator.

**My contribution:** Check the underlying state and verification evidence before saying the problem is resolved. Explain unavailable evidence rather than declaring success. My documented contribution spans requirements, product and system decisions, AI-assisted implementation coordination, investigation and review of validation results. Code generation was AI-assisted; no claim of unaided authorship is made.

**Recorded result:** History from 13 September records audit #53 with H1 count changing from 0 to 1, alongside the user reporting that no explicit resolved indicator was visible.

## Requirement to evidence

| Requirement | COPLIT work | Evidence | What a reviewer can ask |
|---|---|---|---|
| Technical diagnosis and communication | Connect the problem to a bounded decision | Product and engineering records | Why this decision, and what alternative did you reject? |
| Validation | Check the relevant condition or contract | Local workflow or simulated checks, as labelled | What did the check establish and what did it leave open? |
| Communication | Explain the system in terms of the user’s next decision | Portfolio narrative and linked evidence | Can you explain it without relying on the diagram? |

## Worked investigation: evidence changed, outcome unclear

1. Establish what the user sees: before/after heading evidence, without an explicit resolved indicator.
2. Inspect the recorded condition: H1 count changed from 0 to 1 in audit #53.
3. Separate the questions: page correction, saved finding status and visible feedback are different boundaries.
4. Check authoritative state before promising completion; use audit identity and the verification event for escalation.
5. Communicate the confirmed observation and the remaining uncertainty.

**Illustrative customer explanation, written from the historical case:** “The recheck now detects a main heading on the page. The screen has not clearly displayed the resolution status, so I would confirm the saved finding state before calling the workflow complete.” This is a communication sample, not a message sent to a customer.

**Escalation information:** audit identifier, finding type, observed H1 values, expected visible state, actual visible state and reproduction steps. Sanitized request/response data would strengthen this record; no original trace is attached here.

## Remaining selection questions

Paid customer support, ticket-volume or SLA results, customer satisfaction and shift availability are not established here.

## Read the underlying work

[Product study](../PRODUCT-CASE-STUDY.md) · [Architecture](../ARCHITECTURE.md) · [Engineering cases](../ENGINEERING-CASE-STUDIES.md) · [Validation](../VALIDATION-AND-LIMITATIONS.md) · [Evidence index](../EVIDENCE-INDEX.md)

The examples above are historical local records, documented decisions or explicitly labelled illustrative scenarios. They are not production customer incidents.
