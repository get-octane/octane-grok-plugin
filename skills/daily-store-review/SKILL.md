---
name: daily-store-review
description: Review an Octane store's operating-day performance and material inventory or invoice exceptions when an operator asks for a daily briefing or priorities.
---

Read [the shared review rules](../../references/review-rules.md) before using tools.

1. Resolve the authorized store and requested operating period with
   `get_account_context`. For a routine daily briefing without a date, ask for the
   operating day. Account context does not identify the latest available day.
   Name the chosen day and coverage.
2. Call `get_store_performance` for that store and bounded period. Explain the
   returned performance and supported comparisons. A movement is an observation;
   a possible explanation is a hypothesis unless evidence supports the cause.
3. Call `get_inventory_attention` and `get_invoice_attention` for the same store,
   using only date parameters supported by each schema. Identify when their
   windows differ from the performance period; do not imply a common window.
4. Prioritize the most material supported findings by the returned impact,
   urgency, and confidence. Preserve uncertainty instead of inventing an impact
   score or financial estimate. Include useful positive findings only when the
   coverage supports them.

Give the operator the store and period, a concise performance explanation, material
exceptions with evidence and Octane links, and a prioritized follow-up list. Name
unavailable domains and incomplete comparisons. Keep observed facts and proposed
investigation distinct; nothing in the briefing changes store data.
