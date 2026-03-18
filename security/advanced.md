---
title: "Advanced Security"
description: "Monitor security events, understand data isolation, and learn about threat protection."
---

## Security Events

Your security event history tracks authentication-related actions:

| Event | When It's Logged |
|-------|------------------|
| **Login successful** | Each time you log in |
| **Login failed** | Failed login attempt |
| **Password changed** | Password updated |
| **2FA enabled** | Two-factor authentication turned on |
| **2FA disabled** | Two-factor authentication turned off |
| **Re-authentication passed** | Sensitive action password re-entry successful |
| **Recovery codes regenerated** | New backup codes generated |
| **Security policy changed** | Org-wide security settings updated |

Each event records the **IP address** and **browser/device** used. View your security events under **Settings → Account → Security**.

---

## Data Isolation Between Workspaces

Each agency workspace is completely isolated:

- All data is scoped to your organization — no data is shared between workspaces
- Even if the same email address is used across multiple agencies, profile data (name, avatar) is independent per workspace
- Client data, projects, tasks, invoices, and all other records are strictly separated

---

## Protection Against Common Threats

The platform includes built-in protection against:

<ExpandableGroup>
<Expandable title="Authentication Attacks">

| Threat | Protection |
|--------|-----------|
| **Brute Force Attacks** | Rate limiting: 5 login attempts per minute per email, 3 password resets per 10 minutes |
| **Session Hijacking** | Secure, HTTP-only cookies with hostname scoping (no cross-subdomain leaking) |
| **Man-in-the-Middle** | HSTS headers enforcing HTTPS (1-year max-age) |

</Expandable>
<Expandable title="Injection & Forgery">

| Threat | Protection |
|--------|-----------|
| **Cross-Site Scripting (XSS)** | Server-side HTML sanitization + Content Security Policy (CSP) headers |
| **Cross-Site Request Forgery (CSRF)** | Origin header validation with fail-closed policy |
| **Content Injection** | All user-generated HTML sanitized at save-time |

</Expandable>
<Expandable title="Infrastructure">

| Threat | Protection |
|--------|-----------|
| **DNS Spoofing** | DNS-over-HTTPS verification for custom domains |
| **Clickjacking** | X-Frame-Options: DENY |

</Expandable>
</ExpandableGroup>

---

## Custom Domain Security

If you use a custom domain, sessions are automatically scoped to prevent cross-domain leaking:

- **Subdomain access** (`slug.eidoncore.com`) — Sessions are shared across your workspace subdomains
- **Custom domain access** (`app.youragency.com`) — Sessions are scoped to the exact hostname

DNS verification uses secure DNS-over-HTTPS to prevent spoofing.

> **See also:** [Settings](./settings#custom-domains) for setting up custom domains · [Settings](./settings#security-policies) for configuring security policies
