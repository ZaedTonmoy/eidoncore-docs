---
title: "Policies & Auditing"
description: "Configure security policies, password requirements, and review audit logs."
---

## Security Policies

Agency owners can enforce security rules under **Settings → Agency → Security**:

| Policy | What It Does |
|--------|-------------|
| **Require 2FA** | All team members must enable two-factor authentication |
| **Session Idle Timeout** | Auto-logout after inactivity |
| **Max Session Lifetime** | Maximum time before forced re-login |
| **Re-Authentication** | Require password re-entry for sensitive actions (account deletion, MFA changes, backup code regeneration) |
| **Email Domain Allowlist** | Only allow team invites from specific email domains (e.g., `@youragency.com`) |

---

## Password Requirements

All passwords must meet these minimum requirements:

- At least **8 characters** long
- At least **1 uppercase letter**
- At least **1 lowercase letter**
- At least **1 digit**

These requirements apply to registration, password changes, and password resets.

---

## Audit Logging

Every significant action in your workspace is recorded in the audit log:

| Information | What's Tracked |
|------------|---------------|
| **Action** | What happened (e.g., profile updated, role changed, invoice created) |
| **Who** | Which user performed the action |
| **What Changed** | Field-level details of the change |
| **When** | Timestamp |
| **From Where** | IP address and browser information |

Access the audit log under **Settings → Agency → Audit Log**. Filter by action type, actor, or date range.

---
