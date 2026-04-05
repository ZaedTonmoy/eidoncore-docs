---
title: "Ticket Basics"
description: "Learn how the ticketing system works — create, assign, and resolve client support requests with structured workflows separate from your task system."
---

# Ticket Basics

The ticketing system provides structured support request management for your agency. Tickets represent **external requests** from your clients — bug reports, questions, feature requests, and support inquiries. They are separate from tasks, which represent internal work for your team.

## Tickets vs Tasks

Understanding the distinction between tickets and tasks is essential:

| Dimension | Tickets | Tasks |
|-----------|---------|-------|
| **Created by** | Clients (Org Owner, Admin, Member) | Agency team (Owner, Admin, PM, Team Member) |
| **Purpose** | External request management | Internal work management |
| **SLA tracking** | First response time, resolution time, breach alerts | No SLA concept |
| **Satisfaction** | CSAT ratings (1–5) from clients | No feedback loop |
| **Conversation** | Public replies + internal notes | Comments (internal/external) |
| **Billing** | Separate support billing pipeline | Project budget billing |

<Callout kind="tip">
  A ticket **can generate a linked task**. When work is needed, use "Convert to Task" to create a task in any project. The ticket tracks the conversation and resolution; the task tracks the work.
</Callout>

## Creating a ticket

Tickets can be created from multiple sources:

<Tabs>
  <Tab title="Agency Side" icon="briefcase">
    Agency team members (Owner, Admin, PM, Team Member) can create tickets **on behalf of a client**:

    1. Navigate to **Tickets** in the sidebar
    2. Click **New Ticket**
    3. Select the **client organization**
    4. Fill in subject, description, type, and priority
    5. Optionally assign a team member and link to a project or service
    6. Toggle **"Notify organization"** (default: ON) to alert the client

    <Callout kind="info">
      This is useful for capturing support requests received via phone calls, emails, or Slack messages outside the portal.
    </Callout>
  </Tab>

  <Tab title="Client Portal" icon="globe">
    Clients can submit tickets from the portal in three ways:

    - **Tickets page** — dedicated page in the portal sidebar
    - **"Need Help?" button** — floating action button on every portal page
    - **"Report an Issue"** — button on project detail pages (pre-fills the project context)

    The submission form includes: Subject, Description (rich text with file upload), Type, Priority (default: Normal), and optional Project.
  </Tab>

  <Tab title="Messaging" icon="message-circle">
    Use the `/ticket` slash command in any messaging channel to create a ticket from a message thread. The ticket subject is pre-filled from the message content.
  </Tab>
</Tabs>

## Ticket numbering

Every ticket receives a sequential, human-readable number formatted as **`TKT-{N}`** (e.g., TKT-001, TKT-104). Numbers are sequential per agency and generated using atomic database operations to prevent race conditions.

<Callout kind="info">
  The `TKT-{N}` format is for display only. Internal database relations use the ticket's unique ID (cuid).
</Callout>

## Ticket lifecycle

Every ticket follows a structured lifecycle through configurable statuses. Six default statuses are provided:

<Steps>
  <Step title="Open" icon="circle" titleType="p">
    The initial status when a ticket is created. The SLA clock starts ticking immediately.
  </Step>

  <Step title="Triaged" icon="search" titleType="p">
    The team has reviewed the ticket and determined priority and assignment. Still counts toward SLA time.
  </Step>

  <Step title="In Progress" icon="play" titleType="p">
    An agent is actively working on the ticket. SLA clock continues.
  </Step>

  <Step title="Waiting on Client" icon="clock" titleType="p">
    The agent needs information from the client. **The SLA clock pauses automatically** in this status.
  </Step>

  <Step title="Resolved" icon="check-circle" titleType="p">
    The issue has been addressed. The client receives a notification with an optional CSAT rating prompt. Resolved tickets auto-close after 7 days of inactivity.
  </Step>

  <Step title="Closed" icon="lock" titleType="p">
    The ticket is confirmed complete. No further action expected.
  </Step>
</Steps>

<Callout kind="tip">
  On Pro plans, you can create **custom statuses** beyond the 6 defaults — with custom names, colors, SLA pause behavior, and display ordering.
</Callout>

## Ticket types

Every ticket has a type that categorizes the nature of the request:

| Type | Description | Badge Color |
|------|-------------|-------------|
| **Bug** | Something is broken or not working correctly | Red |
| **Question** | Client needs clarification or information | Blue |
| **Feature Request** | Client suggests a new capability | Purple |
| **Change Request** | Client wants modifications to existing work | Orange |
| **Support** | General support or assistance needed | Teal |
| **Billing** | Invoice, payment, or billing inquiry | Green |
| **Other** | Anything that doesn't fit the above categories | Gray |

## Priority levels

Five priority levels determine SLA targets and notification urgency:

| Priority | Response Target | Resolution Target | Notification Priority |
|----------|----------------|-------------------|-----------------------|
| **Critical** | 30 minutes | 4 hours | P1 🚨 |
| **Urgent** | 1 hour | 8 hours | P1 🚨 |
| **High** | 4 hours | 1 business day | P2 |
| **Normal** | 8 hours | 3 business days | P3 |
| **Low** | 24 hours | 5 business days | P3 |

<Callout kind="info">
  SLA targets are configurable per agency in **Settings → Tickets → SLA Configuration**. The values above are defaults.
</Callout>

## Assignment

Tickets can be assigned to any agency team member (Owner, Admin, PM, or Team Member):

- **Manual assignment** — select an assignee when creating or from the ticket detail
- **Auto-assignment rules** (Enterprise) — route tickets automatically based on type, priority, or client using Specific, Round-Robin, or Least-Busy methods

When a ticket is assigned, the assignee receives a `TICKET_ASSIGNED` notification.

## Watchers & CC

Add stakeholders as **watchers** on a ticket. Watchers receive all public-facing notifications (new replies, status changes, resolution) without being the reporter or assignee. Org Owner and Org Admin can manage watchers from the ticket detail.

## Ticket sources

Tickets can originate from multiple channels:

| Source | Description |
|--------|-------------|
| **Portal** | Submitted via the client portal |
| **Email** | Created from inbound email (Enterprise) |
| **Messaging** | Created via the `/ticket` slash command |
| **Automation** | Created by an automation rule |
| **Manual** | Created by an agency team member on behalf of a client |
