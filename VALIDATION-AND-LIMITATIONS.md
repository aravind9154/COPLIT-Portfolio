# What I have tested and what remains

## Recorded evidence

| Check | Outcome | Evidence scope |
|---|---|---|
| P11 syntax | 6/6 passed | Recorded offline checks of the reliability changes |
| P11 mocked behavior | 31/31 passed | Historical offline patch acceptance |
| P11 source contracts | 9/9 passed | Historical offline patch acceptance |
| Conversational understanding | 17/17 passed | Recorded checks of conversational understanding |
| Local audit #58 | Two findings verified fixed; next finding progressed | Recorded local audit |

These are summarized development records. Original sanitized logs and independently reproducible demonstrations are not yet attached. No production benchmarks, customer outcomes or model accuracy claims are made.

## What I still need to test

| Capability | What needs checking |
|---|---|
| Authenticated workspace | End-to-end session and account ownership checks |
| Website inspection | Safe resource limits and supported observation coverage |
| API reliability | Live deadline and HTTP 504 behavior |
| SSE | Completion, disconnect and error cleanup |
| Persistence | Recovery, transaction consistency and workspace restoration |
| AI and retrieval | Website scope, evidence grounding and provider failure handling |
| Verification | Supported issue coverage and uncertain outcomes |
| Production readiness | Dependency reproducibility, migrations, security and operational readiness |

## Before releasing COPLIT

```mermaid
flowchart LR
 A[Source changes] --> B[Offline checks]
 B --> C[Integrated local acceptance]
 C --> D[Security and operational acceptance]
 D --> E[Release decision]
```

Passing a syntax check means the code can be parsed. Mocked checks test behavior using controlled substitutes for dependencies. Source-contract checks examine expected code relationships. None of these alone proves that the whole application works with real services. The project remains in active development. The private implementation and credentials are not published.

[Engineering investigations](ENGINEERING-CASE-STUDIES.md) · [Architecture](ARCHITECTURE.md)
