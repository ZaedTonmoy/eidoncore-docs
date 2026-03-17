# Tasks

Tasks are the building blocks of project work. Assign them to team members, organize them with labels and checklists, track time, and collaborate through comments.

---

## Task Views

Tasks can be viewed in multiple ways:

| View | Best For |
|------|----------|
| **Kanban Board** | Visual workflow — drag and drop tasks between status columns |
| **List View** | Detailed table with sorting, filtering, and drag-and-drop between status groups |
| **Workload View** | See task distribution, capacity levels, and overdue counts per team member |

Switch between views using the view toggle at the top of the tasks page.

### Task Analytics Strip

Above the task list, a quick-reference analytics strip shows:

| Metric | What It Shows |
|--------|--------------|
| **Active** | Total active tasks (not Done) |
| **Overdue** | Tasks past their due date |
| **Due Today** | Tasks due today |
| **Due This Week** | Tasks due within 7 days |
| **Completed This Week** | Tasks marked Done in the last 7 days |
| **Avg. Completion Time** | Average time from created to Done |
| **Completion Rate** | Percentage of all-time tasks that are Done |

---

## Creating & Editing Tasks

### Task Fields

| Field | Description |
|-------|-------------|
| **Title** | Short, descriptive name |
| **Description** | Rich text details and context |
| **Status** | To Do, In Progress, In Review, Done |
| **Priority** | Low, Medium, High, Urgent |
| **Assignee** | Who is responsible for this task |
| **Project** | Which project this task belongs to |
| **Milestone** | Optional milestone within the project |
| **Due Date** | When the task is due |
| **Estimated Hours** | Planned effort |
| **Labels** | Color-coded tags for categorization |
| **Tags** | Free-form text tags for flexible categorization beyond labels |
| **Complexity** | Optional complexity score for estimation and prioritization |
| **Billable** | Whether time logged on this task counts as billable (default: yes) |

### Task Drawer

Click any task to open the **Task Drawer** — a slide-out panel for editing all task details, viewing comments, attachments, checklists, time entries, and the activity log.

### Activity Log

Every task keeps a detailed **activity log** showing all changes: creation, status changes, comments, time entries, reassignments, and more. Each entry records who made the change and when. View the log in the Activity tab of the task drawer.

---

## Task Statuses

By default, tasks flow through four statuses:

| Status | Meaning |
|--------|---------|
| **To Do** | Not yet started |
| **In Progress** | Actively being worked on |
| **In Review** | Completed work awaiting review |
| **Done** | Finished |

Drag tasks between columns on the Kanban board, or change the status dropdown in the task drawer.

### Custom Statuses

Each project can define its own task statuses to match your workflow. Click the **gear icon** on the project's task board to open the Status Manager, where you can:

- **Create** new statuses with a custom name and color
- **Rename** existing statuses
- **Reorder** statuses via drag-and-drop (this changes the column order on the Kanban board)
- **Delete** statuses — you'll be prompted to reassign any tasks using that status
- **Mark as closed** — closed statuses (like "Done") indicate completed work

New projects are automatically seeded with the four default statuses. Custom statuses are scoped per project — they don't affect other projects.

---

## Task Health

Each task is automatically assessed for health based on its due date, dependencies, and activity:

| Indicator | Condition |
|-----------|-----------|
| ● **On Track** | On schedule, no issues |
| ● **At Risk** | Due within 2 days and still in To Do |
| ● **Overdue** | Past due date and not completed |
| ● **Blocked** | Waiting on a dependency that isn't done |
| ○ **Stale** | No updates for 3+ days while still active |
| ✓ **Completed** | Task is Done |

Health is evaluated in order of severity: Completed → Overdue → Blocked → At Risk → Stale → On Track.

Health indicators appear on the task card and in the task drawer.

---

## Subtasks

Break large tasks into smaller **subtasks**. Subtasks are full tasks linked to a parent task:

- Each subtask has its own status, assignee, and due date
- The parent task shows subtask completion progress
- When a subtask is marked Done, the parent task's assignee and creator are notified

---

## Checklists

Add a checklist to any task for a quick to-do list:

- Check off items as they're completed
- Checklist items support **nesting** — add sub-items under any checklist item for multi-level checklists
- A **checklist progress bar** shows the completion percentage on every task card
- When **all items** are checked, the task assignee and creator are notified
- Great for multi-step processes that don't need full subtasks

---

## Dependencies

Link related tasks with dependencies to define the order of work:

| Dependency Type | Meaning |
|----------------|---------|
| **Blocking** | This task must be completed before the linked task can start |
| **Blocked By** | This task is waiting on another task |

Dependencies help visualize the flow of work and identify bottlenecks.

> **Note:** A task cannot be marked as Done if it has unfinished dependencies. Complete the blocking tasks first.

---

## Labels

Create color-coded **labels** to categorize tasks across projects:

- Labels are shared across your workspace
- Assign multiple labels to a single task
- Filter tasks by label in both list and Kanban views

---

## Time Tracking

### Live Timer

Start a timer directly from the task drawer. The timer runs until you stop it, at which point a time entry is automatically created.

### Manual Entry

Log time manually by entering the duration, description, and optionally marking it as billable.

Time logged on a task by someone other than the assignee triggers a notification to the assignee.

> **See also:** [Projects](./projects#time-tracking) for project-level time tracking · [Services](./services#hours--credits-tracking) for service hour deductions · [Reports](./reports) for time reports

---

## Comments & Collaboration

### Adding Comments

Leave comments on tasks to discuss work, ask questions, or share updates.

- **Internal comments** are only visible to agency staff (not visible to client users in the portal)
- **Standard comments** are visible to everyone with access to the task

### Threaded Replies

Reply directly to a comment to keep conversations organized in threads.

### @Mentions

Type `@` followed by a team member's name to mention them. They'll receive a notification linking directly to the comment.

### Reactions

React to comments with emojis for quick feedback — 👍, ❤️, 😂, 🎉, 🤔, 👀, 🚀, and more.

The comment author is notified when someone reacts to their comment.

> **See also:** [Notifications](./notifications) for comment and mention notifications

---

## Task Sharing

Share a task externally using a **public share link** — anyone with the link can view the task details without logging in.

Toggle the share link on or off from the task drawer.

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
