---
name: inventory-attention-review
description: Investigate Octane inventory exceptions when an operator asks which stock or sales-velocity signals need attention.
---

Read [the shared review rules](../../references/review-rules.md) before using tools.

1. Resolve the authorized store and requested period with `get_account_context`, then call
   `get_inventory_attention` using its advertised arguments.
2. Explain the returned stock and velocity signals in their own units and time
   window. Separate a recorded exception from a suspected cause. Describe missing
   counts, ambiguous identity, incomplete sales coverage, or stale observations
   only as supported by the result.
3. Group related findings for investigation. Prefer a small number of useful
   follow-ups over repeating every row. Preserve result limits and omitted counts;
   v1 examines the top 100 unit-selling items, not the store's complete inventory.
4. For each priority, give the observed signal, why it merits review, evidence,
   uncertainty, and the returned Octane navigation link. Suggest checking counts,
   identity, or supporting records only where relevant to that finding.

Do not infer unavailable stock as zero, compute new velocity or days-of-cover
metrics, invent reorder quantities, place orders, or change stock. If the user
asks to act, explain this review's read-only scope and direct them to Octane.
