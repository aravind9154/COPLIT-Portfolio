# Engineering case studies

These examples are based on recorded COPLIT development and validation history. They distinguish implemented source changes and offline checks from live acceptance.

## 1. Request deadlines and API error mapping

**Problem:** A time budget is only useful if it is respected through application services, database access, and persistence. Otherwise, an operation can outlast the API request or return an unclear error.

**Investigation and decision:** Review the request path across the API boundary, intelligence services, database connections, and persistence. Propagate deadline constraints rather than treating each layer independently.

**Implementation work recorded:** Deadline propagation, database connection timeout handling, transaction timeouts, persistence forwarding, and mapping deadline failures to HTTP 504.

**Evidence:** Included in the six-patch P11 offline acceptance set. Syntax, mocked behavioral, and source-contract checks passed.

**Limitation:** Live deadline behavior and full end-to-end runtime acceptance were still pending in the recorded handover.

## 2. Streaming response lifecycle

**Problem:** Progressive responses need a clear lifecycle for completion, exceptions, and client disconnects. Without cleanup, resources or state can remain inconsistent.

**Engineering approach:** Strengthen streaming lifecycle handling and the contract between backend response generation and consumers.

**Evidence:** Streaming lifecycle repair was included in the accepted offline patch set.

**Limitation:** A passing mocked check does not establish live SSE disconnect behavior. That remains a runtime acceptance task.

## 3. Deterministic issue verification

**Problem:** A suggested fix is not proof that a website issue has been resolved.

**Engineering approach:** Separate explanatory guidance from rechecking the relevant website condition. Store the verification event and continue to the next outstanding finding.

**Recorded example:** A previous local audit (#58) included two findings that were reported as verified fixed, followed by successful next-finding progression.

**Limitation:** This is historical local validation evidence, not a claim of general accuracy or support for every SEO issue type.

## 4. Website-grounded conversational intelligence

**Problem:** A generic assistant may give plausible advice that is not supported by the website's actual observations.

**Design decision:** Restrict substantive answers to the connected website's collected evidence and preserve conversation context. Avoid hardcoded user phrases and forced response templates.

**Work completed:** Components for conversational understanding, evidence explanation, guidance, and continuity were developed and subjected to local checks.

**Limitation:** Full integrated, production-grade accuracy, runtime resilience, and model behavior have not been established.

## What these examples demonstrate

The engineering focus is on defining system contracts, tracing behavior across components, making targeted reliability improvements, and distinguishing **what was checked** from **what remains unproven**.
