# Services

Build a service catalog for your agency, assign services to clients, and let clients purchase directly through an integrated cart and checkout experience.

---

## Service Catalog

### Creating a Service

Navigate to **Services** in the sidebar and click **"New Service"**. The multi-step builder walks you through:

1. **Basics** — Name, short summary, category, and cover image
2. **Description** — Full description, deliverables, FAQ, useful links, and gallery images
3. **Pricing** — Choose a pricing model and configure billing
4. **Review & Publish** — Preview, edit the URL slug, and publish

### Service Statuses

| Status | Meaning |
|--------|---------|
| **Draft** | Being prepared — not visible to clients, cannot be assigned |
| **Published** | Live and available for assignment or purchase |
| **Archived** | Soft-deleted — no longer active |

You can switch between Draft and Published at any time. To publish, a service must have a name and valid pricing.

---

## Pricing Models

Eidoncore supports 5 pricing models to fit different agency service types:

| Model | How It Works | Example |
|-------|-------------|---------|
| **One-Time Fixed** | Single flat fee for a deliverable | Website redesign — $5,000 |
| **Recurring Monthly** | Ongoing subscription (monthly, quarterly, or yearly) | SEO retainer — $2,000/mo |
| **Hourly Rate** | Bill per hour worked | Consulting — $150/hr |
| **Hourly Block** | Prepaid block of hours per period | Support package — 20 hours/mo |
| **Credit Pack** | Prepaid credits for work units | Design credits — 100 credits/mo |

### Billing Configuration

Each service specifies:

- **Billing type**: One-Time, Recurring, or Usage-Based
- **Billing interval**: Monthly, Quarterly, or Yearly (for recurring)
- **Billing mode**: Manual or Stripe (for automated payment collection)

---

## Included Hours & Credits

For Hourly Block and Credit Pack services:

| Setting | Description |
|---------|-------------|
| **Included Hours / Credits** | Amount included per billing period |
| **Rollover Policy** | None (reset each period), Capped, or Unlimited |
| **Expiry Days** | Number of days before unused hours/credits expire |
| **Minimum Billable Increment** | Smallest time unit for billing (e.g., 15 minutes) |

---

## Service Content

Enrich your service listings with:

| Content | Description |
|---------|-------------|
| **Cover Image** | Hero image displayed at the top of the service page |
| **Gallery** | Up to 8 images showcasing your work |
| **Deliverables** | A checklist of what's included |
| **FAQ** | Up to 15 frequently asked questions with answers |
| **Useful Links** | Up to 10 links to external resources |

### Client Visibility Controls

Choose which content sections clients can see on the catalog page:

- Show/hide pricing, FAQ, deliverables, gallery, and reviews independently
- These settings are enforced server-side — hidden content is never sent to the client

---

## Task Templates

Pre-configure tasks that are automatically created when a service is assigned to a client:

- Set a **title**, **description**, **priority**, and **estimated hours** for each template task
- Tasks are created inside the project auto-generated for the client
- Saves time on repetitive project setups

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

## Share Links

Every service has shareable public catalog links:

- **Service catalog**: Share a link to your full public catalog (`/catalog/services`)
- **Individual service**: Share a link to any published, public service's detail page (`/catalog/services/{slug}`)

Share links are available on the service list page and each service's detail page via the **Copy Link** button.

---

## Default Assignees

Set **default team members** on a service who will be automatically assigned as project members when the service is assigned or purchased by a client. This ensures the right people are on every project from day one.

---

## Assigning Services to Clients

Assign a published service directly to a client organization:

1. Choose the client and service
2. Optionally select a **service template** or use **task templates** to auto-create a project
3. Set the service period (start/end dates)
4. For hour/credit services, initial balances are set automatically

When a service is assigned:
- A project is optionally auto-created with pre-configured tasks
- Default assignees are added as project members
- If the client is still in the Lead stage, they're automatically upgraded to **Active**

---

## Cart & Checkout Flow

Clients can browse and purchase services directly through a self-service checkout:

### How It Works (Client Experience)

1. **Browse Catalog** (`/catalog/services`) — Clients see available services with pricing, organized by category with search and filtering
2. **View Details** — Full service page with description, deliverables, FAQ, gallery, reviews, and pricing sidebar
3. **Add to Cart** — Click "Add to Cart" on the service detail page
4. **Review Cart** (`/cart`) — See line items, prices, and order total
5. **Checkout** (`/cart/checkout`) — Pay with card, Apple Pay, or Google Pay via the embedded Stripe payment form
6. **Confirmation** (`/cart/success`) — See project cards for each purchased service, account manager info, next steps, and optionally fill out an intake form

### What Happens After Purchase

Behind the scenes:
- A **project** is auto-created for each purchased service
- A **service assignment** is linked to the project
- The client's status is upgraded to **Active** if needed
- The **agency owner** receives a "Service Purchased" notification
- The **client contacts** receive a "Service Activated" notification with a link to their new project

> **See also:** [Client Portal](./client-portal.md) for the full client experience

---

## Hours & Credits Tracking

### Hours Tracking

For services with included hours (Hourly Block):

- When time is logged against a service assignment, the remaining hours balance is automatically reduced
- If time entries are deleted, the balance is restored
- When all hours are depleted, the agency owner and client contacts are notified
- If a recurring subscription's auto-renewal payment fails, the service status changes to **Past Due** — the agency owner and client contacts are notified to update payment details

### Service Assignment Statuses

| Status | Meaning |
|--------|---------|
| **Pending** | Just purchased, awaiting setup |
| **Active** | Currently in use |
| **Paused** | Temporarily suspended |
| **Past Due** | Auto-renewal payment failed — payment method needs updating |
| **Cancelled** | Terminated by the client or agency |
| **Completed** | One-time service delivered |

### Credits Tracking

For credit-based services (Credit Pack):

- Credits are tracked via a **ledger** system
- Credit entries can be: **Add** (initial or top-up), **Spend** (work performed), or **Adjust** (manual correction)
- Each entry includes the amount, reference type, and a note
- When all credits are depleted, the agency owner and client contacts are notified

---

## Intake Forms

Services can have an optional **intake form** that clients fill out after purchase. This is great for collecting project requirements, preferences, or onboarding information.

### How It Works

1. **Create a form** — Go to the **Intake Forms** page (in the sidebar under Tools) and build a form with the drag-and-drop form builder
2. **Add fields** — Supported field types:
 - **Text** — Short text input
 - **Textarea** — Multi-line text
 - **Email** — Email address
 - **Phone** — Phone number
 - **URL** — Web link
 - **Number** — Numeric input
 - **Select** — Dropdown with custom options
 - **Checkbox** — Yes/no toggle
3. **Assign to services** — Link one form to one or more services
4. **Client fills it out** — After purchasing a service, clients see the intake form on the confirmation page
5. **Responses saved** — Submissions are automatically saved as a **pinned project document** in the auto-created project

The agency owner is notified when a client submits an intake form.

### Managing Intake Forms

The Intake Forms page is accessible to **Owners**, **Admins**, and **Project Managers**. From there you can:

- View all forms with field counts and submission counts
- Create, edit, and delete forms
- See which services each form is assigned to
- Review past submissions

> **See also:** [Settings](./settings.md) for managing intake form templates

---

## Reviews

Clients who are active subscribers can leave **reviews** on services:

- Star rating (1-5) with title and rich text comment
- Reviews are visible on the catalog detail page (when approved)
- Moderation support for agency review management
- The agency owner is notified when a review is submitted

---

## Service Access Control

Control which agency staff members can view or manage each service:

- By default, services follow your role permission settings
- Add per-service access rules for more granular control

> **See also:** [Team](./team.md) for role-based permissions · [Projects](./projects.md) for auto-created project details · [Invoicing](./invoicing.md) for service-linked billing
