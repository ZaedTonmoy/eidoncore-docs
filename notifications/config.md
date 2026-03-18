---
title: "Configuration"
description: "Configure notification categories, smart grouping, quiet hours, and scope preferences."
---

## Notification Categories

Notifications are grouped into categories that you can manage individually:

<ExpandableGroup>
<Expandable title="Tasks & Comments">

| Category | Example Events |
|----------|---------------|
| **Task Assigned** | Task assigned or reassigned to you |
| **Task Status Changed** | Task completed, subtask done, checklist completed, file uploaded |
| **Comments & Mentions** | New comment, reply, reaction, @mention |
| **Deadline Approaching** | Task or project due soon |
| **Time Tracking** | Time logged on your tasks by others |

</Expandable>
<Expandable title="Invoices & Payments">

| Category | Example Events |
|----------|---------------|
| **Invoice Created** | Invoice sent or updated |
| **Invoice Paid** | Payment recorded (partial or full) |
| **Invoice Overdue** | Invoice past due |
| **Invoice Viewed** | Client opened the invoice |
| **Payment Failed** | Payment processing failure |
| **Recurring Generated** | Recurring invoice auto-generated |

</Expandable>
<Expandable title="Projects">

| Category | Example Events |
|----------|---------------|
| **Project Lifecycle** | Project completed, status changed, delayed |
| **Milestone Completed** | Project milestone reached |
| **Project Membership** | Added or removed from a project |
| **Budget Alert** | Project budget at ≥80% utilization |
| **Project Docs** | Documents created or updated |

</Expandable>
<Expandable title="Clients & Services">

| Category | Example Events |
|----------|---------------|
| **Follow-Up Reminders** | CRM follow-up due or overdue |
| **Contract Expiring** | Client contract approaching expiry |
| **Client Health Changed** | Client health score changed significantly |
| **Service Purchased** | Client purchased, reviewed, or activated a service. Hours/credits depleted |
| **Service Cancelled** | Client cancelled a subscription |

</Expandable>
<Expandable title="Operations & Chat">

| Category | Example Events |
|----------|---------------|
| **Team Updates** | Role changed, member removed |
| **Automation Failed** | Automation rule execution failed |
| **Plan Updates** | Subscription plan changes (trial ending, payment issues) |
| **Chat & Messaging** | @mentions in chat, replies to your messages, reactions to your messages |

</Expandable>
</ExpandableGroup>

Not every role sees every category — only relevant categories appear in your settings.

---

## Smart Grouping

To prevent notification overload, similar events are automatically grouped:

| Pattern | Instead of... | You see... |
|---------|--------------|------------|
| Same type + same item + same day | 5 separate "time logged" on Task A | "5 time entries logged on Task A today" |
| Batch events | 3 separate "task due tomorrow" alerts | "3 tasks due tomorrow" |
| Multiple updates on one project | Member added + File uploaded + Status changed | "Project Alpha updated (3 changes today)" |

Additionally, a **24-hour cooldown** prevents duplicate notifications of the same type for the same item.

---

## Quiet Hours

Set a quiet period when non-critical notifications won't be delivered via email:

- Configure **start time** and **end time** in your notification settings
- Critical events (P1) **always** bypass quiet hours
- Bell notifications are still stored — you'll see them when you log in

---

## Notification Scope

Control how broadly you want to be notified:

| Scope | What You Receive |
|-------|-----------------|
| **All** | Notifications for everything in the workspace |
| **Only Mine** | Only notifications where you're directly involved |
| **My Projects** | Notifications for projects you're a member of |

Organization users (client contacts) always see notifications scoped to their organization.

---
