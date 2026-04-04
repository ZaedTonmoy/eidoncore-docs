---
title: "Conversion & Billing"
description: "Convert accepted proposals into projects, invoices, or both. Configure auto-conversion, deposits, and service-linked billing."
---

Once a proposal is accepted, convert it into actionable work — manually or automatically. This page covers all conversion options, deposit handling, and service-linked billing workflows.

---

## Conversion Options

| Conversion | What It Creates |
|-----------|----------------|
| **To Project** | A new project with the client organization linked |
| **To Invoice** | A draft invoice with the line items from the proposal |
| **To Both** | Both a project and an invoice simultaneously |
| **Multi-Invoice** | Multiple milestone-based invoices from a payment schedule |

### Manual Conversion

After a proposal is accepted, click the **"Convert"** button and choose your conversion type. The system pre-fills details from the proposal:

<Steps>
<Step title="Select conversion type" icon="settings">
Choose Project, Invoice, Both, or Multi-Invoice.
</Step>
<Step title="Review details" icon="eye">
Confirm the pre-populated project name, invoice line items, or payment schedule.
</Step>
<Step title="Confirm" icon="check-circle">
The system creates the project, invoice, or both and links them to the proposal.
</Step>
</Steps>

---

## Auto-Conversion

You can configure proposals to **automatically convert** when the client accepts:

| Setting | Behavior |
|---------|----------|
| **Manual** | No automation — you convert manually |
| **Auto → Project** | Automatically creates a project on acceptance |
| **Auto → Invoice** | Automatically creates an invoice and redirects the client to pay via Stripe |
| **Auto → Both** | Creates both a project and invoice, with Stripe checkout redirect |

<Callout kind="info">
When auto-conversion is set to create an invoice, the client is **redirected to Stripe Checkout** immediately after accepting. If the client doesn't complete payment, the invoice remains as a draft and can be sent manually later.
</Callout>

---

## Service-Linked Line Items

If you add line items from your **Service Catalog**, converting the proposal to an invoice will automatically:

- Create invoice line items for each service
- **Provision active subscriptions** for recurring services (e.g., monthly hosting, annual licenses)
- Set up automatic billing for recurring items

This means a single proposal can combine one-time project fees with ongoing service subscriptions.

<Callout kind="tip">
Use **pricing configurator** blocks in the proposal builder to let clients choose between service packages. The selected package drives the line items during conversion.
</Callout>

---

## Deposits

Enable **deposit payments** on a proposal to split the payment:

- **Percentage-based** — e.g., 50% upfront, 50% on completion
- **Fixed amount** — e.g., $1,000 deposit, remainder on completion

When converted, the system creates two invoices: one for the deposit (due immediately) and one for the remainder.

### Deposit Flow

<Steps>
<Step title="Enable deposit" icon="sliders">
In proposal settings, toggle **"Require Deposit"** and choose percentage or fixed amount.
</Step>
<Step title="Client accepts" icon="pen-tool">
Client accepts and signs the proposal.
</Step>
<Step title="Invoices created" icon="file-text">
Two invoices are generated — deposit invoice (due now) and balance invoice (due on completion).
</Step>
<Step title="Payment" icon="credit-card">
If auto-conversion is enabled, the client is directed to pay the deposit invoice via Stripe immediately.
</Step>
</Steps>

---

## Multi-Invoice (Milestone Billing)

For large projects, create a **payment schedule** with multiple milestone invoices:

| Field | Description |
|-------|-------------|
| **Milestone Name** | Description of the deliverable or phase |
| **Amount** | Dollar amount or percentage of total |
| **Due Date** | When this milestone payment is due |

Each milestone creates a separate invoice linked to the proposal. Progress through milestones can be tracked from the proposal detail page.

---

## Linked Records

After conversion, the proposal maintains links to all created records:

- **Linked Project** — view and manage the project from the proposal detail page
- **Linked Invoice(s)** — track payment status of all generated invoices
- **Linked Subscriptions** — monitor active subscriptions from service-linked items

These connections provide a full audit trail from initial proposal through project delivery and final payment.

> **See also:** [Proposal Basics](./proposals/overview) for building proposals · [Delivery & Tracking](./proposals/delivery) for sending and client actions · [Projects](./projects) for project management · [Invoicing](./invoicing/overview) for invoice details · [Offerings](./services/overview) for service-linked proposals
