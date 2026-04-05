---
title: "Portal & Client Access"
description: "Learn how clients interact with the ticketing system — submitting tickets, tracking progress, replying, rating satisfaction, and role-based visibility in the client portal."
---

# Portal & Client Access

The ticketing system is fully integrated into the client portal, giving your clients a professional support experience under your brand.

## Submitting tickets

Clients can submit support tickets from three entry points:

<Columns cols="3">
  <Card title="Tickets Page" href="#tickets-page" icon="list" horizontal={false}>
    Dedicated page in the portal sidebar for viewing and submitting tickets.
  </Card>

  <Card title="Need Help? Button" href="#help-button" icon="help-circle" horizontal={false}>
    Floating action button visible on every portal page for quick access.
  </Card>

  <Card title="Report an Issue" href="#report-issue" icon="alert-circle" horizontal={false}>
    Button on project detail pages that pre-fills the project context on the ticket.
  </Card>
</Columns>

### Submission form

The ticket submission form includes:

| Field | Required | Notes |
|-------|----------|-------|
| Subject | ✅ | Short summary of the issue |
| Description | ✅ | Rich text with file upload support |
| Type | ✅ | Bug, Question, Change Request, Feature Request, Support, Billing, Other |
| Priority | ✅ | Default: Normal |
| Project | ❌ | Optional project context |

<Callout kind="tip">
  On Pro plans with intake forms enabled, ticket types can be linked to structured intake forms — showing category-specific fields like "Steps to Reproduce" for bug reports.
</Callout>

## Role-based visibility

Different organization roles see different sets of tickets:

| Role | What They See |
|------|--------------|
| **Org Owner** | All tickets for the organization |
| **Org Admin** | All tickets for the organization |
| **Org Member** | Only tickets they created or are watching |

<Callout kind="info">
  The Org Member visibility scoping ensures that junior team members (content managers, QA testers) can see and respond to their own tickets, but cannot browse the full organization's support history. Add them as **watchers** on specific tickets to grant access.
</Callout>

## Viewing tickets

The portal ticket list shows:

| Column | Description |
|--------|-------------|
| Ticket # | TKT-001 format, clickable |
| Subject | Ticket title |
| Status | Color-coded badge |
| Priority | Signal icon |
| Last Reply | Relative timestamp |
| My Rating | Stars (if resolved and rated) |

## Replying to tickets

Clients can reply to tickets from the ticket detail view:

- **Public replies** are visible to both the client and the agency team
- **Internal notes** from the agency team are **never visible** to clients
- Replies support **rich text** and **file attachments**

### Who can reply

| Role | Can Reply | Condition |
|------|:---------:|-----------|
| Org Owner | ✅ | On any organization ticket |
| Org Admin | ✅ | On any organization ticket |
| Org Member | ✅ | Only on tickets they created or are watching |

<Callout kind="alert">
  Internal notes added by agency team members are completely hidden from all organization roles. The system enforces this server-side — not just in the UI — so notes cannot be exposed via API inspection.
</Callout>

## Rating satisfaction (CSAT)

When a ticket is resolved, clients receive a notification with a CSAT rating prompt:

1. Open the resolved ticket in the portal
2. Click the **star rating** (1–5)
3. Optionally add a **text comment** with feedback
4. Submit — the rating is recorded with the rater's identity and timestamp

CSAT ratings can also be submitted from the resolution notification email link.

| Role | Can Rate | Condition |
|------|:--------:|-----------|
| Org Owner | ✅ | Any resolved ticket |
| Org Admin | ✅ | Any resolved ticket |
| Org Member | ✅ | Only tickets they created or are watching |

## Reopening tickets

If a resolved issue resurfaces, Org Owner and Org Admin can **reopen** the ticket. This moves it back to an open status and notifies the assigned agent.

<Callout kind="info">
  Org Members cannot reopen tickets. They should create a new ticket or ask their Org Owner/Admin to reopen.
</Callout>

## Managing watchers

Org Owner and Org Admin can add or remove **watchers** (CC) on their organization's tickets. This is useful for:

- Keeping project managers informed on support issues
- Allowing an Org Member to follow a specific ticket without full visibility

## Portal navigation

The **Tickets** sidebar item appears for all organization roles (Org Owner, Org Admin, Org Member) when the agency has ticketing enabled.

<Callout kind="info">
  The agency can hide the Tickets nav item via the `portalHiddenNavItems` branding setting — same pattern as hiding Invoices, Projects, or other portal sections.
</Callout>

## Notifications for clients

| Event | Notification | Recipients |
|-------|-------------|-----------|
| Agency replies | `TICKET_REPLY_FROM_AGENT` | Reporter + watchers |
| Ticket resolved | `TICKET_RESOLVED` | Reporter (with CSAT prompt) |
| Ticket merged | Merge notification | Source ticket's reporter |

All ticket notification emails use the agency's branded email template (`sendBrandedEmail()`), respecting custom colors, logo, and white-label settings.
