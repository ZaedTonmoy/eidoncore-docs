# Intake Forms

Collect project requirements, preferences, and onboarding information from clients automatically after they purchase a service. Build custom forms with a drag-and-drop builder and assign them to any service in your catalog.

---

## How Intake Forms Work

The intake form system follows a simple flow:

1. **You create a form** with the questions you need answered
2. **You assign the form** to one or more services
3. **A client purchases the service** through the catalog
4. **The client fills out the form** on the purchase confirmation page
5. **Responses are saved** as a pinned document in the auto-created project
6. **You're notified** when a submission comes in

---

## Creating a Form

Navigate to **Intake Forms** in the sidebar (under Tools) and click **"New Form"**.

### Form Details

| Field | Description |
|-------|-------------|
| **Name** | Form title (e.g., "Website Project Intake") |
| **Description** | Instructions shown to the client before filling out the form |
| **Fields** | The questions and inputs your client will complete |
| **Active** | Toggle the form on or off without deleting it |

### Adding Fields

Use the drag-and-drop field builder to add questions. Each field has:

| Property | Description |
|----------|-------------|
| **Label** | The question text shown to the client |
| **Type** | What kind of input to collect (see below) |
| **Required** | Whether the client must answer this question |
| **Placeholder** | Hint text shown inside the input |

### Supported Field Types

| Type | What It Collects | Input Control |
|------|-----------------|---------------|
| **Text** | Short text response | Single-line text input |
| **Textarea** | Long text response | Multi-line text area |
| **Email** | Email address | Email input with validation |
| **Phone** | Phone number | Phone number input |
| **URL** | Web link | URL input with validation |
| **Number** | Numeric value | Number input |
| **Select** | Choice from a list | Dropdown with custom options |
| **Checkbox** | Yes/no answer | Checkbox toggle |

For **Select** fields, add the dropdown options when creating the field.

---

## Assigning Forms to Services

Each intake form can be assigned to **one or more services**. When creating or editing a form, check the services you want to associate with it.

- One form can serve multiple services (e.g., a general onboarding form)
- Each service can only have one intake form
- Removing a form from a service doesn't delete the form — it just unlinks them

> **See also:** [Services](./services.md#intake-forms) for how intake forms fit into the service workflow

---

## Client Experience

After purchasing a service that has an assigned intake form, the client sees the form on the **purchase confirmation page**:

1. A form card appears with the form name and description
2. The client fills in the required and optional fields
3. On submit, a success message confirms the submission
4. The form disappears from the confirmation page after submission

Clients can only submit each form once per purchase — the form won't appear again after submission.

---

## What Happens After Submission

When a client submits an intake form:

1. **A project document is created** — Responses are formatted into a readable HTML document and saved as a **pinned document** in the project that was auto-created for the service
2. **A submission record is saved** — Linking the response data to the form, project, and submitter
3. **The agency owner is notified** — A notification is sent so you can review the responses immediately

---

## Managing Intake Forms

The Intake Forms page lets you manage all your forms in one place:

| Action | Description |
|--------|-------------|
| **View all forms** | See each form's name, field count, submission count, and assigned services |
| **Create forms** | Build new forms with the drag-and-drop builder |
| **Edit forms** | Update questions, reorder fields, and change service assignments |
| **Delete forms** | Remove forms (unlinks from all services first) |
| **View submissions** | See the last 50 submissions for each form |

### Who Can Access Intake Forms

| Role | Can Access |
|------|:----------:|
| Owner | ✓ |
| Admin | ✓ |
| Project Manager | ✓ |
| Accountant | ✗ |
| Team Member | ✗ |
| Organization Users | ✗ |

Intake Forms is a **Pro plan** feature. On the Free plan, the sidebar item shows a lock badge. Clicking it shows an upgrade prompt.

---

## Notifications

| Event | Who Gets Notified |
|-------|-------------------|
| Intake form submitted | Agency owner |

> **See also:** [Services](./services.md#intake-forms) for service integration · [Projects](./projects.md#project-documents) for where submissions are saved · [Settings](./settings.md#plans--billing) for plan features
