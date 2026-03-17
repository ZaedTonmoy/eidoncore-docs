---
title: "Pricing & Quotas"
---

Configure pricing models for your services and manage hours/credits tracking with automatic quota management.

---

## Pricing Models

Eidoncore supports 5 pricing models to fit different agency service types:

| Model | How It Works | Example |
|-------|-------------|---------|
| **One-Time Fixed** | Single flat fee for a deliverable | Website redesign — $5,000 |
| **Recurring Monthly** | Ongoing subscription (monthly, quarterly, or yearly) | SEO retainer — $2,000/mo |
| **Hourly Rate** | Bill per hour worked | Consulting — $150/hr |
| **Hourly Block** | Prepaid block of hours per period | Support package — 20 hours/mo |
| **Credit Pack** | Prepaid credits for work units | Design credits — 100 credits/mo |

### Billing Configuration

Each service specifies:

- **Billing type**: One-Time, Recurring, or Usage-Based
- **Billing interval**: Monthly, Quarterly, or Yearly (for recurring)
- **Billing mode**: Manual or Stripe (for automated payment collection)

---

## Included Hours & Credits

For Hourly Block and Credit Pack services:

| Setting | Description |
|---------|-------------|
| **Included Hours / Credits** | Amount included per billing period |
| **Rollover Policy** | None (reset each period), Capped, or Unlimited |
| **Expiry Days** | Number of days before unused hours/credits expire |
| **Minimum Billable Increment** | Smallest time unit for billing (e.g., 15 minutes) |
| **Overtime Rate** | Hourly rate charged when included hours are exceeded (for Hourly Block services) |

### Quota Top-Ups

When a client's included hours or credits are running low, additional quota can be added:

<Tabs>
  <Tab title="Agency-Side" icon="building">

**Immediate top-up** — On the project's quota section, click **"+ Add Quota"** to add hours, credits, or tasks directly.

- Top-ups are added to a separate top-up balance that carries over indefinitely (regular renewals only reset the base balance)
- Not available for Usage-Based services

  </Tab>
  <Tab title="Client-Side" icon="user">

**Request & Approve Flow:**

<Steps>
  <Step title="Client requests" icon="plus-circle">
    On their project page, clients click **"Request Top-Up"** and enter the desired amount
  </Step>
  <Step title="Agency reviews" icon="eye">
    The request appears as **Pending** — the agency owner can **Approve** or **Reject** it
  </Step>
  <Step title="Client pays" icon="credit-card">
    If approved, the client sees a **"Pay"** button that redirects to Stripe checkout
  </Step>
  <Step title="Balance updated" icon="check-circle">
    After payment, the top-up balance is updated immediately
  </Step>
</Steps>

  </Tab>
</Tabs>

Both agency and client can view the full **top-up history** on the project, showing each entry's amount, status (Pending, Approved, Paid, Rejected), and date.

---

## Hours & Credits Tracking

### Hours Tracking

For services with included hours (Hourly Block):

- When time is logged against a service assignment, the remaining hours balance is automatically reduced
- If time entries are deleted, the balance is restored
- When all hours are depleted, the agency owner and client contacts are notified
- If a recurring subscription's auto-renewal payment fails, the service status changes to **Past Due**

### Credits Tracking

For credit-based services (Credit Pack):

- Credits are tracked via a **ledger** system
- Credit entries can be: **Add** (initial or top-up), **Spend** (work performed), or **Adjust** (manual correction)
- Each entry includes the amount, reference type, and a note
- When all credits are depleted, the agency owner and client contacts are notified

### Service Assignment Statuses

| Status | Meaning |
|--------|---------|
| **Pending** | Just purchased, awaiting setup |
| **Active** | Currently in use |
| **Paused** | Temporarily suspended |
| **Past Due** | Auto-renewal payment failed |
| **Cancelled** | Terminated by the client or agency |
| **Completed** | One-time service delivered |

---

## Quota Management on Projects

When a project is linked to a service, the project page shows real-time quota information:

### Quota Progress Bar

| Display | Meaning |
|---------|---------|
| **Green** | Normal usage — plenty of balance remaining |
| **Amber** | Over 75% consumed |
| **Red** | Over 90% consumed or fully exhausted |

The progress bar shows remaining allocation (e.g., "15 / 20 hours remaining"). Top-up balances are displayed as a separate segment.

### Quota Exhaustion Guard

<Callout kind="alert">
When a service's quota is fully consumed, the **"+ New Task"** button on the project is **disabled**. A tooltip explains that the quota is exhausted. Agency owners can bypass this restriction.
</Callout>

### Complete & Invoice (One-Time Projects)

For one-time service projects, a **"Complete & Invoice"** button appears in the project header. Clicking it:

1. Automatically stops all running timers on the project
2. Sweeps all unbilled time entries into a **draft invoice**
3. Marks the project as **Completed**

### Time Entry Behaviors

When time is logged against a service with included hours:

- Time is split into **regular** (within balance) and **overtime** (beyond balance) minutes
- The hourly rate and overtime rate are **snapshotted** at the time of logging — changes to the service rate don't retroactively affect past entries
- Once a time entry is **billed** (linked to an invoice), it becomes **immutable** and cannot be edited or deleted
- **Written-off** entries (agency comp) are excluded from invoice totals

<Callout kind="info">
When a time entry is deleted (before being billed), the consumed balance is automatically restored.
</Callout>

---

## Cancelling a Subscription

When a subscription is cancelled (by the client or agency):

<Steps>
  <Step title="Timers stopped" icon="clock">
    Any **active timers** are automatically stopped
  </Step>
  <Step title="Closing invoice" icon="file-text">
    All **unbilled time entries** are swept and added to a closing draft invoice
  </Step>
  <Step title="Status updated" icon="x-circle">
    The subscription status changes to **Cancelled** with a reason recorded
  </Step>
  <Step title="Notifications sent" icon="bell">
    The agency Owner and Admin are notified
  </Step>
</Steps>

### Auto-Renewal

Recurring subscriptions automatically renew at the end of each billing period:

- The saved payment method is charged off-session
- On success, the billing period extends by one month and included hours/credits reset
- On failure, the subscription moves to **Past Due** status and both parties are notified
- The `autoRenew` toggle can be managed from the subscription settings
