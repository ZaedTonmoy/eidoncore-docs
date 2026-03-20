---
title: "Task Basics"
description: "View tasks in Kanban, list, or workload view, create and edit tasks, and manage statuses and labels."
---

Tasks are the building blocks of project work. Assign them to team members, organize them with labels and checklists, track time, and collaborate through comments.

---

## Task Views

Tasks can be viewed in multiple ways:

| View | Best For |
|------|----------|
| **Kanban Board** | Visual workflow — drag and drop tasks between status columns |
| **List View** | Detailed table with sorting, filtering, and drag-and-drop between status groups |
| **Workload View** | See task distribution, capacity levels, and overdue counts per team member |

Switch between views using the view toggle at the top of the tasks page. Your selected view persists via the URL — refreshing the page keeps you on the same view.

### Column Settings (List View)

In List view, click the **⚙ Columns** button to choose which columns are visible. Toggle columns on or off to customize your view:

- Title (always visible)
- Priority, Health, Assignee, Due Date, Created, Updated, Project

Your column preferences are saved per browser and shared across the global Tasks page and project task lists.

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

### Deferred Task Creation

When you click **"+ New Task"**, a title input appears first — the task is only created in the database after you provide a real title and press `Enter`. Press `Escape` to cancel without creating anything.

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

## Labels

Create color-coded **labels** to categorize tasks across projects:

- Labels are shared across your workspace
- Assign multiple labels to a single task
- Filter tasks by label in both list and Kanban views

> **See also:** [Keyboard Shortcuts](../keyboard-shortcuts#tasks-page) for task keyboard shortcuts

---
