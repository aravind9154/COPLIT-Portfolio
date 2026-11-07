# Reliability and debugging: request deadlines across COPLIT

> **Evidence standard:** This case study distinguishes recorded source changes and offline acceptance from live integrated runtime behavior. COPLIT remains in development; this document does not claim production reliability.

## The problem

A request may cross an API endpoint, application service, database operation and persistence step before producing a response. If each layer manages its own timeout without respecting the caller's remaining budget, the overall request can run longer than intended. The visible symptom may be a timeout, but the underlying cause can be at another boundary.

For COPLIT's conversational and audit workflows, a reliable result also needs a clear error outcome and consistent treatment of state when work cannot complete.

## The investigation approach

The engineering review considered the request as an end-to-end sequence rather than debugging only the endpoint that displayed an error:

1. Identify the incoming API boundary and the deadline available to the request.
2. Trace how the time budget is forwarded into downstream intelligence and service calls.
3. Check database connection and transaction timeout behavior.
4. Examine persistence forwarding so state operations do not silently ignore the request deadline.
5. Check how the API maps an exceeded deadline into an understandable HTTP result.
6. Separately consider streaming lifecycle completion, errors and disconnect cleanup.

This is a description of the recorded engineering approach, not a reproduction of private source files.

## The recorded strengthening work

The P11 offline acceptance set covered six reliability patches:

| Area | Purpose |
| --- | --- |
| Streaming lifecycle | Improve completion/error/disconnect lifecycle handling |
| Deadline propagation | Forward request time budgets across service boundaries |
| Database connection timeout | Bound time spent acquiring a database connection |
| Transaction timeout | Bound relevant database operations |
| Persistence forwarding | Carry deadline constraints into persistence-related work |
| API HTTP 504 mapping | Represent deadline-exceeded failures at the API boundary |

These changes address different parts of the same reliability concern. A correctly mapped HTTP response is not enough if downstream work ignores the deadline, and a bounded database operation is not enough if another service can exceed the remaining budget.

## What the offline checks established

The recorded P11 acceptance results were:

| Check type | Result | What it supports |
| --- | --- | --- |
| Python syntax | **6/6 passed** | Relevant patched sources passed the recorded syntax checks |
| Mocked behavioral checks | **31/31 passed** | Expected behavior under the recorded mocked conditions |
| Source-contract checks | **9/9 passed** | Recorded structural and forwarding contracts were satisfied |

These are historical project records, not independently verified benchmarks or live operational measurements.

## What remains unproven

The offline results alone do not establish:

- Live API deadline behavior under an actual local request.
- End-to-end HTTP 504 mapping across all relevant runtime paths.
- SSE streaming behavior when a real client disconnects.
- Database persistence, recovery and restoration behavior in the integrated development runtime.
- Performance, availability or resilience under production traffic.

The recorded next phase was safe local service identification and runtime acceptance, with no assumption that a listening port belongs to COPLIT until verified.

## A practical debugging model

When a request fails, I use these questions to structure investigation:

**Where was the failure observed?** UI, API, service, database, or response stream?

**What should that boundary have guaranteed?** For example, a valid response, a respected deadline, an explicit error status or preserved state.

**What evidence is available?** Request status, sanitized logs, recorded validation output and known source contracts.

**What was actually checked?** A mocked check, syntax validation and a live integrated request prove different things.

**What remains unknown?** A clear limitation is more useful than assuming that an offline pass establishes runtime correctness.

## Engineering lesson

Reliability is a cross-layer contract. Debugging becomes more effective when a visible symptom is traced through the system's actual responsibilities and the evidence for each conclusion is stated precisely.

Related documents: [System walkthrough](SYSTEM-WALKTHROUGH.md), [Engineering case studies](ENGINEERING-CASE-STUDIES.md), [Validation and limitations](VALIDATION-AND-LIMITATIONS.md).

**Security boundary:** This document intentionally excludes private source code, secrets, customer data, internal machine paths and operational configuration.
