# Applied AI Applications — conditional target: COPLIT evidence

Grounding design, retrieval boundaries and evaluation discipline.

I work as a Product Builder across software systems and applied AI. This page explains how my personal product work relates to this role; it does not claim that I have held this job.

## The decision a reviewer can assess

**Problem:** A language model can produce a plausible explanation without observing the current website.

**My contribution:** Keep observations and deterministic findings authoritative; supply relevant authorized context for explanation and use separate checks for verification. My documented contribution spans requirements, product and system decisions, AI-assisted implementation coordination, investigation and review of validation results. Code generation was AI-assisted; no claim of unaided authorship is made.

**Recorded result:** The portfolio documents retrieval and provider responsibilities. The 43/43 historical deterministic run explicitly states calls_llm=False, so it is not evidence of model accuracy.

## Requirement to evidence

| Requirement | COPLIT work | Evidence | What a reviewer can ask |
|---|---|---|---|
| AI product and system reasoning | Connect the problem to a bounded decision | Product and engineering records | Why this decision, and what alternative did you reject? |
| Validation | Check the relevant condition or contract | Local workflow or simulated checks, as labelled | What did the check establish and what did it leave open? |
| Communication | Explain the system in terms of the user’s next decision | Portfolio narrative and linked evidence | Can you explain it without relying on the diagram? |

## Grounding example and evaluation requirements

If a user asks why a page lacks an H1, the proposed explanation path retrieves the correct website, audit, finding and page evidence before explaining the issue. After the user changes the website, a dedicated check evaluates the condition. This scenario describes the design; no captured Gemini request or answer is available in this package.

| Evaluation case | Expected behavior | Current evidence |
|---|---|---|
| Relevant evidence exists | Explain using the correct finding and page | Design and interpretation records |
| Evidence missing | State the limit rather than invent a page observation | Requirement; live model proof absent |
| User asks about another website | Preserve website scope | Requirement; live cross-site evaluation absent |
| User says “fixed” | Request supported verification, not model agreement | Historical deterministic workflow |

The next evidence required for this target is a working model/retrieval trace and evaluated examples. No API key, model call or live crawl was used to create this package.

## Remaining selection questions

Live Gemini grounding, retrieval relevance, a model evaluation dataset and latency/cost measurements are not established. This is a design evidence path, not proof of production AI engineering.

## Read the underlying work

[Product study](../PRODUCT-CASE-STUDY.md) · [Architecture](../ARCHITECTURE.md) · [Engineering cases](../ENGINEERING-CASE-STUDIES.md) · [Validation](../VALIDATION-AND-LIMITATIONS.md) · [Evidence index](../EVIDENCE-INDEX.md)

The examples above are historical local records, documented decisions or explicitly labelled illustrative scenarios. They are not production customer incidents.
