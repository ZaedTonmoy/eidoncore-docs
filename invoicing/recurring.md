---
title: "Recurring Invoices"
description: "Automate billing with recurring invoice templates and usage-based time tracking."
---

## Recurring Invoices

Set up automatic invoice generation on a schedule:

| Setting | Description |
|---------|-------------|
| **Name** | Template name for reference |
| **Frequency** | Weekly, Monthly, Quarterly, or Yearly |
| **Start Date** | When to begin generating invoices |
| **End Date** | When to stop (optional) |
| **Lead Days** | Generate the invoice X days before it's due (default: 5) |
| **Auto-Generate** | Automatically create the invoice |
| **Auto-Send** | Automatically send after generation |
| **Auto-Charge** | Automatically charge via Stripe |
| **Template Items** | Pre-configured line items for each generated invoice |

Recurring templates can be activated, paused, or deleted at any time. Force-generate an invoice from any template at any time.

---

## Usage Breakdown (Time-Based Invoices)

For invoices linked to hourly or usage-based services, the invoice detail page shows a **per-entry breakdown** table:

| Column | What It Shows |
|--------|--------------|
| **Date** | When the time was logged |
| **Task** | Which task the entry relates to (linked) |
| **Regular Minutes** | Time within the included hours balance |
| **Overtime Minutes** | Time beyond the included hours |
| **Regular Rate** | The regular hourly rate at the time of logging |
| **Overtime Rate** | The overtime rate at the time of logging |

Rates are **snapshotted** when time is logged — the invoice reflects the exact rate that applied at that moment, not the current service rate. Written-off entries (agency comp) are excluded from the breakdown.

---
