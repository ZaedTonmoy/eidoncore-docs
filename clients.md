# Clients (CRM)

The Clients section is your built-in CRM for managing client organizations, contacts, and relationships. Track the full client lifecycle from lead to active account.

---

## Adding a Client

Navigate to **Clients** in the sidebar and click **"New Client"**.

### Client Details

| Field | Description |
|-------|-------------|
| **Company Name** | The client's business name |
| **Status** | Pipeline stage (see below) |
| **Industry** | Business industry |
| **Website** | Client's website URL |
| **Country / Timezone** | Location and time zone |
| **Tags** | Custom tags for organizing clients |
| **Account Manager** | Assign an agency team member to manage this account |
| **Notes** | Internal notes about the client |

### Financial Profile

| Field | Description |
|-------|-------------|
| **Billing Email** | Email address for invoices and billing communications |
| **Tax ID** | Client's tax identification number |
| **Default Payment Terms** | Net-X days applied to new invoices for this client |
| **Default Tax Rate** | Tax rate automatically applied to new invoices |
| **Payment Reliability** | Tracked payment behavior score |
| **Currency** | Client's preferred currency |

### Client Status Pipeline

Clients move through a lifecycle pipeline:

```
Lead → Contacted → Proposal Sent → Active → Paused → Churned / Lost / Archived
```

When a client purchases a service through the catalog, their status is automatically upgraded to **Active** if they were previously a Lead, Contacted, or Proposal Sent.

---

## Contacts

Each client organization can have multiple **contacts** — the people you work with at the client company.

### Contact Details

| Field | Description |
|-------|-------------|
| **Name & Email** | Contact identity (one contact per email per client) |
| **Phone** | Phone number |
| **Title** | Business title |
| **Role Type** | Decision Maker, Finance, Technical, Ops, or Other |
| **Preferred Channel** | Email, Phone, Slack, WhatsApp, or Other |
| **Stakeholder Flags** | Primary contact, billing contact, or approver |

### Portal Access

Contacts can be granted **portal access** to your agency's platform, allowing them to view their projects, tasks, invoices, and services.

Two ways to grant access:

1. **When adding a contact** — Set a password during contact creation
2. **Send Invite** — Click the " Send Invite" button on any contact without an account. They'll receive a branded invitation email and can set their own password via the "Forgot Password" flow

Portal users are assigned one of two roles:

| Role | Capabilities |
|------|-------------|
| **Organization Owner** | View projects, tasks, invoices, services. Can comment, create tasks, and update task statuses. Can view reports |
| **Organization Member** | Same views. Can create, edit, and assign tasks. Can add comments. Cannot view reports |

> **See also:** [Client Portal](./client-portal) for a detailed guide on what clients see and can do

---

## Client Detail Page

Each client's detail page is organized into tabs:

| Tab | What It Contains |
|-----|-----------------|
| **Overview** | Company details, financial profile, health score, lead pipeline, contract tracking |
| **Contacts** | Contact list, portal access management, send invite |
| **Projects** | Projects assigned to this client |
| **Invoices** | Invoices billed to this client |
| **Notes** | Internal team notes (General, Call, Meeting, Warning, Opportunity) |
| **Communications** | Interaction logs (calls, meetings, emails, decisions, issues, change requests) |
| **Documents** | Uploaded files (contracts, NDAs, SOWs, proposals, brand assets) |
| **Activity** | Full activity timeline for all client-related events |
| **Settings** | Client-specific settings (follow-ups, tags, account management) |

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

### Notes

Add internal notes about a client:

- Types: General, Call, Meeting, Warning, Opportunity
- Pin important notes to keep them at the top
- Fully internal — not visible to client portal users

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

Health changes from At Risk → Churn Risk trigger **critical notifications** to agency owners.

> **See also:** [Reports](./reports) for client analytics · [Notifications](./notifications) for health change alerts

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

> **See also:** [Services](./services) for managing your service catalog · [Invoicing](./invoicing) for billing clients

---

## Client List Page

The Clients list page at `/organizations` gives you an overview of all clients:

| Column | What It Shows |
|--------|--------------|
| **Company Name** | Client name |
| **Status** | Pipeline status badge |
| **Revenue** | Total revenue from invoices |
| **Unpaid** | Outstanding invoice amount |
| **Health** | Health indicator (green/yellow/red) |
| **Last Activity** | How recently you've interacted |

Sort by name, status, revenue, unpaid amount, health, last activity, creation date, or project count. Filter by name search, status, or health state.

---

## Notifications

| Event | Who Gets Notified |
|-------|------------------|
| New client organization created | Agency owners |
| Follow-up due today | Follow-up owner |
| Follow-up overdue | Follow-up owner |
| Contract expiring within 30 days | Agency owners |
| Client health state changed | Agency owners |

> **See also:** [Settings](./settings) for notification preferences
