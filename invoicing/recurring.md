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
| **Auto-Charge** | Automatically charge via Stripe (requires saved payment method) |
| **Partial Payment** | Allow partial payments on generated invoices (inherits to each invoice) |
| **Template Items** | Pre-configured line items for each generated invoice |

### Managing Recurring Templates

The **Recurring** tab on the Invoices page provides a management interface:

| Column | What It Shows |
|--------|--------------|
| **Invoice** | Template name (links to detail page) |
| **Client** | Client organization |
| **Status** | Active / Paused toggle |
| **Frequency** | Color-coded pill (Weekly, Monthly, Quarterly, Yearly) |
| **Next Due** | Next generation date (highlighted if overdue) |
| **Generated** | Number of invoices generated from this template |
| **Created By** | Who created the template |

### Template Detail Page

Each recurring template has a detail page showing:

- Template metadata and automation settings (auto-generate, auto-send, auto-charge indicators)
- Line items table with totals
- Generation history sidebar showing the last 20 generated invoices
- Actions: Toggle Active/Pause, Generate Now, Delete

Recurring templates can be activated, paused, or deleted at any time. Force-generate an invoice from any template at any time.

<Callout kind="info">
The Recurring tab is only visible to agency staff — client portal users do not see it.
</Callout>

---

## MRR & ARR

Monthly Recurring Revenue (MRR) and Annual Recurring Revenue (ARR) are calculated from active recurring templates using frequency multipliers:

| Frequency | MRR Multiplier |
|-----------|:--------------:|
| Weekly | × 4.33 |
| Monthly | × 1 |
| Quarterly | × 0.33 |
| Yearly | × 0.083 |

MRR and ARR appear in the invoice analytics dashboard.

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
