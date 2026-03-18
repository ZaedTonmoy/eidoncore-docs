---
title: "Notification Basics"
description: "Understand bell and email notifications, priority levels, and how alerts are delivered."
---

Stay informed about what's happening in your workspace through bell notifications, email alerts, digest summaries, and Slack integration.

---

## Bell Notifications

The bell icon () in the top-right of every page shows your notification count. Click it to open the notification panel.

- **Unread badge** — Shows the number of unread notifications
- **Mark as read** — Click a notification to mark it as read
- **Mark all read** — Clear all unread items at once
- **Navigate** — Click a notification to jump directly to the relevant task, invoice, project, or other item

---

## Email Notifications

Notifications can also be delivered via email, depending on your preferences and the notification type.

### Delivery Modes

| Mode | How It Works |
|------|-------------|
| **Instant** | Email sent immediately when the event occurs |
| **Daily Digest** | Summary email sent once a day (8:00 AM) |
| **Weekly Digest** | Summary email sent weekly on Mondays |

Default delivery mode depends on your role:

| Role | Default Mode |
|------|-------------|
| Owner, Admin, PM, Organization Owner | Instant |
| Accountant, Team Member, Organization Member | Daily Digest |

You can change your preference in **Settings → Account → Notifications**.

### Per-Category Email Control

Toggle email delivery on or off for each notification category independently. This lets you receive bell notifications for everything but limit emails to what matters most.

### Branded Emails

All notification emails are branded with your agency's logo, colors, signature, and social links. They include:

- A "View in Dashboard" button linking directly to the item
- A one-click **unsubscribe** link at the bottom (CAN-SPAM compliant)

> Email notifications require SMTP to be configured. See [Settings](../settings/branding#email-smtp-setup).

---

## Priority Levels

Notifications are categorized by priority to help you focus on what matters:

| Priority | Meaning | Behavior |
|----------|---------|----------|
| ● **Critical (P1)** | Financial loss, system failure, operational breakdown | Always instant — bypasses digest and quiet hours |
| ● **Risk (P2)** | Trending toward a problem — needs attention soon | Instant for agency staff, respects quiet hours for clients |
| ● **Action Required (P3)** | You need to do something specific | Normal delivery, respects digest settings |
| ○ **Informational (P4)** | Lifecycle updates and context | Collapsible, digestable, low visual weight |

### Critical Events (Always Instant)

These events bypass all batching and quiet hours:
- Payment failed
- Automation failed
- Project delayed
- Invoice overdue
- Task overdue batch
- Budget threshold reached
- Contract expiring
- Client health changed to Churn Risk

---
