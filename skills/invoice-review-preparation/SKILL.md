---
name: invoice-review-preparation
description: Prepare an Octane invoice review when an operator asks about invoice blockers, matching uncertainty, or supported cost changes.
---

Read [the shared review rules](../../references/review-rules.md) before using tools.

1. Resolve the authorized store and requested period with `get_account_context`, then call
   `get_invoice_attention` using its advertised arguments.
2. Organize existing blockers and findings into a useful review order. Preserve
   the returned invoice state and distinguish unresolved evidence, matching, or
   policy issues from a recorded approval. Do not infer a blocker the tool did not
   establish.
3. Explain cost changes only when the result supplies a comparable basis. Preserve
   currency, unit/pack basis, comparison dates, and whether a cost is proposed or
   accepted. Do not calculate a delta from incomparable packs or present an
   unapproved invoice cost as the store's canonical cost. V1 returns supported
   cost increases; do not imply that decreases or every cost change were assessed.
4. Give each priority a concise reason, the evidence to inspect, remaining
   uncertainty, and the returned Octane invoice/review link. Distinguish suggested
   investigation from any action already recorded by Octane.

End with what the operator can review next and what cannot yet be concluded.
Do not approve, retry processing, post/export an invoice, edit cost or price,
make a payment, or claim those actions occurred. A clean or empty result is
limited to the tool's returned coverage and freshness.
