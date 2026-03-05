# Settings & Customization

Configure your account, brand your workspace, set up email delivery, connect integrations, and manage your subscription plan.

---

## Account Settings

Accessible to all users under **Settings → Account**.

### Profile

| Setting | Description |
|---------|-------------|
| **Display Name** | Your name as it appears across the workspace |
| **Avatar** | Profile picture (drag-and-drop upload) |
| **Timezone** | Your local timezone for timestamps and scheduling |
| **Locale** | Language and formatting preferences |

### Password & Security

- **Change Password** — Requires your current password. New password must meet strength requirements (minimum 8 characters, including uppercase, lowercase, and digit)
- **Two-Factor Authentication (2FA)** — Add an extra layer of security using an authenticator app
  - Scan the QR code with your authenticator app (Google Authenticator, Authy, etc.)
  - Enter the 6-digit code to verify
  - Save your **8 recovery codes** in a safe place — these are your backup if you lose access to your authenticator
  - Disable 2FA with your password and a verification code
- **Active Sessions** — View all devices where you're logged in
  - See device type, browser, location, and last activity
  - Revoke individual sessions or all other sessions at once

### Notification Preferences

| Setting | Options |
|---------|---------|
| **Email Notifications** | On / Off (global toggle) |
| **In-App Notifications** | On / Off |
| **Digest Frequency** | Instant, Daily, or Weekly |
| **Quiet Hours** | Set a start and end time for no email delivery |
| **Scope** | All, Only Mine, or My Projects |
| **Per-Category Toggles** | Enable/disable email for each notification category |

> **See also:** [Notifications](./notifications.md) for how notifications work

### Account Deletion

Request account deletion under Settings → Account. A 7-day grace period applies before your account is permanently removed. Agency owners must transfer ownership before deleting their account.

---

## Agency Settings

Accessible to **Owners** and **Admins** under **Settings → Agency**.

### Agency Profile

| Setting | Description |
|---------|-------------|
| **Agency Name** | Your agency's display name |
| **Workspace URL** | Your subdomain (e.g., `myagency.eidoncore.com`) |
| **Contact Info** | Email, phone, address |
| **Legal Details** | Legal name, tax ID, tagline |
| **Default Currency** | Currency for new invoices and services (default: USD) |
| **Default Timezone** | Workspace-wide default timezone |

---

## Agency Branding

Customize the look and feel of your entire workspace under **Settings → Agency → Branding**.

### Identity

| Setting | What It Affects |
|---------|----------------|
| **Brand Name** | Displayed in the sidebar and browser title |
| **Logo (Light & Dark)** | Sidebar logo, adapts to dark mode |
| **Favicon** | Browser tab icon |
| **Primary Color** | Buttons, active elements, accents throughout the UI |
| **Secondary Color** | Supporting UI elements |
| **Success / Warning / Danger Colors** | Status indicators and alerts |
| **Font** | Choose from: System, Inter, Poppins, Roboto, or Outfit |
| **Corner Style** | Sharp, Medium, or Rounded (affects all buttons, cards, and inputs) |

### Email Branding

| Setting | What It Affects |
|---------|----------------|
| **Sender Name & Email** | From name and address on all emails |
| **Reply-To Address** | Where replies are directed |
| **Header/Footer Logo** | Logo images in branded emails |
| **Email Signature** | HTML signature appended to emails |
| **Footer Text** | Legal or informational footer |
| **Social Links** | Social media icons in email footer |

### Invoice Branding

| Setting | What It Affects |
|---------|----------------|
| **Invoice Logo** | Logo on generated invoices |
| **Accent Color** | Invoice heading and total amount color |
| **Footer Note** | Legal text on invoices |
| **Bank Details** | Payment information for bank transfers |
| **Payment Instructions** | How-to-pay guidance |
| **Signature Image** | Authorized signature on invoices |
| **Print Settings** | Paper size, show/hide logo, payments, bank details, notes in print |

> **See also:** [Invoicing](./invoicing.md#invoice-branding) for invoice branding details

### Portal Branding

Customize what clients see on the login, register, and portal pages:

| Setting | What It Affects |
|---------|----------------|
| **Login Logo** | Logo on the login page |
| **Portal Accent Color** | Button and link colors on auth pages |
| **Background Image** | Login page background |
| **Headline & Subtext** | Welcome message on the login page |
| **Welcome Message** | Banner shown after clients log in |
| **404 Message** | Custom "page not found" text |
| **Footer Text** | Text at the bottom of auth pages |
| **Hidden Nav Items** | Choose which sidebar items to hide from client users |
| **Default Landing Page** | Where clients land after login |

### White Label

For agencies that want complete branding control:

| Setting | What It Does |
|---------|-------------|
| **Enable White Label** | Removes all platform branding |
| **Custom Page Title** | Override the browser tab title |
| **Hide Platform Name** | Remove "Agency" text from sidebar |
| **Hide Platform Logo** | Remove default logo from sidebar |
| **Hide Footer Credits** | Remove "Powered by" from invoices |
| **Support Email / URL** | Custom support contact details |

---

## Email (SMTP) Setup

Configure email delivery under **Settings → Agency → Email**.

Eidoncore supports these email providers with auto-configuration:

| Provider | Setup |
|----------|-------|
| **Resend** | Enter your API key |
| **Postmark** | Enter your Server Token |
| **SendGrid** | Enter your API key |
| **Mailgun** | Enter SMTP username and password |
| **Emailit** | Enter your username and API key |
| **Custom SMTP** | Enter your server host, port, username, and password |

After configuring, click **"Test Connection"** to send a test email to yourself.

> Email delivery is required for invoice sending, notification emails, digest summaries, and password resets. New workspaces use a platform fallback email provider until you configure your own.

---

## Custom Domains

Add a custom domain to your workspace under **Settings → Agency → Domains**.

### Setup Steps

1. Click **"Add Domain"** and enter your domain (e.g., `app.myagency.com`)
2. Create a **CNAME record** in your DNS pointing to the provided target
3. Click **"Verify"** — the platform checks your DNS and provisions SSL automatically

Once verified, users can access your workspace via your custom domain. Both the custom domain and your subdomain (`slug.eidoncore.com`) continue to work.

---

## Integrations

### Stripe Connect

Connect your Stripe account to accept payments from clients:

1. Go to **Settings → Agency → Integrations → Stripe**
2. Click **"Connect Stripe"** to start the Stripe onboarding flow
3. Complete Stripe's onboarding to enable payouts

Once connected, clients can pay invoices via Stripe, and service purchases use the checkout flow.

### Slack

Send notifications to a Slack channel:

1. Go to **Settings → Agency → Integrations → Slack**
2. Enter your Slack **Incoming Webhook URL**
3. Choose which notification categories to send to Slack

> **See also:** [Notifications](./notifications.md#slack-integration) for more on Slack notifications

---

## Roles & Permissions

Manage roles under **Settings → Agency → Roles & Permissions**.

- View all built-in and custom roles
- Create new custom roles with specific permission sets
- Edit permissions for existing custom roles
- See how many team members are assigned to each role

> **See also:** [Team](./team.md) for detailed role descriptions and permissions

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

> **See also:** [Security](./security.md) for full security details

---

## Audit Log

View a complete log of all actions in your workspace under **Settings → Agency → Audit Log**.

- Filter by action type, actor, or date range
- See what changed (field-level diff), who made the change, and when
- Paginated results (25 entries per page)

---

## Plans & Billing

Manage your subscription under **Settings → Plan & Billing** (Owner only).

### Plan Comparison

| Feature | Free | Pro ($29/mo) | Enterprise ($79/mo) |
|---------|:----:|:---:|:----------:|
| Team Members | 2 | 15 | Unlimited |
| Client Organizations | 3 | 50 | Unlimited |
| Active Projects | 5 | 100 | Unlimited |
| Services | 3 | 30 | Unlimited |
| Automations | 0 | 20 | Unlimited |
| Recurring Invoices | 0 | 20 | Unlimited |
| Intake Forms | 1 | 10 | Unlimited |
| Custom Roles | 0 | 5 | Unlimited |
| File Storage | 500 MB | 10 GB | 100 GB |
| Invoice Reminders (in-app) | ✅ | ✅ | ✅ |
| Invoice Reminders (email) | ❌ | ✅ | ✅ |
| Recurring Invoices | ❌ | ✅ | ✅ |
| Automations | ❌ | ✅ | ✅ |
| Branded Emails | ❌ | ✅ | ✅ |
| Full Branding & Portal Customization | ❌ | ✅ | ✅ |
| Audit Log | ❌ | ✅ | ✅ |
| Health Scoring | ❌ | ✅ | ✅ |
| Custom SMTP | ❌ | ❌ | ✅ |
| Custom Domains | ❌ | ❌ | ✅ |
| White Label | ❌ | ❌ | ✅ |
| Security Policies | ❌ | ❌ | ✅ |

> Annual billing discounts available: Pro at $23/mo, Enterprise at $63/mo.

### Managing Your Plan

- **Upgrade** — Click the upgrade button on any plan to start a Stripe checkout
- **Downgrade** — Changes take effect at the end of your current billing period
- **Cancel** — Schedule cancellation with a reason; you keep access until period end
- **Reactivate** — Reverse a pending cancellation before the period ends
- **Billing Portal** — Manage payment methods, view invoices, and update billing details via Stripe's billing portal
- **Usage Dashboard** — See your current resource usage vs. plan limits
- **Data Export** — Export all agency data as a CSV/JSON bundle

### Plan Status Indicators

| Status | Meaning |
|--------|---------|
| **Active** | Subscription is current and paid |
| **Trialing** | Free 14-day Pro trial — no credit card required |
| **Past Due** | Payment failed — update your payment method (you still have access) |
| **Frozen** | 3+ payment failures — read-only access until payment is resolved |

A global status banner appears (visible to the Owner only) when your plan needs attention.

---

## About / Changelog

View the platform changelog under **Settings → About** to see recent updates, new features, and improvements.
