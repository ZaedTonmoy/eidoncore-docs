---
title: "Service Builder"
description: "Create services with rich content, task templates, intake forms, reviews, and shareable catalog links."
---

Create and manage services with rich content, task automation, and intake forms.

---

## Creating a Service

Navigate to **Services** in the sidebar and click **"New Service"**. The multi-step builder walks you through:
<Steps>
<Step title="Basics" icon="edit">
Name, short summary, category, and cover image
</Step>
<Step title="Description" icon="file-text">
Full description, deliverables, FAQ, useful links, and gallery images
</Step>
<Step title="Pricing" icon="credit-card">
Choose a pricing model and configure billing
</Step>
<Step title="Review & Publish" icon="check-circle">
Preview, edit the URL slug, and publish
</Step>
</Steps>

## Service Statuses

| Status | Meaning |
|--------|---------|
| **Draft** | Being prepared — not visible to clients, cannot be assigned |
| **Published** | Live and available for assignment or purchase |
| **Archived** | Soft-deleted — no longer active |
<Callout kind="info">
You can switch between Draft and Published at any time. To publish, a service must have a name and valid pricing.
</Callout>

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

## Intake Forms

Services can have an optional **intake form** that clients fill out after purchase. This is great for collecting project requirements, preferences, or onboarding information.

### Form Statuses

| Status | Meaning |
|--------|---------|
| **Draft** | Form is being built — not available to clients |
| **Published** | Active and linked to services — clients can fill it out |
| **Archived** | Retired — no longer available for new submissions |

### How It Works
<Steps>
<Step title="Create a form" icon="file-plus">
Go to the **Intake Forms** page (in the sidebar under Tools) and build a form with the drag-and-drop form builder
</Step>
<Step title="Add fields" icon="list">
Drag fields from the palette onto the canvas. Supported field types are listed below.
</Step>
<Step title="Configure fields" icon="settings">
Set required toggles, placeholders, help text, validation rules, and conditional visibility
</Step>
<Step title="Assign to services" icon="link">
Link one form to one or more services
</Step>
<Step title="Client fills it out" icon="user-check">
After purchasing a service, clients see the intake form on the confirmation page
</Step>
</Steps>

### Supported Field Types
<Tabs>
<Tab title="Text Fields" icon="type">

| Field Type | What It Collects |
|-----------|-----------------|
| Text | Short text input |
| Textarea | Multi-line text |
| Email | Email address |
| Phone | Phone number |
| URL | Web link |
| Number | Numeric input |
| Address | Structured address input |
| Currency | Formatted money input with $ prefix |
</Tab>
<Tab title="Selection" icon="check-square">

| Field Type | What It Collects |
|-----------|-----------------|
| Select | Single dropdown with custom options |
| Multi-Select | Checkbox group for multiple choices |
| Checkbox | Single yes/no toggle |
| Radio | Radio button group |
| Toggle | Yes/No pill buttons |
</Tab>
<Tab title="Date & Time" icon="calendar">

| Field Type | What It Collects |
|-----------|-----------------|
| Date | Date picker |
| Time | Time input |
| DateTime | Combined date and time picker |
</Tab>
<Tab title="Rich Fields" icon="star">

| Field Type | What It Collects |
|-----------|-----------------|
| File Upload | File upload zone with drag-and-drop |
| Image Upload | Image upload with preview |
| Rating | Configurable star rating (3–10 stars) |
| Signature | Signature drawing canvas |
| Color Picker | Color picker with hex input |
| Slider | Range slider with configurable min/max |
</Tab>
<Tab title="Layout & Advanced" icon="layout">

| Field Type | What It Collects |
|-----------|-----------------|
| Heading | Section heading (no input — for structure) |
| Paragraph | Description text block |
| Divider | Visual separator |
| Hidden | Pre-filled hidden field |
| Repeater | Dynamic row group — add/remove rows with configurable sub-fields |
</Tab>
</Tabs>

### Field Configuration

Each field supports:
- **Required** toggle — must be filled to submit
- **Placeholder** and **Help Text** — guide the client
- **Width** — Full or Half width for side-by-side layout
- **Validation** rules — min/max length, pattern matching, file types, max file size, max rating
- **Conditional visibility** — show/hide based on another field's value
<Callout kind="tip">
Use **multi-page forms** for longer forms. Clients see a step wizard with numbered progress indicators and per-page validation.
</Callout>

### Managing Intake Forms

The Intake Forms page is accessible to **Owners**, **Admins**, and **Project Managers**. From there you can:

- View all forms with field counts and submission counts
- Filter by status (Draft, Published, Archived)
- Search by form name
- Create, edit, duplicate, and delete forms
- See which services each form is assigned to
- Review past submissions

---

## Reviews

Clients who are active subscribers can leave **reviews** on services:

- **Star rating** (1-5) with an optional title and rich text comment
- **One review per organization** per service
- Reviews require **moderation** before appearing publicly:
  - Newly submitted reviews are marked as **pending**
  - Agency owners can **approve** reviews to make them visible in the catalog
  - Agency owners can **reject** (delete) reviews
- Approved reviews appear on the catalog detail page with star ratings and comment cards
- The best review quote (highest rated with a comment) is featured on the service hero section
<Callout kind="info">
The agency owner is notified when a review is submitted.
</Callout>

---

## Share Links

Every service has shareable public catalog links:

- **Service catalog**: Share a link to your full public catalog (`/catalog/services`)
- **Individual service**: Share a link to any published, public service's detail page (`/catalog/services/{slug}`)

Share links are available on the service list page and each service's detail page via the **Copy Link** button.
