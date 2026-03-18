---
title: "Branding & Email"
description: "Customize your agency branding, configure SMTP email, and set up custom domains."
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

> **See also:** [Invoicing](../invoicing/analytics#invoice-branding) for invoice branding details

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

<Callout kind="info" collapsed="true" title="White Label Settings">
For agencies that want complete branding control:

| Setting | What It Does |
|---------|-------------|
| **Enable White Label** | Removes all platform branding |
| **Custom Page Title** | Override the browser tab title |
| **Hide Platform Name** | Remove "Agency" text from sidebar |
| **Hide Platform Logo** | Remove default logo from sidebar |
| **Hide Footer Credits** | Remove "Powered by" from invoices |
| **Support Email / URL** | Custom support contact details |

</Callout>

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

<Steps>
<Step title="Add your domain" icon="globe">
Click **"Add Domain"** and enter your domain (e.g., `app.myagency.com`)
</Step>
<Step title="Configure DNS" icon="server">
Create a **CNAME record** in your DNS pointing to the provided target
</Step>
<Step title="Verify" icon="check-circle">
Click **"Verify"** — the platform checks your DNS and provisions SSL automatically
</Step>
</Steps>

Once verified, users can access your workspace via your custom domain. Both the custom domain and your subdomain (`slug.eidoncore.com`) continue to work.

---
