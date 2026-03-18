---
title: "Payments & Credits"
description: "Record payments, set up reminders, issue credit notes, and process refunds."
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

## Credit Notes

Issue credit notes against invoices when refunds or adjustments are needed:

- Credit notes are numbered automatically (e.g., CN-00001)
- Each credit note tracks a **remaining balance**
- Apply credit notes as payment to any invoice — the credit's balance is reduced and the invoice's paid amount is increased
- Credits can be applied in full or partially

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
