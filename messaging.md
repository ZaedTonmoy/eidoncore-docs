# Messaging

Real-time chat for your agency team and client contacts. Communicate within project channels, organization-wide channels, and direct messages — all built into your workspace.

---

## Channel Types

Messaging is organized into three types of channels:

| Channel Type | How It's Created | Who Can See It |
|-------------|-----------------|----------------|
| **Project Channel** | Automatically created when a project is created | All project members |
| **Organization Channel** | Automatically created for each client organization | All organization members |
| **Direct Message (DM)** | Started by any user | Only the two participants |

Project and organization channels keep their membership in sync — when a member is added or removed from a project, the channel updates automatically.

---

## Sending Messages

### Composing

Type your message in the input area at the bottom of the chat view. Messages support:

- **Rich text** — formatting for emphasis
- **File attachments** — drag and drop or click to attach files
- **@Mentions** — type `@` followed by a team member's name to mention them
- **Replies** — click the reply button on any message to start a thread

Messages appear **instantly** in the chat (optimistic send) — the message is shown immediately while it saves in the background.

### Editing Messages

You can edit your own messages within a **5-minute window** after sending. After 5 minutes, messages become permanent.

### Deleting Messages

- You can delete your own messages at any time
- Admins and Owners can delete any message

Deleted messages are soft-deleted — they disappear from the chat but are retained briefly for audit purposes.

---

## Reactions

React to any message with an emoji. Click the 😊 button that appears when you hover over a message to open the emoji picker.

- **One reaction per person per message** — selecting a new emoji replaces your previous reaction
- Click your existing reaction again to remove it
- The message author is notified when someone reacts to their message

---

## Typing Indicators

When someone is composing a message in the same channel, you'll see a **"{Name} is typing..."** indicator with animated dots below the message list. The indicator disappears after 3 seconds of inactivity.

---

## Read Receipts

Sent messages show **read receipts** — small avatar circles at the bottom-right corner of your messages, similar to Facebook Messenger. These show which channel members have read up to that message.

Hover over the avatars to see "Seen by {Name}".

---

## Unread Indicators

Stay on top of conversations with multiple unread indicators:

| Indicator | Where | What It Shows |
|-----------|-------|---------------|
| **Channel badge** | Channel list sidebar | Unread flag on channels with new messages |
| **Sidebar badge** | Messages nav item | Count of channels with unread messages (1–9, 9+) |
| **Favicon dot** | Browser tab icon | Colored dot using your agency's brand color |

All indicators update automatically in the background.

---

## Internal Messages

In project and organization channels, you can mark messages as **internal**:

- Internal messages are visible **only to agency staff** — client contacts in the channel won't see them
- This lets you discuss work privately within a shared channel
- Internal messages are not available in Direct Messages

---

## Direct Messages

Start a private conversation with any workspace member:

1. Click the **search/new DM** field in the messaging sidebar
2. Search for a team member by name
3. Click their name to open or create a DM channel

DMs are always between exactly two people. Existing DM channels appear in your channel list for quick access.

> **Note:** Client contacts cannot DM other client contacts — DMs are only between agency staff, or between agency staff and client contacts.

---

## File Attachments

Attach files to messages by dragging and dropping onto the chat view or using the attach button.

Supported file types include images, documents, PDFs, spreadsheets, archives, and media files (30+ file types).

Maximum attachment size depends on your plan:

| Plan | Max Attachment Size |
|------|:------------------:|
| **Free** | 5 MB |
| **Pro** | 10 MB |
| **Enterprise** | 25 MB |

---

## Message Actions

Hover over any message to see the action bar with quick buttons:

| Action | What It Does |
|--------|-------------|
| 😊 **React** | Add an emoji reaction |
| ↩️ **Reply** | Start a threaded reply |
| ⋮ **More** | Edit (own, within 5 min), Delete |

On mobile, **swipe right** on a message to reply.

---

## Plan Limits

Messaging features scale with your subscription plan:

| Resource | Free | Pro | Enterprise |
|----------|:----:|:---:|:----------:|
| Channels | 10 | 50 | Unlimited |
| Members per channel | 10 | 30 | Unlimited |
| Message retention | 30 days | 90 days | Unlimited |
| Max attachment size | 5 MB | 10 MB | 25 MB |

> **See also:** [Settings](./settings.md#plans--billing) for plan details

---

## Notifications

You'll receive notifications for key messaging events:

| Event | Who Gets Notified |
|-------|-------------------|
| @mentioned in a message | Mentioned user |
| Reply to your message | Original message author |
| Reaction to your message | Message author |

### Chat Digest

If you've been away for more than 10 minutes, an **hourly chat digest email** summarizes any unread messages across your channels. This runs in addition to your regular notification digest.

> **See also:** [Notifications](./notifications.md) for notification preferences · [Settings](./settings.md#notification-preferences) for digest settings

---

## Permissions

| Permission | What It Allows | Default Roles |
|-----------|---------------|---------------|
| **View Messages** | See messages in channels you're a member of | All roles |
| **Send Messages** | Post messages and attachments | All roles |
| **Delete Any Message** | Delete messages from any user | Owner, Admin |
| **Manage Channels** | Create and configure channels | Owner, Admin |
| **Browse All Channels** | See all channels in the workspace | Owner, Admin |

> **See also:** [Team](./team.md) for configuring role permissions · [Projects](./projects.md) for project channel membership · [Client Portal](./client-portal.md) for client messaging access
