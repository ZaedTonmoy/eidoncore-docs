---
title: "Proposal Basics"
description: "Create professional proposals with a block-based builder, add line items, and manage proposal settings."
---

Create professional, branded proposals and deliver them to clients for review, acceptance, or negotiation. The proposal builder supports rich content blocks, line item pricing, client signatures, version tracking, and automatic conversion to projects and invoices.

<Columns cols="2">
<Card title="Delivery & Tracking" icon="send" href="/proposals/delivery">
Send proposals, track views, and monitor engagement analytics
</Card>
<Card title="Conversion & Billing" icon="refresh-cw" href="/proposals/conversion">
Turn accepted proposals into projects and invoices automatically
</Card>
</Columns>

---

## Creating a Proposal

Navigate to **Proposals** in the sidebar and click **"New Proposal"** (or press `N`).

### Proposal Details

| Field | Description |
|-------|-------------|
| **Title** | A descriptive proposal title |
| **Client** | The client organization this proposal is for |
| **Template** | Optionally start from a saved proposal template |
| **Currency** | Currency for pricing (defaults to USD) |
| **Expiry** | Number of days the proposal remains valid (default: 30 days) |

<Callout kind="tip">
Use **proposal templates** to save time on frequently-sent proposals. Templates preserve the full block structure, line items, and settings so you can reuse them.
</Callout>

---

## Proposal Builder

The proposal builder uses a **block-based editor** — add, reorder, and customize content blocks to build your proposal. Changes are **auto-saved** with a debounce delay, so you never lose work.

### Content Block Types

| Block | Purpose |
|-------|---------| 
| **Heading** | Section headings (H1–H3) |
| **Text** | Rich text paragraphs |
| **Image** | Uploaded images with captions |
| **Divider** | Visual separator line |
| **Spacer** | Vertical spacing |
| **Pricing Table** | Line item pricing (qty, unit price, discounts, tax) |
| **Total Summary** | Subtotal, discount, tax, and grand total |
| **Scope of Work** | Rich text scope description |
| **Timeline** | Project timeline and milestones |
| **Terms** | Terms and conditions |
| **Signature** | Client signature capture area |
| **Deliverables** | Deliverables checklist |
| **Testimonial** | Client testimonial quote |
| **Case Study** | Past project showcase |
| **Attachments** | File attachments |
| **Video** | Embedded video (YouTube, Vimeo, Loom) |
| **Team Bios** | Team member cards with bios |
| **Pricing Configurator** | Interactive pricing option selector |

---

## Line Items & Pricing

The **Line Items** tab lets you manage individual pricing entries for your proposal.

### Adding Line Items

You can add line items in two ways:

- **Manual items** — Enter a custom name, quantity, unit price, and optional discount or tax
- **From Service Catalog** — Click **"Add from catalog"** to pull in services with their configured pricing. Billing type badges show whether an item is recurring (/mo, /yr), hourly (/hr), or one-time

### Line Item Features

| Feature | Description |
|---------|-------------|
| **Quantity & Unit Price** | Set the quantity and per-unit price |
| **Discounts** | Per-item percentage or fixed discount |
| **Tax** | Per-item or proposal-level tax rate |
| **Optional Items** | Mark items as optional — clients choose whether to include them during acceptance |
| **Billing Type Badges** | Visual indicators: **RECURRING**, **SERVICE**, **ONE-TIME** |

### Pricing Summary

The proposal automatically calculates:

- **Subtotal** — sum of all non-optional accepted items
- **Discount** — document-level percentage or fixed discount
- **Tax** — applied to subtotal after discount
- **Grand Total** — final amount

<Callout kind="info">
When a client accepts a proposal with optional items, the totals are **recalculated** based on which optional items they selected.
</Callout>

---

## Proposal Templates

Save any proposal as a **template** for reuse. Templates preserve:

- All content blocks
- Line item structure
- Proposal settings

Agency Owners and Admins can manage templates. When creating a new proposal, you can start from a template and customize it for the specific client.

---

## Proposal Views

The **Proposals** list page supports two views:

- **Table view** — sortable list with status filter tabs
- **Card view** — visual cards with proposal summaries

Your view preference is saved automatically.

---

## Download & Print

| Action | Description |
|--------|-------------|
| **Download PDF** | Download the proposal as a PDF document |
| **Print** | Opens a clean print-ready view of the proposal |
| **Copy Share Link** | Copy the public share URL (available after sending) |

Proposals sent via email include the PDF as an attachment.

---

## Permissions

| Permission | What It Allows | Default Roles |
|-----------|---------------|---------------|
| **View Proposals** | See proposals (own or all) | Owner, Admin, PM (own only) |
| **Create** | Create new proposals | Owner, Admin, PM |
| **Edit** | Edit proposal content and settings | Owner, Admin, PM (own only) |
| **Send** | Send proposals to clients, approve reviews | Owner, Admin |
| **Delete** | Delete proposals | Owner, Admin |
| **Convert** | Convert accepted proposals to projects/invoices | Owner, Admin |
| **View All** | View all proposals regardless of ownership | Owner, Admin |
| **Manage Templates** | Create, edit, and delete templates | Owner, Admin |

<Callout kind="info">
Proposals is a **Pro plan** feature. Free plan users will see a lock icon on the sidebar item with an upgrade prompt.
</Callout>

> **See also:** [Delivery & Tracking](./proposals/delivery) for sending, analytics, and client actions · [Conversion & Billing](./proposals/conversion) for converting to projects and invoices
