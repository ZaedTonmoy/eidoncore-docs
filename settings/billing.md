---
title: "Plans & Billing"
description: "Manage your subscription plan, report bugs, and view the platform changelog."
---

## Plans & Billing

Manage your subscription under **Settings → Plan & Billing** (Owner only).

### Plan Comparison

| Feature | Free | Pro ($29/mo) | Enterprise ($79/mo) |
|---------|:----:|:---:|:----------:|
| **Resource Limits** | | | |
| Team Members | 2 | 15 | Unlimited |
| Portal Members | 10 | 50 | Unlimited |
| Client Organizations | 3 | 50 | Unlimited |
| Active Projects | 5 | 100 | Unlimited |
| Services | 3 | 30 | Unlimited |
| Digital Products | 100 | 1,000 | Unlimited |
| Automations | 0 | 20 | Unlimited |
| Recurring Invoices | 0 | 20 | Unlimited |
| Intake Forms | 1 | 10 | Unlimited |
| Project Templates | 0 | 3 | Unlimited |
| Lists per Project | 3 | 10 | Unlimited |
| Open Tickets | 100 | 500 | Unlimited |
| Custom Roles | 0 | 5 | Unlimited |
| File Storage | 500 MB | 10 GB | 100 GB |
| **Communication** | | | |
| Chat Channels | 10 | 50 | Unlimited |
| Members per Channel | 10 | 30 | Unlimited |
| Message Retention | 30 days | 90 days | Unlimited |
| Max Attachment Size | 5 MB | 10 MB | 25 MB |
| **Core (All Plans)** | | | |
| Projects & Tasks | ✓ | ✓ | ✓ |
| Invoicing | ✓ | ✓ | ✓ |
| CRM & Client Management | ✓ | ✓ | ✓ |
| Dashboard | ✓ | ✓ | ✓ |
| Messaging | ✓ | ✓ | ✓ |
| Invoice Reminders (in-app) | ✓ | ✓ | ✓ |
| Basic Ticketing | ✓ | ✓ | ✓ |
| Slack Integration (single channel) | ✓ | ✓ | ✓ |
| **Pro Features** | | | |
| Recurring Invoices | ✗ | ✓ | ✓ |
| Credit Notes | ✗ | ✓ | ✓ |
| Automations | ✗ | ✓ | ✓ |
| Advanced Reports | ✗ | ✓ | ✓ |
| Service Catalog & Cart | ✗ | ✓ | ✓ |
| Service Templates | ✗ | ✓ | ✓ |
| Digital Products & Sales Tracker | ✗ | ✓ | ✓ |
| Proposals | ✗ | ✓ | ✓ |
| Project Templates | ✗ | ✓ | ✓ |
| Branded Emails | ✗ | ✓ | ✓ |
| Full Branding & Portal Customization | ✗ | ✓ | ✓ |
| Audit Log | ✗ | ✓ | ✓ |
| Health Scoring | ✗ | ✓ | ✓ |
| Advanced CRM (pipeline, saved views, bulk actions) | ✗ | ✓ | ✓ |
| Client Reports | ✗ | ✓ | ✓ |
| AI Connector (Claude, Cursor, Windsurf) | ✗ | ✓ | ✓ |
| Slack Multi-Channel Routing | ✗ | ✓ | ✓ |
| Slack Executive Digests | ✗ | ✓ | ✓ |
| Ticket SLA & CSAT | ✗ | ✓ | ✓ |
| Ticket Templates & Forms | ✗ | ✓ | ✓ |
| Ticket Merge | ✗ | ✓ | ✓ |
| Custom Ticket Statuses | ✗ | ✓ | ✓ |
| Ticket → Proposal Conversion | ✗ | ✓ | ✓ |
| Intake Forms | ✗ | ✓ | ✓ |
| **Enterprise Only** | | | |
| Custom SMTP | ✗ | ✗ | ✓ |
| Custom Domains | ✗ | ✗ | ✓ |
| White Label | ✗ | ✗ | ✓ |
| Security Policies | ✗ | ✗ | ✓ |
| Impersonation (View As) | ✗ | ✗ | ✓ |
| Ticket Auto-Assignment | ✗ | ✗ | ✓ |
| Email-to-Ticket Inbound | ✗ | ✗ | ✓ |

> Annual billing discounts available: Pro at $23/mo, Enterprise at $63/mo.

### Managing Your Plan

- **Upgrade** — Click the upgrade button on any plan to start a Stripe checkout
- **Downgrade** — Changes take effect at the end of your current billing period
- **Cancel** — Schedule cancellation with a reason (e.g., "Too expensive", "Not using it", "Switching provider"); you keep access until period end
- **Reactivate** — Reverse a pending cancellation before the period ends
- **Billing Portal** — Manage payment methods, view invoices, and update billing details via Stripe's billing portal
- **Usage Dashboard** — See your current resource usage vs. plan limits
- **Data Export** — Export all agency data as a downloadable bundle. Includes projects, tasks, clients, invoices, time entries, team members, and services. Available in CSV and JSON formats. Useful for backups, compliance, or migrating to another platform

### Plan Status Indicators

| Status | Meaning |
|--------|---------|
| **Active** | Subscription is current and paid |
| **Trialing** | Free 14-day Pro trial — no credit card required |
| **Past Due** | Payment failed — update your payment method (you still have access) |
| **Frozen** | 3+ payment failures — read-only access until payment is resolved |

A global status banner appears (visible to the Owner only) when your plan needs attention.

### Downgrade Behavior

When your plan downgrades (e.g., from Pro to Free):

- **Your data is never deleted** — all existing projects, tasks, invoices, and files remain accessible
- New creation is blocked when you exceed Free plan limits (e.g., can't add a 3rd team member on Free)
- **Automations** and **recurring invoices** that exceed limits are paused automatically
- When you upgrade again, paused automations and recurring invoices are **automatically reactivated**
- Existing team members keep access — only new invites are blocked beyond the limit

### Trial

Every new workspace starts with a **14-day free trial** of the Pro plan. You'll receive email reminders at **7 days** and **1 day** before your trial expires. When the trial ends, your workspace downgrades to the Free plan unless you subscribe.

---

## Bug Reports

Report issues directly from your workspace using the built-in **Bug Report** system.

### Quick Report (Floating Button)

A **bug report button** appears on every page in the workspace. Click it to instantly open the bug report form — the current page is auto-filled, and you can capture a **screenshot** of what you're seeing:

- **Automatic screenshot** — captures the current page using the browser's rendering engine
- **Screenshot markup** — annotate the screenshot to highlight the issue before submitting
- **Manual image upload** — drag and drop an image (PNG, JPG, GIF, WebP — up to 5 MB) if you prefer

### Filing a Report

| Field | Description |
|-------|-------------|
| **Title** | Short summary of the issue |
| **Description** | Detailed explanation of what went wrong |
| **Severity** | Low, Medium, High, or Critical |
| **Page** | Auto-filled with the current page URL |
| **Screenshot** | Captured or uploaded image showing the issue |

### Report Statuses

| Status | Meaning |
|--------|---------|
| **Open** | Newly submitted — awaiting review |
| **In Progress** | Being investigated |
| **Resolved** | Fix has been applied |
| **Closed** | Issue is resolved and closed |

### Tracking Your Reports

Navigate to **Bug Reports** in the sidebar (under Tools) to view all reports. You can:

- Filter by **status** and **severity**
- View a report's **comment thread** for updates from the platform team
- Leave comments on your own reports for additional context
- Receive **notifications** when a report's status changes or the platform team replies

### Permissions

Bug report access is available to **Owners**, **Admins**, and **Project Managers**.

---

## About / Changelog

View the platform changelog under **Settings → About** to see recent updates, new features, and improvements.
