# COPLIT
### AI-powered website intelligence — independent product engineering case study

**Aravind Mugappagari** · Product development · Backend integration · AI-assisted engineering · Technical SEO

COPLIT is an independent software product in active development. It aims to help website owners move from **finding technical problems** to **understanding, prioritizing, resolving, and verifying** them.

> **Status:** Development project, not a production-ready commercial service. The application source is maintained privately. This repository contains public-facing documentation, not application code.

## Why I started it

Website audit tools can return large lists of issues. The hard part for many users comes next: which findings matter, what evidence supports them, what should be changed, and did the fix actually work?

I designed COPLIT around a guided workflow rather than a chatbot-first interface or an unstructured list of errors.

**Connect → Crawl → Understand → Diagnose → Prioritize → Explain → Guide → Verify → Track**

## How it works

- **Discover and inspect:** Crawl website pages and collect technical signals, including browser-rendered observations where applicable.
- **Analyze and organize:** Associate supported technical findings with affected pages and evidence.
- **Prioritize and explain:** Make findings understandable and actionable, with website-grounded AI assistance under development.
- **Guide and verify:** Help users act on supported findings and recheck whether conditions have changed.
- **Remember progress:** Persist audit and verification information for history and continuity.

## Technology and responsibilities

| Area | Technology | Purpose |
| --- | --- | --- |
| User interface | Next.js, React, TypeScript, Tailwind CSS | Guided audit experience |
| API and services | Python, FastAPI | Orchestration and application endpoints |
| Data persistence | PostgreSQL | Websites, audits, findings, evidence, and history |
| Website inspection | Python crawler, Playwright | Page discovery and browser inspection |
| Intelligence | Evidence-grounded reasoning; Gemini integration in progress | Contextual explanations and guidance |
| Verification | Deterministic issue rechecks | Evaluate whether supported problems were resolved |
| Communication | REST APIs; SSE work in progress | Application requests and progressive responses |

## What I contributed

I have worked on requirements, architecture decisions, product workflows, AI-assisted implementation, integration investigation, debugging, and validation. My focus is on how components connect and how to establish that the system behaves as intended—not simply generating code.

## Selected engineering work

**Request reliability:** Coordinated improvements to deadline propagation, database timeouts, streaming cleanup, persistence forwarding, and API timeout mapping. A recorded P11 offline acceptance run passed **6/6 syntax checks, 31/31 mocked behavioral checks, and 9/9 source-contract checks**. These are offline results, **not** production benchmarks.

**Issue verification:** A prior local audit workflow recorded two supported findings verified after fixes, with next-finding progression. Wider coverage and live end-to-end acceptance are separate milestones.

**Grounded AI responses:** The design constrains explanations to connected-website evidence, while allowing natural-language questions without rigid keyword triggers. Integration and runtime behavior remain under development.

Read the detailed documents:
- [Product case study](PRODUCT-CASE-STUDY.md)
- [Architecture and system flow](ARCHITECTURE.md)
- [Engineering case studies](ENGINEERING-CASE-STUDIES.md)
- [Validation, limitations, and roadmap](VALIDATION-AND-LIMITATIONS.md)

## Long-term direction

Make website intelligence accessible to businesses, freelancers, and agencies by connecting technical diagnosis with understandable guidance and evidence-based verification.

**Source availability:** The original COPLIT implementation is private. No private code, credentials, customer data, or operational infrastructure details are published here.
