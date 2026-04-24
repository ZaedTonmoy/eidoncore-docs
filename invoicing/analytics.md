---
title: "Analytics & Branding"
description: "Customize invoice appearance, track financial metrics, and view the invoice timeline."
---

## Invoice Branding

Invoices are automatically branded with your agency's settings:

- **Invoice logo** — Custom logo or your main logo
- **Accent color** — Applied to the "INVOICE" label and total amount
- **Footer note** — Legal footer text
- **Bank details** — Bank transfer payment details
- **Payment instructions** — How to pay
- **Signature** — Optional signature image
- **Business registration** — Registration or tax ID display

### Print Settings

| Setting | Options |
|---------|---------| 
| **Show Logo** | Yes / No |
| **Show Payment History** | Yes / No |
| **Show Bank Details** | Yes / No |
| **Show Notes** | Yes / No |
| **Paper Size** | A4 or Letter |

> **See also:** [Settings](../settings/branding#agency-branding) for configuring invoice branding

---

## Invoice Timeline

Every invoice has a unified **timeline** that shows all activity in chronological order:

- Audit events (created, edited, sent, voided)
- Payment recordings and deletions
- Refund events
- Credit note issued and applied events
- Reminder sends (with delivery status)

View the timeline from the invoice detail page to see a complete history of the invoice's lifecycle.

---

## Visibility Controls

Control which team members can see specific invoices. By default, invoices are visible to all authorized users. Add visibility restrictions to limit access to sensitive invoices.

---

## Comments

Leave comments on invoices for team discussion:

- **Internal comments** — only visible to agency staff, useful for discussing pricing or payment issues
- **Standard comments** — visible to anyone with access to the invoice
- Supports threaded replies, @mentions, and emoji reactions
- Comments appear in the invoice detail view

---

## Finance Analytics Dashboard

The **Analytics** tab on the Invoices page provides a comprehensive financial overview.

<Tabs>
<Tab title="Agency Staff" icon="briefcase">

| Metric | What It Shows |
|--------|--------------|
| **Outstanding Amount** | Total unpaid across all invoices |
| **Overdue Amount** | Unpaid invoices past their due date |
| **This Month's Revenue** | Payments received this month |
| **Total Revenue** | All-time revenue from paid invoices |
| **Collection Rate** | Percentage of issued invoices that were collected |
| **Average Days to Payment** | Mean time from issue to payment |
| **Average Days Late** | Mean time past due for late payers |
| **MRR / ARR** | Monthly and yearly recurring revenue from recurring templates |
| **Aging Buckets** | Overdue amounts grouped: 0-30, 31-60, 61-90, 90+ days |
| **Revenue by Client** | Top 5 clients by revenue |
| **Revenue Forecast** | Expected revenue for next 30/60/90 days |
| **Status Counts** | Breakdown by invoice status |

</Tab>
<Tab title="Client Portal" icon="building">

Organization Owners see a simplified 4-card analytics view:

| Card | What It Shows |
|------|--------------|
| **Outstanding Balance** | Current unpaid invoice total |
| **Overdue** | Overdue invoice amount |
| **Total Paid** | All-time payment total |
| **Avg Days to Pay** | Average time to payment |

</Tab>
</Tabs>

<Callout kind="info">
The full analytics dashboard is only visible to agency staff with financial access. Project Managers and Team Members see a restricted view without dollar amounts.
</Callout>

### Sidebar Badge

An **unpaid invoice count badge** appears on the Invoices sidebar link for client portal users, showing the number of outstanding invoices (Sent, Viewed, Partially Paid, or Overdue).

<Callout kind="tip">
Use the aging buckets to proactively follow up on overdue invoices before they hit the 90+ day mark — where collection rates drop significantly.
</Callout>

---

## Related

<Columns cols="2">
<Card title="Reports" icon="bar-chart-2" href="../reports">
Additional revenue, client, and project analytics.
</Card>
<Card title="Clients" icon="users" href="../clients/overview">
Per-client financial tracking and billing history.
</Card>
</Columns>
