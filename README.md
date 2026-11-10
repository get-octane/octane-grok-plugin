# Octane for Grok Bot and Cursor

Review a convenience store's daily performance, important inventory exceptions,
invoice blockers and supported cost increases with evidence from your Octane
account. Octane is a product of Ryw, Inc. This plugin is read-only: it cannot
approve invoices, change prices or inventory, place orders, retry processing, or
send commands to a register.

## What you can ask

| Skill | Example request |
| --- | --- |
| `daily-store-review` | “Review my store for October 20, 2026. What should I investigate first?” |
| `inventory-attention-review` | “Which inventory exceptions need attention for October 14–20, 2026?” |
| `invoice-review-preparation` | “Prepare this store's invoice review for October 14–20, 2026.” |

Each review starts by identifying the connected account and its authorized stores.
The agent asks you to choose when several stores match, and asks for a period when
you give none. A daily review uses the store's operating days; invoices use their
printed invoice dates and list undated exceptions separately. Inventory compares
the requested sales window with current on-hand, not historical stock.

Findings keep their dates, observation time, coverage limits and links to the
supporting records in Octane. Missing data is reported as missing, not as zero,
and an empty page is not an all-clear. Suggestions are not approvals or completed
actions; follow the evidence links to review the records in Octane itself.

## Connect your account

You need an existing Octane account with access to the store you want to review.
In Grok Bot, add Octane from **Connect apps**; in Cursor, install it from the
marketplace. Then sign in with your usual Octane sign-in when prompted, choosing
the intended workspace. Your current membership and store permissions decide what
the agent can read; installing the plugin grants no store access. A team admin's
connector policy can block or allow Octane for members.

## What the plugin runs and sends

The plugin contains three skills, their shared review rules, and one remote
connection: `https://store.getoctane.ai/mcp`, the Octane service operated by
Ryw, Inc. It runs no local programs, hooks, scripts or background tasks, and the
plugin itself sends data nowhere else.

Sign-in uses OAuth with your Octane account through Octane's sign-in provider,
Clerk, as a public client with PKCE; the plugin stores no password, token or key.
When you ask for a review, the agent calls four read-only Octane tools with a
store, a date range and paging values:

| Tool | Returns |
| --- | --- |
| `get_account_context` | The connected account, workspace and readable stores |
| `get_store_performance` | Sales, tax, fuel gallons and receipt counts for the period, with the days that have data |
| `get_inventory_attention` | At-risk, warning or unknown stock among top-selling items |
| `get_invoice_attention` | Invoice review exceptions and supported cost increases |

Results include store names and identifiers, business figures, item and invoice
references, and evidence links. They exclude passwords, OAuth credentials, raw
invoice-recognition text and personal contact details. Results stay under your
Grok Bot or Cursor account's own privacy and retention settings. Octane's logs
record which tool ran, its outcome and duration, but not the request values or the
results.

## Connection and data problems

Reconnect Octane from your app's connector settings if authorization expires or
the agent asks you to sign in again. For a missing store or an access denial, ask
your Octane workspace owner; the agent will not substitute another store or
workspace. If a connection or data domain is unavailable, the review says so
instead of inventing results. You can disconnect at any time and manage access in
Octane.

## Support, privacy, terms and license

- [Octane](https://getoctane.ai)
- [Support](https://getoctane.ai/support): agent@getoctane.ai
- [Privacy policy](https://getoctane.ai/privacy)
- [Terms](https://getoctane.ai/terms)

This package is licensed under the Apache License 2.0 (`LICENSE`). The Octane name
and logo are trademarks of Ryw, Inc. and are not licensed (`NOTICE`). Your Octane
service agreement governs the Octane service, and the package grants no rights to
customer data.
