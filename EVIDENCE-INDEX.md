# Evidence index

This index distinguishes evidence types so a reviewer can assess what a claim supports. Historical results are recovered project records, not a new execution of the application.

| ID | Record | Supported claim | Scope and limit |
|---|---|---|---|
| E01 | Public engineering case: local audit #58 | Missing H1 and meta description corrections verified; next-finding progression | Local workflow summary; original logs not included |
| E02 | Public P11 reliability record | Six accepted changes; 6/6 syntax, 31/31 mocked behavior and 9/9 source-contract checks | Offline checks; no live performance inference |
| E03 | History, 13 September 2026, audit #53 | H1 count 0 → 1; user could not see an explicit resolved indicator | Historical page evidence plus UI feedback; separate from #58 |
| E04 | History, 14 September 2026, audit #60 | Two findings resolved; open_findings=0; current_task=null | Historical retrieved state; separate from #53/#58 |
| E05 | History, 23 September 2026, Stage 4 | 43/43 recorded checks; targeted H1 verification, history and next task; calls_llm=False | Deterministic historical run; not model accuracy or broad SEO coverage |
| E06 | Public product study | Intended users, problem, trade-offs and proposed measures | Assumptions; not customer research or collected metrics |
| E07 | Public AI design | Retrieval/provider responsibilities and evidence boundaries | Live integrated retrieval and Gemini quality not established |
| E08 | New review-time VM check output | Existing main.ts CLI exercised against documented fixtures | Separate public project; newly authored tests, not historical user execution |

## Source locations

- [Recorded verification case](ENGINEERING-CASE-STUDIES.md#3-checking-whether-a-fix-worked)
- [Reliability patch record](RELIABILITY-AND-DEBUGGING.md)
- [Validation boundaries](VALIDATION-AND-LIMITATIONS.md)
- [Product assumptions and proposed measures](PRODUCT-CASE-STUDY.md)
- [AI design](AI-INTELLIGENCE.md)

E03–E05 were recovered from earlier chat records during the 28 November 2026 review. They are explicitly historical summaries; this page does not supply an original execution-log attachment. E01 and E02 are also present in the current public portfolio. Additional historical 52/52 and 14/14 summaries were found, but are omitted from headline claims because the complete scripts and original artifacts were not recovered here.

## Source availability

The connected private COPLIT repository inspected on 28 November contains the earlier HTML/JavaScript website tools, not the newer Python/FastAPI application described in development history. The missing source cannot be recreated faithfully from a summary. Runnable backend reproduction requires the actual current source and dependency versions. New example code must not be presented as recovered COPLIT code.

## Contribution boundary

Aravind defined product direction, requirements and system responsibilities, coordinated AI-assisted development, investigated failures and reviewed proposed changes and validation results. This does not claim unaided authorship of every source file or production customer delivery.

## Newly measured evidence

The VM fixture runner and its output were created by an AI assistant for this review. Before adopting those results as a portfolio demonstration, Aravind should inspect the scenarios, run them and explain the implementation. The original main.ts is unchanged. These checks exercise selected behavior, not complete specification compliance or bounty acceptance.
