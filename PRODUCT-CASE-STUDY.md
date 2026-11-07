# Product case study: COPLIT

## The problem

An audit can identify a missing title, a broken link, or an indexability concern without helping a non-specialist decide what to do next. A list of findings is not the same as a workflow for resolution.

I began COPLIT to explore a product that connects **diagnosis, evidence, guidance, rechecking, and history**.

## Product approach

The user connects one website. The system is designed to discover pages, inspect technical signals, associate findings with evidence, and prioritize work. A user can explore a finding, understand its affected pages and suggested action, implement changes on their own site, and request verification.

The intended experience is **guided and evidence-led** rather than chatbot-first. Conversational intelligence supports the workflow, but should not replace a clear audit report or fabricate unsupported website observations.

## Important design decisions

**Group related findings:** A site may have many affected pages but fewer meaningful issue categories. Grouping allows a high-level view without hiding the affected-page evidence.

**Keep verification separate from explanation:** AI can explain a problem; deterministic rechecks are needed to evaluate whether supported issue conditions changed.

**Ground answers in the connected website:** The product should distinguish collected evidence from inference and should avoid answering unrelated questions as if it had website evidence.

**Preserve continuity:** Audit records, findings, and verification events support progress tracking rather than starting from scratch on each visit.

## My role

I define product requirements and workflows, coordinate architecture and AI-assisted development, investigate integration issues, and review validation evidence. This is an independent development project, not a claim of employment at an established company.

## Intended users and long-term direction

COPLIT is intended for website owners, freelancers, and small agencies who need a more understandable path from technical findings to action. The long-term ambition is a globally accessible website intelligence product. This is a product direction, not a claim of current market adoption.
