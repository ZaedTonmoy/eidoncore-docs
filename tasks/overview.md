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

<Callout kind="tip">
Your column preferences are saved per browser and shared across the global Tasks page and project task lists.
</Callout>

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

## Sections & Lists

Organize tasks within a project using a **Section → List** hierarchy. Sections act as folders, and each list contains its own group of tasks with an independent status pipeline.

```
Project
├── Section (folder)
│   ├── List
│   │   ├── Task
│   │   └── Task
│   └── List
├── List (top-level, no section)
└── Tasks (project root — no list)
```

### Key Concepts

| Concept | Description |
|---------|-------------|
| **Sections** | Folders that group related lists. Strictly flat — no nested sections. Deleting a section moves its lists to the top level. |
| **Lists** | Each list has its own tasks and an independent status pipeline. Deleting a list moves its tasks to the project root. |
| **Project Root** | Tasks with no list assignment appear in the "All Tasks" view. |

### List-Specific Status Pipelines

Each list gets its own set of task statuses, copied from the project's statuses when the list is created. This means different lists can have completely different workflows:

- **Design List** → Concept → Wireframe → Review → Approved
- **Development List** → Backlog → In Progress → Testing → Done

### Cross-List Task Moves

When you move a task between lists, if its current status doesn't exist in the destination list, it's automatically **remapped to the default status** of the new list.

### Sidebar Navigation

The project sidebar shows a collapsible tree of Sections → Lists:

- **Create** sections and lists inline from the sidebar
- **Rename or delete** via right-click context menu
- **Reorder** sections and lists with drag-and-drop
- **Move lists between sections** by dragging a list onto a different section header
- **Collapsed mode** — icon-only sidebar rail (56px) with tooltips for compact navigation
- **Mobile** — slide-over sheet on small screens

### URL Deep Linking

Selecting a list sets `?list={listId}` in the URL. Links are bookmarkable and shareable — opening the link auto-switches to the Tasks tab with the correct list selected.

### Grouping Options

In the "All Tasks" view (no specific list selected), you can toggle **Group by: Status or List** in the filter bar. This groups your tasks by their parent list instead of status, giving you a cross-list overview.

<Callout kind="info">
Lists are gated by your plan. Each plan defines a maximum number of lists per project (default: 3). Existing projects without lists continue to work unchanged.
</Callout>

---

## Labels

Create color-coded **labels** to categorize tasks across projects:

- Labels are shared across your workspace
- Assign multiple labels to a single task
- Filter tasks by label in both list and Kanban views

> **See also:** [Keyboard Shortcuts](../keyboard-shortcuts#tasks-page) for task keyboard shortcuts

---
