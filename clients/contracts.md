---
title: "Contracts & Services"
description: "Track contract renewals, manage client service subscriptions, monitor time entries, and generate invoices."
---

## Contract & Renewal Tracking

For active clients, track contract details:

| Field | Description |
|-------|-------------|
| **Contract Start/End Date** | Active contract period |
| **Renewal Type** | Auto-renew, manual, etc. |
| **Notice Period** | Days before contract end to flag for renewal |
| **SLA Tier** | Service level agreement tier |

When a contract is approaching expiry (within the notice period), agency owners are notified.

---

## Client Services

View and manage services assigned to each client under the **Services** tab. This shows:

- Active, paused, and cancelled service assignments
- Remaining hours and credits
- Billing period tracking

> **See also:** [Services](../services/overview) for managing your service catalog · [Invoicing](../invoicing/overview) for billing clients

---

## Time & Billing

The client detail page includes a **Time & Billing** tab that aggregates all time entries across every project and ticket belonging to the client organization. This provides a centralized view for billing teams to review tracked time and generate invoices.

### Stats Bar

Four metrics displayed at the top of the tab:

| Metric | What It Shows |
|--------|--------------|
| **Total Hours** | All tracked time across the organization |
| **Billable Hours** | Time marked as billable |
| **Billed Hours** | Time already included on an invoice |
| **Unbilled Hours** | Billable time not yet invoiced |

### Filters

- **Billable Status** — All Entries, Billable Only, or Non-Billable
- **Project/Ticket** — Filter by specific project or ticket

### Time Entry Table

Each entry shows:

| Column | What It Shows |
|--------|--------------| 
| **Source** | Project name (bold) + task or ticket reference |
| **Who** | Team member who tracked the time |
| **Duration** | Time spent |
| **Description** | Entry description |
| **Billable** | Whether the entry is billable |
| **Invoice Status** | Lock icon if already linked to an invoice |

Locked entries (linked to an existing invoice) cannot be re-billed.

### Generate Invoice

Click the **"Generate Invoice"** button (shows an unbilled entry count badge) to create a DRAFT invoice from time entries:

<Steps>
<Step title="Select date range" icon="calendar">
Choose a preset (Last Month, This Month) or set a custom date range.
</Step>
<Step title="Choose grouping" icon="layers">
Select how to organize line items on the invoice.
</Step>
<Step title="Set hourly rate" icon="dollar-sign">
Enter the hourly rate to apply to all entries.
</Step>
<Step title="Review preview" icon="eye">
See a live preview showing entry count, line items, total hours, and estimated total — updates dynamically as you change settings.
</Step>
<Step title="Generate draft" icon="file-plus">
Click "Generate Draft" to create the invoice and redirect to the invoice detail page.
</Step>
</Steps>

#### Grouping Modes

| Mode | How It Groups |
|------|--------------|
| **Per Project** | Each project becomes its own line item |
| **Per Task & Ticket** | Each task or ticket becomes a line item |
| **Per Entry** | Each individual time entry gets its own line |
| **Per Team Member** | Entries grouped by the person who tracked them |
| **Single Line** | All entries combined into one line item |

<Callout kind="info">
Project-level time tracking and per-project invoice generation is also available on the **Project Detail → Budget** tab. Use the organization-level view here for consolidated cross-project billing.
</Callout>

> **See also:** [Tasks](../tasks/collaboration#time-tracking) for task-level time tracking · [Tickets](../tickets/features#time-tracking--billing) for ticket-level time tracking · [Projects](../projects#time-tracking) for project-level time tracking · [Reports](../reports) for time tracking reports

---

## Organization Announcements

The client Settings tab includes a **Portal Announcements** section for creating announcements visible only to this specific client's portal users:

- Create announcements with a title, message, and optional pin
- Organization-specific announcements display alongside global announcements in the client portal
- Pinned announcements always appear first

> **See also:** [Settings](../settings/branding) for global portal announcements · [Client Portal](../client-portal/overview) for the portal experience
