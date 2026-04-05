---
title: "Advanced Features"
description: "Explore advanced ticketing features — SLA tracking, CSAT ratings, canned templates, ticket merging, auto-assignment, custom statuses, and automation integration."
---

# Advanced Features

Beyond core CRUD, the ticketing system offers powerful features for agencies that handle high-volume client support.

## SLA tracking

Service Level Agreements define your response and resolution commitments per priority level.

### How SLA computation works

<Callout kind="alert">
  Simple `resolvedAt - createdAt` math is **wrong** for SLA. If a ticket bounces between "In Progress" and "Waiting on Client" — paused for 4 days out of 5 — the actual active time is 1 day, not 5.
</Callout>

The system uses an **accumulator approach**:

1. Every status change logs the time spent in the previous status
2. If the previous status had **SLA active** (e.g., Open, In Progress), that duration is added to the accumulated active time
3. If the previous status had **SLA paused** (e.g., Waiting on Client), time is logged but **not** added to the accumulator
4. SLA breach checks compare accumulated active time against the target — not wall-clock time

### SLA breach handling

- **Warning at 80%** — `TICKET_SLA_WARNING` notification to the assigned agent and agency owner (P1 priority, bypasses email digests)
- **Breach at 100%** — `TICKET_SLA_BREACHED` notification to owner and admin; ticket flagged as breached
- **Optional escalation** — configure automation rules to auto-reassign breached tickets

### First response time

First response time = `firstRespondedAt - createdAt`. Only **public replies** by agency agents count (not internal notes).

<Callout kind="info">
  SLA tracking requires the **Pro plan** or higher. Starter plan users see an upgrade prompt.
</Callout>

## CSAT ratings

When a ticket is resolved, the client can rate their experience:

- **1–5 star rating** with optional text comment
- Prompted via the resolution notification email and in-app
- Org Owner, Org Admin, and Org Member (on their own tickets) can submit ratings
- Feeds into **Reports → Support** tab, **CRM health scoring**, and **CRM activity timeline**

<Callout kind="info">
  CSAT ratings require the **Pro plan** or higher (`ticketCsat` feature flag).
</Callout>

## Canned response templates

Save frequently used responses as reusable templates:

- **Title and content** — rich text body with categories and optional shortcut keys
- **Template management** — Owner, Admin, and PM can create, edit, and delete
- **Quick insert** — all agents can insert templates from a dropdown in the reply editor

<Callout kind="info">
  Canned templates require the **Pro plan** or higher (`ticketTemplates` feature flag).
</Callout>

## Ticket merging

When duplicate tickets arrive, merge them:

1. Open the source ticket → **"Merge into..."**
2. Search for the target ticket
3. The system re-parents replies, re-links time entries, merges watchers, adds an internal note, marks the source as merged, and notifies the reporter

<Callout kind="alert">
  Cannot merge a ticket into itself or merge an already-merged ticket. Owner, Admin, and PM only.
</Callout>

## Auto-assignment rules

Route tickets automatically (Enterprise plan):

| Method | Description |
|--------|-------------|
| **Specific** | Assign to a named team member |
| **Round-Robin** | Rotate across a pool of team members |
| **Least-Busy** | Assign to the member with fewest open tickets |

**Conditions** (optional, AND logic): ticket type, priority, client organization. First matching rule wins.

## Custom statuses

Create statuses beyond the 6 defaults with custom names, colors, sort order, SLA pause behavior, and resolution flags. Drag-and-drop reordering supported.

<Callout kind="info">
  Custom statuses require the **Pro plan** or higher (`ticketCustomStatuses` feature flag).
</Callout>

## Convert to task

When internal work is needed:

1. Click **"Convert to Task"** on the ticket
2. Select the target project
3. A linked task is created with the ticket subject and description
4. The ticket tracks the client conversation; the task tracks the work

## Convert to proposal

Turn **Feature Request** and **Change Request** tickets into proposals:

1. Click **"Convert to Proposal"**
2. A new proposal is created with pre-filled subject and description
3. Creates a natural pipeline: **support request → proposal → billable project**

## Time tracking & billing

### Manual time entry and live timer

Log time via **"Log Time"** or start a **live timer** from the ticket drawer.

### Billing pathways

| Path | When | How |
|------|------|-----|
| **Service deduction** | Ticket linked to a support retainer | Auto-deducts from `balanceHoursRemaining` |
| **Invoice generation** | No service link | Unbilled time on CRM "Support Time" tab → "Generate Support Invoice" |

<Callout kind="alert">
  Ticket time entries do **not** appear in project budget tabs. Support and project billing stay separate.
</Callout>

## Automation integration

5 triggers and 3 actions integrate with the automation engine:

**Triggers:** `ticket_created`, `ticket_status_changed`, `ticket_assigned`, `ticket_resolved`, `ticket_sla_breached`

**Actions:** `assign_ticket`, `update_ticket_status`, `create_ticket`

## Notifications

9 notification types covering the full ticket lifecycle: created, assigned, client replied, agent replied, resolved, reopened, SLA warning, SLA breached, and escalated. All support bell, email, and Slack delivery.

## Plan availability

| Feature | Starter | Pro | Enterprise |
|---------|:-------:|:---:|:----------:|
| Core ticketing | ✅ (50 max) | ✅ (unlimited) | ✅ |
| SLA tracking | ❌ | ✅ | ✅ |
| CSAT ratings | ❌ | ✅ | ✅ |
| Canned templates | ❌ | ✅ | ✅ |
| Ticket merging | ❌ | ✅ | ✅ |
| Custom statuses | ❌ | ✅ | ✅ |
| Auto-assignment | ❌ | ❌ | ✅ |
| Email-to-ticket | ❌ | ❌ | ✅ |
