# Technical Product Analyst / Business Analyst: COPLIT evidence

Requirements, state analysis, evidence interpretation and clear specifications.

I work as a Product Builder across software systems and applied AI. This page explains how my personal product work relates to this role; it does not claim that I have held this job.

## The decision a reviewer can assess

**Problem:** A finding, its page evidence and its verification history must remain traceable across interface, service and persistence boundaries.

**My contribution:** Define the expected state transition and evidence before evaluating the response. Separate display text from the stored finding status. My documented contribution spans requirements, product and system decisions, AI-assisted implementation coordination, investigation and review of validation results. Code generation was AI-assisted; no claim of unaided authorship is made.

**Recorded result:** History from 14 September records audit #60 with two resolved findings, zero open findings and no current task. That is a separate audit from #58.

## Requirement to evidence

| Requirement | COPLIT work | Evidence | What a reviewer can ask |
|---|---|---|---|
| Requirements and system analysis | Connect the problem to a bounded decision | Product and engineering records | Why this decision, and what alternative did you reject? |
| Validation | Check the relevant condition or contract | Local workflow or simulated checks, as labelled | What did the check establish and what did it leave open? |
| Communication | Explain the system in terms of the user’s next decision | Portfolio narrative and linked evidence | Can you explain it without relying on the diagram? |

## Worked analysis: distinguish evidence, state and next task

| Question | Historical observation | Interpretation |
|---|---|---|
| Did the observed page condition change? | Audit #53: H1 count 0 → 1 | Relevant page evidence changed |
| Was the resolution clearly visible? | Same run: user could not see an explicit resolved indicator | Evidence and interface communication need separate acceptance |
| Can completed state be retrieved? | Separate audit #60: two resolved findings, open_findings=0, current_task=null | A recorded saved-state result; not a persistence benchmark |

These are separate historical observations, not a joined dataset or a newly executed SQL analysis. A traceable requirement is: when supported evidence establishes correction, the stored result, visible status and next-task decision should agree. A reviewer can ask how each boundary is checked and how unknown evidence is represented.

## Sample specification derived from the case

Given an open finding with an affected page, when a supported reinspection supplies sufficient evidence that the relevant condition is corrected, then record the verification event, update the finding and select the next unresolved task. When the evidence is unavailable, preserve an uncertain outcome instead of recording success. This is a proposed readable specification of the recorded workflow, not a recovered original ticket.

## Remaining selection questions

Advanced SQL, BI dashboards, statistical inference and commercial domain analysis are not demonstrated by the inspected materials.

## Read the underlying work

[Product study](../PRODUCT-CASE-STUDY.md) · [Architecture](../ARCHITECTURE.md) · [Engineering cases](../ENGINEERING-CASE-STUDIES.md) · [Validation](../VALIDATION-AND-LIMITATIONS.md) · [Evidence index](../EVIDENCE-INDEX.md)

The examples above are historical local records, documented decisions or explicitly labelled illustrative scenarios. They are not production customer incidents.
