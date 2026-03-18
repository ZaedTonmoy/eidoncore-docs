---
title: "Roles & Security"
description: "Configure team roles and permissions, enforce security policies, and review the audit log."
---

## Integrations

### Stripe Connect

Connect your Stripe account to accept payments from clients:

<Steps>
<Step title="Navigate to Stripe integration" icon="settings">
Go to **Settings → Agency → Integrations → Stripe**
</Step>
<Step title="Start Stripe onboarding" icon="credit-card">
Click **"Connect Stripe"** to start the Stripe onboarding flow
</Step>
<Step title="Complete setup" icon="check-circle">
Complete Stripe's onboarding to enable payouts
</Step>
</Steps>

Once connected, clients can pay invoices via Stripe, and service purchases use the checkout flow.

### Slack

Send notifications to a Slack channel:

1. Go to **Settings → Agency → Integrations → Slack**
2. Enter your Slack **Incoming Webhook URL**
3. Choose which notification categories to send to Slack

> **See also:** [Notifications](../notifications/integrations#slack-integration) for more on Slack notifications

---

## Roles & Permissions

Manage roles under **Settings → Agency → Roles & Permissions**.

- View all built-in and custom roles
- Create new custom roles with specific permission sets
- Edit permissions for existing custom roles
- See how many team members are assigned to each role

> **See also:** [Team](../team) for detailed role descriptions and permissions

---

## Security Policies

Agency-wide security settings under **Settings → Agency → Security**:

| Policy | Description |
|--------|-------------|
| **Require 2FA** | Force all team members to enable two-factor authentication |
| **Session Idle Timeout** | Auto-logout after a period of inactivity (up to 24 hours) |
| **Maximum Session Lifetime** | Force re-login after a maximum period (up to 30 days) |
| **Re-Authentication for Sensitive Actions** | Require password re-entry for account deletion, MFA changes |
| **Email Domain Allowlist** | Restrict team invites to specific email domains |

> **See also:** [Security](../security/overview) for full security details

---

## Audit Log

View a complete log of all actions in your workspace under **Settings → Agency → Audit Log**.

- Filter by action type, actor, or date range
- See what changed (field-level diff), who made the change, and when
- Paginated results (25 entries per page)

---
