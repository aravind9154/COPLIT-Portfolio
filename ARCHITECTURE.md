# Architecture and system flow

This document describes COPLIT's **logical architecture** and intended responsibilities. It is not a statement that every subsystem has completed live runtime acceptance.

```text
User / Guided UI
    |
    v
Next.js + React + TypeScript
    |
    v
FastAPI application endpoints and workflow coordination
    |
    +--> Website discovery: Python crawler / Playwright
    |        |
    |        v
    |    Page observations and technical signals
    |
    +--> Analysis: supported SEO checks and finding evidence
    |        |
    |        v
    |    Grouping / prioritization / explanations
    |
    +--> Guidance and deterministic re-verification
    |
    +--> PostgreSQL: websites, audits, pages, findings,
                     evidence, verification events, history

Evidence-grounded AI assistance supports explanation and guidance.
```

## Component responsibilities

### Frontend
Next.js, React, TypeScript, and Tailwind CSS support website connection, audit navigation, finding exploration, and guided interaction. The product direction favors a structured report rather than a chatbot as the primary surface.

### API and services
Python and FastAPI coordinate application requests and the backend workflow. Reliability concerns include consistent request deadlines, error mapping, and forwarding timeout constraints across service boundaries.

### Website discovery
Custom crawling and Playwright-based browser inspection collect observations needed by supported checks. Browser execution and external website crawling require explicit resource and security controls.

### Analysis and evidence
Analysis components interpret collected signals and associate supported findings with affected pages. Explanations should refer back to this evidence rather than invent missing measurements.

### Persistence
PostgreSQL stores the state required for website connections, audits, findings, evidence, verification events, and history. Database availability and recovery behavior must be validated in the integrated runtime.

### AI assistance
The intended conversational layer uses website-specific evidence and context to generate adaptive explanations and guidance. Gemini integration and runtime acceptance are ongoing work; this is not presented as a completed production capability.

### Verification
Supported finding types can be rechecked after a user makes changes. Verification is a separate technical operation from AI-generated advice.

## Security and publication boundaries

The implementation repository is private. This public document intentionally omits secrets, internal paths, deployment configuration, live customer information, and implementation-sensitive details.
