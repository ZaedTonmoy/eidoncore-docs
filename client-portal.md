# Client Portal

The client portal gives your clients a dedicated space to view their projects, tasks, invoices, services, and files — all branded with your agency's identity.

---

## What Is the Client Portal?

When you grant a client contact **portal access**, they can log in to your agency's workspace and see information scoped to their organization. They see your agency's branding (logo, colors, fonts) and interact with the platform through a streamlined interface.

Clients access the portal via your workspace URL (`yourslug.eidoncore.com`) or your custom domain (`app.youragency.com`).

> **See also:** [Clients](./clients.md#portal-access) for how to grant portal access to contacts

---

## Portal Roles

| Role | Display Name | What They Can Do |
|------|-------------|-----------------|
| **Organization Owner** | Client admin | View projects, tasks, invoices, and services. Can comment on tasks and change task statuses |
| **Organization Member** | Client viewer | Same views as Organization Owner, but **read-only** — cannot modify tasks or add comments |

---

## What Clients See

### Client Dashboard

After logging in, clients see a dedicated dashboard showing:

- **Project progress bars** — Visual completion status of each project
- **Task breakdown** — Tasks grouped by status (To Do, In Progress, Done, etc.)
- **Recent invoices** — Latest invoices and their payment status
- **Active services** — Services assigned to their organization

If you've configured a **welcome message** in portal branding, it appears as a banner at the top.

### Sidebar Navigation

Clients see a simplified sidebar:

| Nav Item | Organization Owner | Organization Member |
|----------|:-----------------:|:-------------------:|
| Dashboard | ✅ | ✅ |
| Projects | ✅ | ✅ |
| Tasks | ✅ | ✅ |
| Services | ✅ | ✅ |
| Invoices | ✅ | ✅ |
| Reports | ✅ | ❌ |
| Settings (Account) | ✅ | ✅ |

You can further customize what clients see by **hiding nav items** in Settings → Agency → Branding → Portal.

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

> **See also:** [Services](./services.md#cart--checkout-flow) for the full purchase flow from the agency perspective

---

## Client Account Management

Clients can manage their account under **Settings → Account**:

### My Account Page

| Feature | Description |
|---------|-------------|
| **Profile** | Update name, avatar, and contact information |
| **Password** | Change password (meets same strength requirements) |
| **Two-Factor Authentication** | Enable/disable 2FA for extra security |
| **Active Sessions** | View and revoke login sessions |
| **Notification Preferences** | Toggle email, digest frequency |

### Subscriptions

If clients have active service subscriptions, they can:

- View their active subscriptions
- See billing period and renewal dates
- **Cancel subscriptions** (with a cancellation reason — the agency is notified)

### Billing Information

Clients can manage their payment methods and view their billing history.

---

## Client Notifications

Clients receive notifications for events relevant to their organization:

| Notification | Organization Owner | Organization Member |
|-------------|:-----------------:|:-------------------:|
| Task assigned | ✅ | ✅ |
| Task status changed | ✅ | ✅ |
| Comments & mentions | ✅ | ✅ |
| Invoice sent/updated | ✅ | ✅ |
| Invoice paid | ✅ | ✅ |
| Invoice overdue | ✅ | ❌ |
| Project delayed | ✅ | ✅ |
| Deadline approaching | ✅ | ✅ |
| Project completed | ✅ | ✅ |
| Milestone completed | ✅ | ✅ |
| Contract expiring | ✅ | ❌ |
| Service activated | ✅ | ✅ |

Default notification delivery:
- **Organization Owner** — Instant delivery
- **Organization Member** — Daily digest

> **See also:** [Notifications](./notifications.md) for full notification details · [Settings](./settings.md#notification-preferences) for preference management
