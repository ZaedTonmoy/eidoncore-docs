---
title: "Portal Features"
description: "Explore client features including the service catalog, purchasing, and guest checkout."
---

## Client Features

### Projects

Clients can view all projects assigned to their organization:

- Project name, status, and progress
- Task lists within each project
- Milestones and their completion status
- Uploaded files and documents
- Comments and discussions

Organization Owners can **add comments** on projects — these are always visible to the agency team (never internal-only).

### Messages

Clients can participate in real-time messaging:

- **Organization channel** — A shared channel for all organization members to communicate with the agency
- **Project channels** — Chat within each project they're a member of
- **Direct Messages** — Private conversations with agency staff members

Clients can see standard messages but **not internal messages** — agency staff can discuss work privately within shared channels.

<Callout kind="info">
Internal messages are never visible to client contacts. Use them for private team discussions within shared project channels.
</Callout>

> **See also:** [Messaging](../messaging) for full messaging features

### Tasks

Clients see tasks in projects assigned to their organization:

- Task title, status, priority, and due date
- Task details and description
- Comments and activity history

Organization Owners can **update task statuses** (e.g., mark as In Review or Done).

### Invoices

Clients can view all invoices billed to their organization:

- Invoice number, amount, status, and due date
- Payment history
- Outstanding balance

### Services

Clients see services assigned to their organization:

- Active, paused, and cancelled services
- Remaining hours or credits balance
- Billing period information
- Linked project (if applicable)

### Files

Clients can access files across all their projects:

- View files uploaded to their projects
- Download files

### Digital Assets

If a client has purchased any **digital products**, a **Digital Assets** page appears in their sidebar. This page shows all purchased products in a table with status, pricing, purchase date, and renewal information.

Clicking a product opens a detail panel where clients can:

- **Download** the product file (when fulfilled and a delivery URL is set)
- **View delivery instructions**
- **Submit an intake form** (if the product has one assigned)
- **Cancel a recurring subscription** with a cancellation reason
- View purchase timeline and cancellation details

> **See also:** [Services](../services/overview#digital-products) for the full digital products feature

### My Account

Clients have a dedicated **My Account** page (in the Finance section of the sidebar) for managing their account:

| Tab | What It Shows |
|-----|--------------|
| **Subscriptions** | Active, paused, and past service subscriptions with status, pricing, billing period, remaining hours/credits, and project links. Cancel subscriptions directly from here |
| **Payments** | Combined spending summary (total spent, invoice payments, service purchases), service purchase history, and invoice payment history |
| **Billing Info** | Organization billing details and saved payment methods (card brand, last 4 digits, expiry) |

When cancelling a subscription, clients select a reason and can add additional details. The agency is notified immediately.

---

## Service Catalog & Purchases

Clients can browse your service catalog and make purchases directly:

### Browsing the Catalog

At `/catalog/services`, clients see:

- **My Active Services** — Services they already have, with remaining hours/credits and a link to the project
- **Available Services** — All published services, organized by category
- **Search and filter** by text, category, or pricing type

### Making a Purchase

1. Click a service to view details (description, deliverables, FAQ, pricing, reviews)
2. Click **"Add to Cart"**
3. Review cart at `/cart`
4. **Checkout** with card, Apple Pay, or Google Pay
5. After payment, a confirmation page shows:
 - Project cards for each purchased service
 - Account manager details
 - "What happens next" steps
 - Intake form (if the service has one)

After purchase, a project is automatically created and immediately visible in the client's project list.

### Saved Payment Methods

During checkout, clients can opt to **save their card** for future purchases. Saved cards are:
- Displayed at checkout for one-click payments
- Visible in **My Account → Billing Info** (card brand, last 4 digits, expiry)
- Used for **automatic recurring billing** on subscription services

Clients can uncheck the "Save card" option during checkout if they prefer a one-time payment.

### Public Catalog (Guest Checkout)

Your service catalog is also accessible to **visitors who don't have an account**:

1. Visitor browses the public catalog at your workspace URL
2. Clicks **"Purchase This Service"** on a service detail page
3. Fills in registration details (company name, name, email, password)
4. Completes payment through Stripe
5. An account, project, and service assignment are **automatically created after payment**
6. Visitor can log in immediately to access their new project

Guest checkout creates the full client setup in one step — no pre-registration needed.

```mermaid
graph LR
    A["Browse Catalog"] --> B["Purchase Service"]
    B --> C["Enter Details"]
    C --> D["Pay via Stripe"]
    D --> E["Account Created"]
    E --> F["Project Ready"]
    F --> G["Login & Start"]
```

> **See also:** [Services](../services/catalog#cart--checkout-flow) for the full purchase flow from the agency perspective

---
