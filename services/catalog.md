---
title: "Client Catalog"
description: "Public service catalog, service assignments, cart and checkout flow, and the end-to-end client purchase experience."
---

Manage your public service catalog and the end-to-end client purchase experience.

---

## Service Catalog

Your service catalog is the public-facing storefront where clients browse and purchase services.

### How Clients See Your Catalog

Clients access the catalog at `/catalog/services` and can:

- Browse services organized by category
- Search and filter using category pills
- View full service details with description, deliverables, FAQ, gallery, reviews, and pricing

---

## Assigning Services to Clients

Assign a published service directly to a client organization:
<Steps>
<Step title="Choose client & service" icon="users">
Select the client and the service to assign
</Step>
<Step title="Configure project" icon="settings">
Optionally select a **service template** or use **task templates** to auto-create a project
</Step>
<Step title="Set service period" icon="calendar">
Define start/end dates. For hour/credit services, initial balances are set automatically
</Step>
</Steps>

When a service is assigned:

- A project is optionally auto-created with pre-configured tasks
- Default assignees are added as project members
- If the client is still in the Lead stage, they're automatically upgraded to **Active**

---

## Cart & Checkout Flow

Clients can browse and purchase services directly through a self-service checkout:

### How It Works (Client Experience)
<Steps>
<Step title="Browse Catalog" icon="search">
Clients see available services with pricing at `/catalog/services`, organized by category with search and filtering
</Step>
<Step title="View Details" icon="eye">
Full service page with description, deliverables, FAQ, gallery, reviews, and pricing sidebar
</Step>
<Step title="Add to Cart" icon="shopping-cart">
Click "Add to Cart" on the service detail page
</Step>
<Step title="Review Cart" icon="list">
See line items, prices, and order total at `/cart`
</Step>
<Step title="Checkout" icon="credit-card">
Pay with card, Apple Pay, or Google Pay via the embedded Stripe payment form
</Step>
<Step title="Confirmation" icon="check-circle">
See project cards for each purchased service, account manager info, next steps, and optionally fill out an intake form
</Step>
</Steps>

### What Happens After Purchase

Behind the scenes:

- A **project** is auto-created for each purchased service
- A **service assignment** is linked to the project
- The client's status is upgraded to **Active** if needed
- The **agency owner** receives a "Service Purchased" notification
- The **client contacts** receive a "Service Activated" notification with a link to their new project
<Callout kind="info">
See also: [Client Portal](/client-portal) for the full client experience
</Callout>
