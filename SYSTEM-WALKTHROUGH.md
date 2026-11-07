# COPLIT system walkthrough

> **Scope:** Public engineering documentation of an independent product in active development. This is a logical walkthrough based on recorded architecture and project work, not proof that every path has passed live end-to-end testing. The implementation repository remains private.

## The product problem

An SEO audit can identify a technical condition without helping the user decide what to do next. COPLIT is designed to connect discovery, diagnosis, evidence, guidance, rechecking and history in a single workflow.

The conceptual journey is:

**Connect → Crawl → Understand → Find → Prioritize → Explain → Evidence → Guide → User fixes → Verify → History → Next**

The interface is intended to be a guided audit experience, not a chatbot-first dashboard.

## The technology map

| Layer | Technology | Responsibility |
| --- | --- | --- |
| User interface | Next.js, React, TypeScript, Tailwind CSS | Connect a website; present reports, findings and actions |
| API | Python, FastAPI | Receive authenticated requests, coordinate work and return results |
| Website inspection | Python crawler, Playwright | Discover pages and collect technical or browser-rendered observations |
| Diagnosis | Supported technical checks and evidence processing | Turn observations into findings associated with affected pages |
| Persistence | PostgreSQL | Retain website, audit, page, finding, evidence, verification and history records |
| Explanations | Evidence-grounded AI design; Gemini integration in progress | Communicate findings in context without inventing website observations |
| Verification | Deterministic supported-issue rechecks | Inspect whether the relevant condition changed after a user fix |
| Communication | REST; SSE work under validation | Connect UI requests with backend processing and progressive responses |

## Walkthrough: from connection to action

### 1. Connect and identify the website

A user connects a website through the interface. The backend must associate requests and results with the authenticated account and connected website. Website input validation and account isolation are important trust boundaries. A connection is the start of an audit, not proof that every page is reachable or inspectable.

### 2. Discover and observe pages

The Python crawler discovers reachable pages and collects technical signals. Playwright can support browser-rendered inspection where applicable. Resource budgets, redirects, unsupported protocols, and safe handling of external content are engineering concerns. A collected observation should be distinguishable from a guess or a missing measurement.

### 3. Interpret observations as findings

Supported checks examine collected signals, such as whether a page has an expected heading or meta description. Findings can be associated with affected pages and supporting evidence. A reported count should be traceable to observations and the audit scope; it should not imply complete coverage of the public web.

### 4. Prioritize and explain

The product aims to group related issues and explain which actions deserve attention. Priority is a product decision informed by evidence, not simply the number of warnings. The conversational intelligence work aims to answer arbitrary natural-language questions about the connected website while staying grounded in its evidence. Gemini integration and integrated runtime validation remain in progress.

### 5. Guide, recheck, and retain history

A user makes a change to their own website. For supported finding types, deterministic verification re-inspects the relevant condition rather than trusting a user assertion or an AI-generated answer. The application can record verification events and continue to the next outstanding finding. Historical local audit #58 recorded two supported findings verified fixed; that is not a universal verification guarantee.

## How the layers interact

A simplified logical path is:

```text
User action in guided UI
        |
        v
Next.js / React frontend
        |
        v
FastAPI request boundary
        |
        +----> crawler / browser inspection ----> page observations
        |                                          |
        |                                          v
        +----> supported checks -------------> findings + evidence
        |                                          |
        +----> explanation / guidance <-------------+
        |
        +----> PostgreSQL: audit, finding, evidence, verification history
        |
        v
UI report, evidence detail, action guidance and supported recheck
```

This diagram describes responsibilities, not a guarantee that each path is currently production-ready.

## Where failures can occur

- **Frontend/API boundary:** incorrect request shape, authentication failure, unexpected response or stale UI state.
- **Crawl/inspection boundary:** unreachable pages, redirects, browser execution limits, time budgets or incomplete observations.
- **Analysis/evidence boundary:** unsupported issue types, missing evidence or mismatched page associations.
- **API/database boundary:** unavailable connections, transaction deadlines, persistence or restoration problems.
- **AI/explanation boundary:** insufficient grounding, out-of-scope questions or model failures.
- **Verification boundary:** a change that was not deployed, an unsupported recheck, or a new observation that does not match the claimed fix.

A useful investigation starts by locating the boundary where the expected contract diverged from the observed result, rather than assuming the visible UI error identifies the root cause.

## What has and has not been demonstrated

Recorded development evidence includes P11 offline checks (6/6 syntax, 31/31 mocked behavior and 9/9 source-contract checks) and a historical local verification workflow. Those checks do **not** establish production uptime, universal issue accuracy, real-world customer outcomes or complete live runtime acceptance.

For more detail, see [Architecture](ARCHITECTURE.md), [Engineering case studies](ENGINEERING-CASE-STUDIES.md), and [Validation and limitations](VALIDATION-AND-LIMITATIONS.md).

## Publication boundary

No private application code, internal file paths, credentials, customer data, database connection details or deployment configuration are included here.
