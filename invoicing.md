# Invoicing & Billing

Create professional invoices, track payments, set up recurring billing, issue credit notes, and monitor your agency's financial health.

---

## Creating an Invoice

Navigate to **Invoices** in the sidebar and click **"New Invoice"**.

### Invoice Fields

| Field | Description |
|-------|-------------|
| **Invoice Number** | Auto-generated sequentially (e.g., INV-00001) |
| **Client** | The client organization being billed |
| **Project** | Optionally link to a project |
| **Issue Date** | Date the invoice is created (defaults to today) |
| **Due Date** | Payment deadline |
| **Payment Terms** | Terms text (e.g., "Net 30") |
| **Currency** | Invoice currency (defaults to your agency's default) |
| **Notes** | Client-facing notes |
| **Internal Notes** | Agency-only notes (not visible to clients) |

### Line Items

Each invoice contains line items with:

| Field | Description |
|-------|-------------|
| **Type** | One-Time, Recurring, Usage-Based, Discount, Tax, or Credit |
| **Name & Description** | What you're billing for |
| **Quantity** | Number of units |
| **Unit Price** | Price per unit |
| **Discount** | Per-line discount (percentage or fixed amount) |
| **Tax Rate** | Per-line tax percentage |
| **Service Link** | Optionally link to a service from your catalog |

Line totals are calculated automatically: `(Quantity × Unit Price − Discount) × (1 + Tax Rate)`.

Invoice-level discounts and tax rates can also be applied to the entire invoice.

---

## Invoice Statuses

Invoices flow through the following lifecycle:

```
Draft → Scheduled → Sent → Viewed → Partially Paid → Paid
                     │                                  ↑
                     └─→ Overdue ──→ Bad Debt           │
                                                        │
                              Refunded ←────────────────┘
                     └─→ Void
```

| Status | Meaning |
|--------|---------|
| **Draft** | Still being prepared — only drafts can be deleted |
| **Scheduled** | Set to send automatically on a future date |
| **Sent** | Delivered to the client |
| **Viewed** | The client has opened the invoice |
| **Partially Paid** | Some payment has been received |
| **Paid** | Fully paid |
| **Overdue** | Past due date without full payment |
| **Bad Debt** | Marked as uncollectable |
| **Void** | Cancelled / invalidated |
| **Refunded** | Payment has been fully refunded |

---

## Sending Invoices

Once an invoice is ready, click **"Send"** to deliver it to the client's contacts. You can also:

- **Schedule** an invoice for future delivery
- **Share via public link** — generate a shareable URL for clients to view the invoice without logging in

When an invoice is sent, all contacts linked to the client organization receive a notification.

---

## Recording Payments

Record payments on any sent invoice:

| Field | Description |
|-------|-------------|
| **Amount** | Payment amount |
| **Method** | Manual, Bank Transfer, Stripe, PayPal, Cash, Check, or Other |
| **Reference** | External reference (check number, wire reference, etc.) |
| **Date** | When the payment was received |
| **Notes** | Payment notes |

When a payment is recorded:
- If the paid amount equals or exceeds the total → status changes to **Paid**
- If partial payment → status changes to **Partially Paid**
- Client contacts are notified automatically

---

## Invoice Reminders

Set up automated payment reminders:

| Reminder Type | When It Sends |
|--------------|--------------|
| **Before Due** | X days before the due date |
| **On Due Date** | The day payment is due |
| **After Due** | X days after the due date (for overdue invoices) |

Each reminder can have a custom message. Delivery is tracked so you can see when reminders were sent.

Additionally, the platform automatically sends a **payment reminder** to client contacts when an invoice is due within 3 days.

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

## Credit Notes

Issue credit notes against invoices when refunds or adjustments are needed:

- Credit notes are numbered automatically (e.g., CN-00001)
- Each credit note tracks a **remaining balance**
- Apply credit notes as payment to any invoice — the credit's balance is reduced and the invoice's paid amount is increased
- Credits can be applied in full or partially

---

## Refunds

Issue refunds against specific payments or entire invoices:

1. The refund amount is validated against the paid amount
2. The invoice's paid amount is decreased
3. If fully refunded, the invoice status changes to **Refunded**
4. Stripe refunds are processed automatically for online payments

Refund statuses: Pending → Processed / Failed.

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

> **See also:** [Settings](./settings.md#agency-branding) for configuring invoice branding

---

## Visibility Controls

Control which team members can see specific invoices. By default, invoices are visible to all authorized users. Add visibility restrictions to limit access to sensitive invoices.

---

## Finance Analytics Dashboard

The invoice analytics view provides a comprehensive financial overview:

| Metric | What It Shows |
|--------|--------------|
| **Outstanding Amount** | Total unpaid across all invoices |
| **Overdue Amount** | Unpaid invoices past their due date |
| **This Month's Revenue** | Payments received this month |
| **Collection Rate** | Percentage of issued invoices that were collected |
| **Average Days to Payment** | Mean time from issue to payment |
| **Average Days Late** | Mean time past due for late payers |
| **MRR / ARR** | Monthly and yearly recurring revenue from recurring templates |
| **Aging Buckets** | Overdue amounts grouped: 0-30, 31-60, 61-90, 90+ days |
| **Revenue by Client** | Top 5 clients by revenue |
| **Revenue Forecast** | Expected revenue for next 30/60/90 days |
| **Status Counts** | Breakdown by invoice status |

> **See also:** [Reports](./reports.md) for additional revenue and client reports · [Clients](./clients.md) for per-client financial tracking

---

## Duplicate & Delete

- **Duplicate** any invoice to create a copy with a new invoice number
- **Delete** is only available for Draft invoices — once sent, invoices must be voided instead

---

## Permissions

| Permission | What It Allows |
|-----------|---------------|
| **View Invoices** | List, view details, see statistics and analytics |
| **Create Invoices** | Create new invoices and duplicates |
| **Edit Invoices** | Update invoice details and line items |
| **Send Invoices** | Send invoices to clients |
| **Void Invoices** | Void an invoice |
| **Delete Invoices** | Delete draft invoices |
| **Record Payments** | Record and delete payments, apply credit notes |
| **Mark Bad Debt** | Mark invoices as uncollectable |
| **Issue Refunds** | Issue refunds and create credit notes |

> **See also:** [Team](./team.md) for configuring role permissions
