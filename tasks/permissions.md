---
title: "Visibility & Permissions"
description: "Control task visibility by role, configure assignee rules, and manage task notifications."
---

## Task Visibility

Control who can see specific tasks using four visibility levels:

| Visibility | Who Can See |
|-----------|-------------|
| **Organization** (default) | Everyone in the workspace |
| **Project** | Only members of the task's project |
| **Team** | Specific users you grant access to, plus project members |
| **Private** | Only specific users you explicitly grant access to |

Set the visibility level in the task drawer. For Team and Private visibility, add individual users to the access list.

Client users (Organization Owner/Member) always see only tasks in their organization's projects, regardless of the visibility setting.

---

## Assignee Rules

The assignee dropdown shows different people depending on context:

| Context | Who Appears |
|---------|------------|
| Task inside a project | Project team members + Agency Owner |
| Task without a project | All agency staff + Agency Owner |

Client users (Organization Owner / Organization Member) **cannot be assigned tasks** — only agency staff appear in the assignee dropdown.

---

## Notifications

You'll receive automatic notifications for key task events:

| Event | Who Gets Notified |
|-------|------------------|
| Task assigned to you | Assignee |
| Task status changed | Assignee + creator (excludes the person who made the change) |
| New comment on your task | Assignee |
| Reply to your comment | Comment author |
| Reaction on your comment | Comment author |
| @mentioned in a comment | Mentioned user |
| Task due tomorrow | Assignee |
| Sub-task completed | Parent task assignee + creator |
| All checklist items completed | Task assignee + creator |

> **See also:** [Notifications](./notifications) for setting up preferences and digest frequency · [Automations](./automations) for automating task actions
