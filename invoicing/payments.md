---
title: "Payments & Credits"
description: "Record payments, set up reminders, issue credit notes, and process refunds."
---

## Recording Payments

Record payments on any sent invoice:

| Field | Description |
|-------|-------------|
| **Amount** | Payment amount |
| **Method** | Manual, Bank Transfer, Stripe, PayPal, Cash, Wise, or Other |
| **Reference** | External reference (check number, wire reference, etc.) |
| **Date** | When the payment was received |
| **Notes** | Payment notes |

When a payment is recorded:
- If the paid amount equals or exceeds the total → status changes to **Paid**
- If partial payment → status changes to **Partially Paid**
- Client contacts are notified automatically

### Stripe Payments

Clients can pay invoices online via Stripe through the invoice's public share link or from their portal. For invoices linked to proposals with recurring services, the payment method is saved automatically for future auto-renewal.

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

## Credit Notes

Issue credit notes against invoices when refunds or adjustments are needed:

- Credit notes are numbered automatically (e.g., CN-00001)
- Each credit note tracks a **remaining balance**
- Apply credit notes as payment to any invoice — the credit's balance is reduced and the invoice's paid amount is increased
- Credits can be applied in full or partially

### Issuing a Credit Note

On the invoice detail page, click **"Credit Note"** to issue a credit against the invoice. Enter the credit amount and an optional reason.

### Applying a Credit

Click **"Apply Credit"** on any invoice with an outstanding balance to apply an existing credit note's balance as payment.

<Callout kind="info">
Credit notes are available on **Pro** plans and above.
</Callout>

---

## Refunds

Issue refunds against specific payments or entire invoices:

<Steps>
<Step title="Validate refund amount" icon="shield-check">
The refund amount is validated against the paid amount
</Step>
<Step title="Decrease paid amount" icon="minus-circle">
The invoice's paid amount is decreased
</Step>
<Step title="Update invoice status" icon="refresh-cw">
If fully refunded, the invoice status changes to **Refunded**
</Step>
<Step title="Process Stripe refund" icon="credit-card">
Stripe refunds are processed automatically for online payments
</Step>
</Steps>

Refund statuses: Pending → Processed / Failed.

---

## Action Bar

The invoice detail page shows action buttons based on your role and the invoice's current status:

| Action | When Available | Required Permission |
|--------|---------------|:-------------------:|
| **Edit** | Not Void or Bad Debt | Edit Invoices |
| **Send** | Draft or Scheduled | Send Invoices |
| **Record Payment** | Unpaid invoices | Record Payments |
| **Refund** | Paid or Partially Paid | Issue Refunds |
| **Credit Note** | Non-terminal statuses | Issue Refunds or Record Payments |
| **Apply Credit** | When balance is due | Record Payments |
| **Bad Debt** | Non-terminal, unpaid | Mark Bad Debt |
| **Void** | Non-terminal, not paid | Void Invoices |
| **Delete** | Draft only | Delete Invoices |

<Callout kind="info">
Buttons that you don't have permission for are hidden — you'll never see a button that would fail when clicked.
</Callout>

---
