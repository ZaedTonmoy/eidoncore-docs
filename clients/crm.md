---
title: "CRM & Intelligence"
description: "Track client health, manage leads, identify upsell opportunities, and use follow-up tools."
---

## CRM Features

### Follow-Ups

Schedule and track follow-up tasks for each client:

- Set a **title**, **due date**, and **priority** (Low, Medium, High, Urgent)
- Assign to a team member
- Track status: Open → Completed / Cancelled
- Receive notifications when follow-ups are due or overdue

### Communication Logs

Record interactions with clients:

| Type | Use For |
|------|---------| 
| **Call** | Phone conversations |
| **Meeting** | In-person or virtual meetings |
| **Email Summary** | Key email correspondence |
| **Decision** | Important decisions (can be pinned) |
| **Issue** | Problems that arose |
| **Change Request** | Scope or requirement changes |

Each log includes details, outcome, duration, and which contact was involved.

#### Email Logging

Use the dedicated **"📧 Log Email"** button to record email interactions with structured fields — subject, from contact, to contacts (with auto-suggestions), and outcome (Positive, Neutral, or Negative).

#### Inline Editing

Click any communication log summary to edit it inline. Press `Cmd+Enter` to save or `Escape` to cancel. Pin important entries as decisions using the clickable ★ badge on each entry.

### Notes

Add internal notes about a client:

- Types: General, Call, Meeting, Warning, Opportunity
- Rich text formatting with @mentions and inline styling
- Pin important notes to keep them at the top (highlighted background)
- Fully internal — not visible to client portal users
- Searchable by content, type, and author

### Comments

Leave comments directly on a client organization for team discussion:

- **Internal comments** — only visible to agency staff
- **Standard comments** — visible to anyone with access to the client
- Supports threaded replies, @mentions, and emoji reactions
- Great for quick team discussions about the account without creating a formal note

### Documents

Upload and manage client-related documents:

| Document Type | Examples |
|--------------|---------| 
| **Contract** | Service agreements |
| **NDA** | Non-disclosure agreements |
| **SOW** | Scope of work documents |
| **Proposal** | Project proposals |
| **Brand Asset** | Logo files, brand guides |
| **Report** | Deliverable reports |

Documents support version tracking and contain metadata like file size and upload date.

---

## Client Health Scoring

Client health is automatically calculated based on:

- Overdue invoices
- Payment delays
- Activity gaps (how recently you've interacted)
- Overdue tasks

| Health State | Meaning |
|-------------|---------| 
| ● **Healthy** | Active engagement, payments on time |
| ● **At Risk** | Some warning signs (late payments, inactivity) |
| ● **Churn Risk** | Significant issues — requires immediate attention |

An info tooltip on the client Overview tab explains the composite health formula and rating thresholds.

<Callout kind="danger">
Health changes from At Risk → Churn Risk trigger **critical notifications** to agency owners.
</Callout>

> **See also:** [Reports](../reports) for client analytics · [Notifications](../notifications/overview) for health change alerts

---

## Saved Views

Save your current filter and sort combination as a named view for quick access later:

- Click **"💾 Save View"** when filters are active
- Views appear as clickable pills above the content area
- Choose between **Shared** (visible to all team members) or **Personal** views
- Collapsible when more than 3 views are saved

---

## 360° Activity Timeline

The Activity tab on each client shows a **unified timeline** merging data from 8+ sources:

| Source | What It Shows |
|--------|--------------|
| **Audit Log** | CRUD operations (created, updated, deleted) |
| **Follow-Ups** | Follow-up created and completed events |
| **Communications** | Logged calls, meetings, emails, decisions |
| **Notes** | Notes added to the client |
| **Invoices** | Invoices created, sent, and paid |
| **Projects** | Projects created and status changes |
| **Tickets** | Tickets created and resolved |
| **Documents** | Documents uploaded |

Each entry shows an icon, timestamp, actor, and content preview. The timeline uses scroll-based pagination for performance.

---

## Upsell & Expansion Tracking

Track expansion opportunities for each client:

| Field | Description |
|-------|-------------|
| **Upsell Probability** | Likelihood of expanding the account |
| **Estimated Expansion Value** | Projected additional revenue |
| **Upsell Notes** | Context and strategy notes for expansion |

These fields are visible on the client detail page and help your account managers identify growth opportunities.

---

## Lead Pipeline

When a client is in the **Lead**, **Contacted**, or **Proposal Sent** stage, additional lead tracking fields become available:

| Field | Description |
|-------|-------------|
| **Expected Value** | Estimated deal value |
| **Deal Probability** | Likelihood of closing (%) |
| **Expected Close Date** | Target close date |
| **Pipeline Source** | Where the lead came from |

---
