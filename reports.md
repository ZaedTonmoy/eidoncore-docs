# Reports & Dashboards

Monitor your agency's performance with real-time dashboards and detailed reports across revenue, clients, projects, tasks, and time tracking.

---

## Executive Dashboard

Available to **Owners**, **Admins**, **Project Managers**, **Accountants**, and **Team Members**, the executive dashboard is your command center.

### Revenue KPIs

| Metric | What It Shows |
|--------|--------------|
| **Total Revenue** | Sum of all invoiced amounts (with period comparison) |
| **Outstanding** | Total unpaid across all invoices |
| **Overdue** | Unpaid invoices past their due date |
| **Monthly Recurring Revenue (MRR)** | Revenue from active recurring invoice templates |

### Project Overview

- Active project count
- Project health breakdown (on track / at risk / off track)
- Projects by status

### Team Workload

- Tasks per team member
- Capacity overview
- Who's overloaded, who has availability

### Recent Activity

A timeline of the latest actions across your workspace.

### Dashboard Alerts

Real-time alert banners appear at the top of the dashboard when action is needed:

#### Critical Alerts

| Alert | Trigger |
|-------|---------|
| **Overdue Invoices** | Any invoice with overdue status |
| **Critical Projects** | Projects with "Off Track" health score |
| **Failed Automations** | Automation failures in the last 7 days |
| **Failing Subscription Renewals** | Client subscriptions with "Past Due" status |

#### Warning Alerts

| Alert | Trigger |
|-------|---------|
| **Stale Tasks** | Tasks overdue for more than 3 days |
| **Expiring Contracts** | Client contracts expiring within 30 days |

#### Info Alerts

| Alert | Trigger |
|-------|---------|
| **Inactive Clients** | Clients with no activity for more than 30 days |
| **Unassigned Tasks** | More than 5 active tasks with no assignee |

Click any alert to navigate to the relevant page. Dismiss alerts with the ✕ button — they'll reappear on your next visit if the underlying condition persists.

---

## Team Member Dashboard

A focused view for individual contributors showing:

- Tasks assigned to you and their statuses
- Projects you're a member of
- Your recent activity and upcoming deadlines

---

## Client Dashboard

For client portal users (Organization Owner/Organization Member):

- Project progress bars and health scores
- Task breakdown by status (To Do, In Progress, In Review, Done)
- Recent invoices with status, total, and amount due — plus summary of total billed, paid, and outstanding
- Active services with pricing details
- Upcoming milestones and task deadlines in the next 7 days
- Recent activity scoped to your organization

> **See also:** [Client Portal](./client-portal.md) for the full client experience · [Dashboard](./dashboard.md) for detailed dashboard documentation

---

## Reports

Navigate to **Reports** in the sidebar to access detailed analytics.

### Revenue Report

| Metric | Description |
|--------|-------------|
| **Revenue Over Time** | Monthly/quarterly revenue trends |
| **Revenue by Client** | Which clients generate the most revenue |
| **Revenue by Service** | Which services are most profitable |
| **Outstanding vs. Collected** | Revenue collection efficiency |
| **Forecast** | Projected revenue for upcoming periods |

### Client Report

| Metric | Description |
|--------|-------------|
| **Total Clients** | Active client count |
| **Client Acquisition** | New clients over time |
| **Client Revenue Distribution** | Revenue breakdown by client |
| **Client Health Overview** | Health status across all clients |
| **Top Clients** | Highest revenue clients |

### Project Report

| Metric | Description |
|--------|-------------|
| **Active Projects** | Current project count by status |
| **Project Health** | Health distribution across all projects |
| **Completion Rate** | Percentage of projects completed on time |
| **Budget Utilization** | How projects are tracking against their budgets |
| **Projects by Client** | Project distribution across clients |

### Task Report

| Metric | Description |
|--------|-------------|
| **Task Completion** | Tasks completed over time |
| **Tasks by Status** | Distribution across statuses |
| **Overdue Tasks** | Count and age of overdue tasks |
| **Tasks by Assignee** | Workload per team member |
| **Average Completion Time** | How long tasks take to complete |

### Time Tracking Report

| Metric | Description |
|--------|-------------|
| **Hours Logged** | Total time logged over a period |
| **Billable vs. Non-Billable** | Ratio of billable to non-billable time |
| **Time by Project** | Where time is being spent |
| **Time by Team Member** | Individual contribution breakdown |
| **Utilization Rate** | Billable hours as a percentage of total hours |

### Date Range Filtering

All reports support date range filtering:
- Preset ranges: **7 days**, **30 days**, **90 days**, **12 months**, **All time** (default: 30 days)
- Period-over-period comparisons

---

## Client Reports (Organization Owner)

Organization Owners see a separate set of 3 report tabs, automatically scoped to their organization:

### Overview Tab

| Element | Type |
|---------|------|
| Active Projects | KPI — count of active projects |
| Task Completion | KPI — completion percentage |
| Overdue Tasks | KPI — count of overdue tasks |
| Avg Turnaround | KPI — average days from task creation to completion |
| Hours Invested | KPI — total hours logged by agency team |
| Outstanding | KPI — outstanding invoice amount |
| Total Spent | KPI — combined invoice payments + service purchases |
| Project Health | Donut chart — On Track, At Risk, Off Track |
| Task Status | Donut chart — Done, In Progress, To Do, In Review |

### Projects & Tasks Tab

| Element | Type |
|---------|------|
| Total / Active / Completed Projects | KPIs |
| Total Tasks / Completion Rate / In Progress | KPIs |
| Project Status | Donut chart — Not Started, In Progress, Completed |
| Task Priority | Donut chart — High, Medium, Low, Urgent |
| Task Completion Trend | Bar chart — monthly completed tasks |
| Project Health | Donut chart |
| Tasks by Agency Member | Table — member, total, done, in progress, overdue, completion % |

### Team Activity Tab

| Element | Type |
|---------|------|
| Team Members | KPI — count of agency members on your projects |
| Total Hours | KPI — hours logged by agency team |
| Avg Turnaround | KPI — average task completion time |
| Hours by Team Member | Bar chart |
| Task Priority Distribution | Donut chart |
| Agency Team Performance | Table — member, tasks, completed, in progress, overdue, completion % |

> **Note:** Organization Members do not have access to Reports. Only Organization Owners can view the report tabs scoped to their organization.

---

## Permissions

| Permission | What It Allows |
|-----------|---------------|
| **View Reports** | Access all report pages |
| **Export Reports** | Download reports as CSV or PDF |

Available to: Owner, Admin, Project Manager, and Accountant by default. Team Members have limited access.

> **See also:** [Invoicing](./invoicing.md#finance-analytics-dashboard) for the detailed finance dashboard · [Projects](./projects.md#project-health) for health scoring · [Clients](./clients.md#client-health-scoring) for client health analytics
