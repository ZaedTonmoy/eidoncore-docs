---
title: "Services Overview"
description: "Build a service catalog with project-based services and digital products, manage categories, templates, and access control."
---

Build a service catalog for your agency, assign services to clients, and let clients purchase directly through an integrated cart and checkout experience. Eidoncore supports two types of offerings: **project-based services** (collaborative workspaces) and **digital products** (downloadable deliverables).
<Columns cols="2">
<Card title="Service Builder" icon="wrench" href="/services/builder">
Create services with content, task templates, and intake forms
</Card>
<Card title="Pricing & Quotas" icon="calculator" href="/services/pricing">
Pricing models, hours/credits tracking, and quota management
</Card>
<Card title="Client Catalog" icon="shopping-bag" href="/services/catalog">
Catalog, cart & checkout, and service assignments
</Card>
</Columns>

---

## Fulfillment Types

Every offering in your catalog is one of two types:

| Type | Sidebar Location | Delivery | Use Case |
|------|-----------------|----------|----------|
| **Services** (Project-Based) | Offerings --> Services | Creates a collaborative project workspace | Retainers, custom work, consulting |
| **Digital Products** | Offerings --> Products | Downloadable files + delivery instructions | Templates, design assets, guides, toolkits |

Both types are created through the same multi-step **Service Builder** and share pricing models, categories, and catalog features. The fulfillment type is selected at creation and **cannot be changed** after the offering is created.

---

## Digital Products

Digital products are offerings delivered as files or instructions rather than collaborative projects.

### Creating a Digital Product

Navigate to **Products** (under Offerings in the sidebar) and click **"New Digital Product"**. The builder is the same as for services, with an additional **Digital Delivery** section on Step 2:

| Field | Description |
|-------|-------------|
| **Delivery File URL** | The download URL for the product file |
| **Delivery Instructions** | Instructions shown to the buyer after purchase |
| **Requires Manual Fulfillment** | If enabled, the agency must manually mark the product as delivered |

### Products Listing

The Products page shows all digital products in a grid layout with cover images, pricing, and category labels. Use category filter pills and search to find products quickly.

### Sales Tracker

Track all digital product sales in one place via **Products --> Sales Tracker**:

- **Stats cards** at the top showing Monthly Recurring Revenue, Total Revenue, Active Sales, and Churn
- **Filter by status** — All, Active, Pending, or Cancelled (with counts)
- **Search** by product name or client company
- **Sortable table** with 7 columns (Product, Client, Price, Type, Status, Fulfillment, Date) — click any column header to toggle A-Z / Z-A sorting

Click any row to open the **Sale Detail Panel** (slide-out drawer) where you can:

| Section | What You Can Do |
|---------|----------------|
| **Status** | Change to Active, Pending, Cancelled, Paused, or Expired |
| **Fulfillment** | Mark as Delivered or Pending |
| **Dates** | Set start date and end date |
| **Recurring Settings** | Set next renewal date, toggle auto-renew, view billing interval |
| **Notes** | Add internal notes about this sale |
| **Intake Form** | View linked intake form name and submission status |
| **Timeline** | See created, started, and cancelled dates |

### Digital Assets (Client View)

Clients who purchase digital products see a **Digital Assets** page in their sidebar. This page shows all their purchased digital products in a table with:

- Product name with delivery instructions preview
- Status, billing type, and price
- Purchase date and next renewal date (for recurring products)

Clicking a row opens a detail panel where clients can:

- **Download** the product file (if fulfilled and a delivery URL exists)
- **Submit an intake form** (if the product has one assigned)
- **Cancel a recurring subscription** — with a reason selection (6 predefined options + custom text)
- View delivery instructions, timeline, and cancellation details

### File Security

Digital product downloads are protected with:

- **Authentication** — Only verified purchasers can download
- **Rate limiting** — 10 downloads per hour per user
- **Signed URLs** — Temporary download links that expire after 60 minutes
- **Fulfillment check** — Files are only served when the product is marked as Delivered
- **Virus scanning** — All uploaded files are scanned before being made available

---

## Service Templates

For more complex project scaffolding, create **Service Templates** that define:

- A **default project name** for auto-created projects
- **Pre-configured tasks** (title, description, status, priority, sort order)
- **Pre-configured milestones** (name, sort order)
- An optional **SLA configuration**

Multiple templates can exist for a single service — the user picks one at assignment time.

---

## Categories

Organize your service catalog with **categories**:

- Each category has a name, slug, description, and color badge
- Filter services by category in the catalog
- Deleting a category doesn't delete the services in it — they simply become uncategorized

---

## Default Assignees

Set **default team members** on a service who will be automatically assigned as project members when the service is assigned or purchased by a client. This ensures the right people are on every project from day one.

---

## Service Access Control

Control which agency staff members can view or manage each service:

- By default, services follow your role permission settings
- Users with the **View All Services** permission can see all services
- For users without that permission, add **per-service access rules**:

| Access Level | What It Grants |
|-------------|----------------|
| **Can View** | See the service in listings |
| **Can Edit** | Modify the service details |
| **Can Assign** | Assign the service to clients |
<Callout kind="tip">
This is useful for large teams where certain services should only be visible to specific team members.
</Callout>

> **See also:** [Team](./team) for role-based permissions · [Projects](./projects) for auto-created project details · [Invoicing](./invoicing) for service-linked billing
