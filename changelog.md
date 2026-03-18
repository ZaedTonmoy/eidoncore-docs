---
title: "Changelog"
description: "All notable changes, new features, improvements, and bug fixes across every Eidoncore platform release."
---

All notable changes to the EidonCore platform.

<Update label="2026-03-14" description="v8.3.0 — Performance Boost & Modular Architecture" tags={["Performance", "Billing", "Tasks"]}>

> Server-side caching for branding and config data, composite database indexes for faster queries, ~300KB bundle reduction via dynamic imports, service query pagination, and modular component architecture across the organization, service, invoice, and dashboard pages.

### 🚀 New
- Server-side branding cache — branding data cached with 5-min TTL and tag-based invalidation, eliminating redundant DB lookups on every page load

### ✨ Improved
- Organization page modularized — split into 6 focused tab components (Overview, Notes, Communications, Documents, Settings, Contacts) for faster rendering
- Component architecture overhaul — icons, project tabs, service builder, and intake form builder split into focused modules for better code organization
- Service list pagination — service queries now bounded to prevent slow unbounded fetches on large catalogs
- ~300KB bundle reduction — jsPDF dynamically imported only when generating invoice PDFs instead of loaded on every page
- 3 composite database indexes — Task (assignee + status), Notification (user + read state), OrgService (org + status) for faster filtered queries
- Task status config caching — lookups now use server-side cache with tag-based invalidation instead of per-request DB queries

</Update>

<Update label="2026-03-12" description="v8.2.0 — Digital Products Sales Tracker, Invoice PDF & Org Self-Service" tags={["Billing", "Services", "CRM"]}>

> New digital products Sales Tracker with sortable table and slide-out management panel, proper PDF invoice email attachments, styled confirmation dialogs replacing browser prompts, organization self-service member management, chat member panel with auto-join, and invoice preview enhancements.

### 🚀 New
- Digital Products Sales Tracker — dedicated page with MRR, revenue, active sales, and churn stats cards, status filter pills, search, and sortable table (A-Z/Z-A on all 7 columns)
- Sale Detail Panel — slide-out drawer for managing digital product sales: change status, fulfillment, dates (styled DatePicker), auto-renew toggle, internal notes, intake form display, and sale timeline
- Invoice PDF attachment — emails now include a proper PDF invoice instead of an HTML file, generated via jsPDF with accurate layout matching the print template
- Styled confirmation dialogs — replaced all native browser confirm() prompts with a polished modal component across the entire app
- Organization self-service member management — org owners can now invite, edit roles, and remove their own team members
- Chat member panel — view channel members in messaging, with org contacts auto-joined to project channels on link
- Multi-page invoice preview — InvoicePreview now shows page break indicators for long invoices and scales to 1:1 match with the print version
- Auto-sync showPoweredBy and hideFooterCredits toggles for consistent branding control

### ✨ Improved
- Internal note toggle hidden from organization users — only agency staff can see the internal note option in messaging
- Invoice email subject now uses the client company name for easier identification
- Invoice signature field and logo positioning — logo moved to billed-from position, signature line added to preview and print

### 🐛 Fixed
- Organization page tabs no longer invisible — fixed min-height and CSS scoping issues
- Team sidebar item and restricted pages now properly hidden from organization roles with page-level access guards
- Print dialog title shows invoice number instead of generic 'Dashboard'
- Preserve newlines in agency address on invoice preview and print
- PDF logo format — WebP and SVG logos automatically converted to PNG for PDF compatibility
- showPoweredBy toggle now respected in print invoice view

</Update>

<Update label="2026-03-10" description="v8.1.0 — Live Messaging, Reactions, Read Receipts & Real-Time UX" tags={["Mobile", "Notifications", "Messaging"]}>

> Complete real-time messaging system — live chat via Pusher Channels, message reactions & thread replies, Facebook-style read receipts, typing indicators, optimistic message sending, unread badges (sidebar + favicon dot), inline DM search, notification grouping, settings search, reports UX upgrade, and mobile responsive layouts.

### 🚀 New
- Live Messaging (Phases 1–8) — real-time chat via Pusher Channels with private/presence channels, channel sync, DM finder, message retention cron, chat digest emails, plan gating, and 90-day retention
- Message reactions — emoji reaction bar with one-per-user swap logic, hover action bar (😊 react, ↩️ reply, ⋮ more), and click-to-open emoji picker
- Thread replies — reply-to with swipe gesture, reply preview in chat, and CHAT_REPLY notifications
- Facebook-style read receipts — tiny avatar circles at bottom-right of your sent messages showing who's seen them, readReceipts tRPC query with 10s polling
- Typing indicator — 'Name is typing...' with animated dots, client-typing Pusher events with 2s throttle, auto-clear after 3s
- Optimistic message sending — messages appear instantly (opacity 0.6), matched by clientId on server confirmation, ~200ms perceived send time
- Favicon unread dot — branded primary-color dot overlay on tab favicon using 32×32 canvas, polls in background even when tab is inactive
- Sidebar unread badge — count pill next to Messages nav item (expanded: number badge, collapsed: dot), globalUnreadCount query with background polling
- Inline DM search — replaced '+New DM' button with search box that filters existing channels and shows DM candidates
- @mention autocomplete — type @ in chat to see org member suggestions with avatar and name
- Drag-and-drop file uploads — drop files anywhere in the chat area to attach
- Settings search — deep keyword search across 13 settings pages with 200+ terms, flash-highlight on navigate, collapsible plan table
- Reports page UX upgrade — tooltips, data caching, CSV export, KPI trends
- Mobile responsive CSS — kanban board, filter bar, and table layouts adapt to small screens
- Integrations hub — refactored sub-pages pattern for Stripe and Slack integrations with search routing
- Bell notification on onboarding completion

### ✨ Improved
- Fire-and-forget message send — notifications, Pusher broadcast, and unread updates run in background for instant response
- Notification grouping — CHAT_REPLY and CHAT_REACTION now grouped by type + same day (batch threshold ≥2)
- Auto-focus message input — editor focuses on channel load and reply click for instant typing
- Bell notification deep links — clicking a chat mention notification navigates directly to the mentioned channel

### 🐛 Fixed
- Fix React hooks violation — globalUnreadCount query moved before early return in Sidebar (rules of hooks)
- Fix favicon distortion — use fixed 32×32 canvas to prevent SVG natural dimension stretch
- Fix message order — newest messages now correctly at bottom, oldest at top
- Fix full page scroll on messages — constrain chat panel height
- Fix unread badge clearing + send button active state
- Fix sender's channel showing unread after sending own message
- Fix emoji picker z-index stacking on column-reverse layout
- Fix bubble squeeze — 65% max-width with proper action bar positioning
- Fix agency security page infinite loading for PM role
- Scope settings audit log by role — team members see only their own changes

</Update>

<Update label="2026-03-07" description="v8.0.0 — Service Pricing Engine, Quota System & Catalog Redesign" tags={["Major Update", "Tasks", "Services"]}>

> Major release — complete service pricing architecture overhaul with 4 quota types (Standard, Time-Based, Credit-Based, Usage-Based), dual-ledger quota engine with 105 edge cases covered, inline task creation pattern, field tooltips and conditional form logic, slug availability checking, and a premium catalog service page redesign with glass cards, animations, and gallery lightbox.

### 🚀 New
- 4 Quota Types — STANDARD (task count), TIME_BASED (hours with overtime), CREDIT_BASED (credits per task), USAGE_BASED (metered billing) with full lifecycle support including rollover, expiry, and top-ups
- Dual-ledger quota engine — base balance + top-up balance with SELECT...FOR UPDATE row-locking, Stateful Ledger Memory (deductedFromBase/deductedFromTopUp stamps), and atomic spillover deduction
- Inline task creation — '+ New Task' now instantly creates a task and opens the full TaskDrawer with comments, reactions, attachments, and activity. TaskCreateDrawer deprecated
- Quota top-ups — manual top-ups for agency/org owners with QuotaTopUp model, Stripe webhook handler (fulfillQuotaTopUp), state-machine idempotency, and separate balance columns
- Time entry overtime split — splitTimeEntryMinutes() calculates regularMinutes/overtimeMinutes with billedHourlyRate/billedOvertimeRate snapshotted onto each TimeEntry for invoice accuracy
- USAGE_BASED auto-invoicing — renewals cron generates DRAFT invoices with usage line items at period end, sweeps unbilled TIME_BASED overtime entries, and stamps entries with invoiceId
- Cancellation final invoice sweep — auto-stops running timers, sweeps unbilled USAGE_BASED + TIME_BASED overtime, generates closing DRAFT invoice before setting CANCELLED status
- Config snapshot isolation — 12+ fields snapshotted from Service to OrgService at purchase time, so agency template changes never affect active client contracts
- Project quota status bar — visual progress bar in project OverviewTab showing base + top-up usage for all 4 quota types, with '+ New Task' disabled when quota exhausted
- Gallery lightbox — click-to-open full-screen lightbox on catalog service page with blur backdrop, prev/next navigation arrows, and close button
- Slug availability check — real-time debounced (500ms) slug uniqueness validation in the Service Builder with ✅/❌ indicators and clickable suggestions for conflicts
- Convert catalog gallery from grid to responsive slider
- Phase 1 catalog detail enhancements
- Add reusable demo services seed script
- Guest cart for public visitors
- Make pricing card '+N more included' clickable to expand all deliverables
- Add Enterprise plan lock overlay to SMTP settings page
- Add Email Logo upload to Brand Identity tab

### ✨ Improved
- Catalog service page premium redesign — taller hero with gradient overlay and frosted-glass category pill, content cards with staggered fade-in animation, gradient accent section titles, deliverable hover highlights, animated FAQ accordion, review cards with accent border
- Pricing sidebar upgrade — gradient stripe header, elevated shadow, structured detail rows for included hours/credits, shimmer CTA button on hover, active subscriber and in-cart badges
- Service Builder tooltips — explanatory FieldHint tooltips on all pricing and quota fields with contextual descriptions and profit calculation examples
- Conditional form fields — Included Hours shown only for TIME_BASED/USAGE_BASED, Included Credits only for CREDIT_BASED, Max Rollover Periods only for CAPPED rollover, Credits Per Task only for CREDIT_BASED
- Shared service-utils.ts — extracted 13 helper functions from 6 duplicate locations into a single shared module with backward compatibility for both pricingModel and billingType/quotaType
- Automation quota gate — automation engine's create_task action now routes through checkAndDeductQuota(), preventing unlimited task creation that bypassed tRPC quota gate
- Renewals cron upgraded — migrated from hardcoded RECURRING_MONTHLY to billingType: RECURRING, added rollover logic per RolloverPolicy, dual-sweep for USAGE_BASED + TIME_BASED overtime
- Harden admin panel — strip spoofable header + enforce 2FA at tRPC level
- Deduplicate email sender fields — SMTP page is single source

### 🐛 Fixed
- Fixed Lazarus re-activation exploit — isRefunded flag prevents refunded tasks from being re-activated without re-checking quota
- Fixed subtask promotion bypass — parentTaskId null transitions now run checkQuota() to prevent creating free subtasks then promoting to root-level
- Fixed billed time immutability — timeEntryUpdate and timeEntryDelete throw FORBIDDEN if invoiceId is set, preventing modification of invoiced entries
- Fixed active timer ghost on cancel/pause — auto-stops all running timers (endTime: null) when OrgService status transitions to PAUSED or CANCELLED
- Hero quote picks best review (highest rated + has comment + newest)
- CTA button - remove icon, solid color using branding var(--accent-primary)
- Related services grid stretches to fill width (auto-fit)
- PublicCategoryList now includes _count for published+public services
- Darken hero overlay for better text readability on cover images
- Center FAQ collapse minus icon in pill toggle
- Admin sidebar not loading on login + block /admin on non-admin subdomains
- Use hard navigation after admin login to force layout re-render
- Sidebar logo now reactively switches on theme toggle
- Use live DB query for SMTP plan gate instead of stale session JWT
- Add programmatic file type validation to ImageUpload component

</Update>

<Update label="2026-02-19" description="v7.6.0 — Intake Form Builder v2 — Multi-Page, Repeater & Preview" tags={["Major Update", "Projects", "Services"]}>

> Major intake form upgrade — multi-page forms with step wizard, repeater/group fields with dynamic rows, full-screen preview modal, public catalog redesign with share links and SEO, and field type expansion to 27 types.

### 🚀 New
- Multi-page intake forms — add pages via page tabs in the builder; clients see a step wizard with numbered indicators, Previous/Next navigation, and per-page validation
- Repeater / Group fields — new field type for repeatable data (e.g. team members, project phases); clients can dynamically add and remove rows, each with configurable sub-fields
- Form Preview modal — full-screen preview in the builder showing exactly how clients will see the form, with multi-page navigation and all 27 field types rendered
- Public service catalog redesign — refreshed catalog grid with share links, SEO metadata (title, description, Open Graph), and improved service detail pages
- Restructure intake forms - page-based builder, 18 field types, draft support

### ✨ Improved
- Expanded to 27 field types — all types now fully rendered on the client success page, in the form preview, and in the generated HTML document (buildIntakeDocHtml)
- All icons now use proper SVG components from the icon library — replaced 25+ emoji and inline SVG instances with consistent IconX, IconEye, IconStar, etc.
- Uplift intake form builder UI - premium visuals

### 🐛 Fixed
- Fixed API field type validation — Zod enum was limited to 18 types, silently rejecting forms with newer field types like address, currency, toggle, color_picker, and slider
- Fixed repeater data display in generated documents — submitted repeater rows now render as a clean nested table in the HTML document
- Sidebar cutoff, button consistency, branding vars + add conditional logic
- Sidebar lifts off bottom when scrolling - remove alignSelf flex-start
- Sidebar gap at bottom when scrolling - split into outer wrapper + inner sticky
- Move bottom padding from flex parent to canvas only - fixes sidebar gap

</Update>

<Update label="2026-02-14" description="v7.5.1 — Kanban Redesign, Task Drag-and-Drop & Custom Statuses" tags={["Major Update", "Billing", "Tasks"]}>

> Visual Kanban board overhaul with shadow cards and priority badges, drag-and-drop task reordering in list view, project-scoped custom task statuses, guest checkout for public catalog, and invoice discount safety.

### 🚀 New
- Kanban board redesign — shadow-elevated cards with colored status pills, priority badges, progress bars, project names, due date pills, grip handles, and card overflow menu
- Task list drag-and-drop — drag tasks between status groups in the grouped list view with full-row drag overlay, scroll position preservation, and optimistic updates
- Project-scoped custom task statuses — define custom status columns per project with drag-and-drop reordering on the Kanban board
- Guest checkout — public catalog now supports purchases without requiring login, streamlining the client onboarding flow
- Kanban card context menu — right-click or overflow menu on cards for quick actions

### ✨ Improved
- Tasks view mode persists via URL hash (#board, #list, #workload) — survives page reloads and browser back/forward
- Service gallery — extracted shared ServiceBuilderForm component with image gallery support on the service detail page

### 🐛 Fixed
- Fixed discount safety — fixed discounts now clamped to prevent negative invoice totals
- Fixed duplicate file entries and enforced storage quota limits on all upload paths
- Fixed pricing validation blocking progression and cover image display issues in service builder

</Update>

<Update label="2026-02-12" description="v7.5.0 — Typography Refactor & SF Pro Display Default Font" tags={["Major Update", "UI/UX"]}>

> Comprehensive typography standardization across the entire codebase — replaced 1,476 inline font declarations with CSS design tokens, introduced utility classes, and switched the default system font from Plus Jakarta Sans to SF Pro Display.

### 🚀 New
- SF Pro Display is now the default system font — loaded via @font-face (Regular 400, Medium 500, Bold 700) with system-ui fallback. Replaced Plus Jakarta Sans (Google Fonts).
- Admin direct password change + impersonation token-based auto-login
- KanbanBoard visual redesign — shadow cards, progress bars, project names, priority icons, date pills, column add-task button
- Persist Tasks view mode in URL hash (#board, #list, #workload) — survives page reload
- Add drag-and-drop to GroupedTaskList — drag tasks between status groups in list view
- Add platform admin security log page
- Add functional kanban card context menu & polish board icons
- Project-scoped task statuses with optimistic DnD
- Guest checkout flow for public catalog

### ✨ Improved
- Typography design tokens — 17 font-size tokens (--text-2xs through --text-7xl), 5 font-weight tokens (--fw-normal through --fw-extrabold), 3 letter-spacing tokens, and 26 utility classes in globals.css
- Full inline style tokenization — converted 985 inline fontSize declarations and 491 inline fontWeight declarations to CSS variable references across 82+ TSX files
- Letter-spacing standardization — unified all letter-spacing values from pixel units to em units across dashboard and admin CSS
- Extract shared CreateOrganizationModal component
- Extract shared ServiceBuilderForm + add gallery to detail page

### 🐛 Fixed
- Fixed non-standard font-weight: 650 to 700 in .svc-card-title and font-size: 12.5px to 13px in .svc-card-desc
- Fixed bare-number letterSpacing values (e.g. 0.5 → '0.04em') that browsers could misinterpret as pixel values
- KanbanBoard card refinements — task title on top, always-show progress/counts/menu
- Make progress bar track visible at 0% — use border-primary instead of bg-tertiary
- Drag overlay now renders full card instead of partial 3-row preview
- List view drag overlay shows full row — title, priority, assignee, due date, status
- Preserve scroll position after drag-and-drop in list view — await refetch + double-rAF
- Capture scroll position before drag mutation — use ref for reliable scroll preservation
- Re-enable autoScroll for list DnD + capture/restore scroll in handleDragEnd to prevent jump
- Use table-layout:fixed on grouped task list — aligns columns across all status groups
- Clamp fixed discounts to prevent negative invoice totals
- Duplicate file entries, storage quota enforcement, and doc updates
- Pricing validation blocks progression + cover image display

</Update>

<Update label="2026-02-02" description="v7.4.0 — Invoice Form Redesign — Live Preview, Edit Parity & Print Template" tags={["Major Update", "Billing", "UI/UX"]}>

> Redesigned invoice creation with a 55/45 form+preview split layout, live A4-proportioned preview panel, unified edit page, aligned line-item sub-rows, and pixel-perfect print template matching the preview.

### 🚀 New
- Live invoice preview — InvoicePreview component shows a real-time A4-proportioned mirror of the invoice form with accent-colored headers, dashed dividers, and branded footer

### ✨ Improved
- Invoice form layout — 55/45 split with consolidated 'Details' card on the left and sticky preview panel on the right
- Edit Invoice parity — edit page now mirrors the new invoice form exactly with same layout, preview, and compact styling
- Line item alignment — Tax % label and input split into separate grid columns aligning perfectly with Qty and Price fields above
- Print template redesign — PrintableInvoice rewritten with identical inline styles as InvoicePreview for pixel-perfect matching when printing

### 🐛 Fixed
- Fixed edit invoice crash — added missing totals, billToCompany, billToAddress, and paymentTerms props to InvoicePreview
- Fixed extra blank page in print — removed spacer div that pushed content past A4 boundary
- Sidebar display name duplication, dashboard greeting uses live profile, mobile header layout

</Update>

<Update label="2026-01-30" description="v7.3.0 — Dashboard Greeting Enhancements & Daily Motivational Quotes" tags={["Tasks", "Analytics", "UI/UX"]}>

> Time-aware greeting with contextual icons, daily motivational quotes that rotate through 345+ curated entries, and polished header layout with quote and greeting side-by-side.

### 🚀 New
- Daily motivational quotes — 345 curated business, productivity, and inspirational quotes displayed on the dashboard, rotating daily with a year-shifted pattern so the same date never shows the same quote across years

### ✨ Improved
- Time-aware greeting — dashboard now shows 'Good Morning' (before noon), 'Good Afternoon' (noon–5 PM), or 'Good Evening' (after 5 PM) with matching sun/moon icon
- Dashboard header layout — motivational quote displayed on the left side of the info bar alongside the greeting on the right, with prominent italic styling
- Page component — description prop now accepts ReactNode for custom styling; non-detail pages render description and actions side-by-side in a horizontal bar

### 🐛 Fixed
- Removed tinted background color from project page summary card icons for visual consistency
- Build error — getDashboardStats → getOverview + docs updates

</Update>

<Update label="2026-01-28" description="v7.2.0 — Bug Reports Button, Tasks Filter Bar & UI Polish" tags={["Security", "Tasks", "Analytics"]}>

> Restored missing Report a Bug button on the bug reports page, moved the List/Board/Workload view toggle into the tasks filter bar alongside filters and New Task, and fixed several layout and overflow issues.

### 🚀 New
- Add PlatformAdmin dashboard (Phase 1 — read-only)
- Phase 2 — administrative actions
- Phase 3 — impersonation via signed redirect URL
- Phase 4 — Revenue & Analytics + Onboarding Insights
- Mandatory 2FA with 3-day grace period
- Phase 6 — Bug Report System
- Phase 6b — Bug Report Notifications (bell + email)
- Phase 6c — Screenshot capture in bug reports
- Global Bug Report FAB — floating bug button on all pages
- Bug report notifications clickable — navigate to /bug-reports/[id]
- 2FA setup countdown banner in admin panel
- Add image upload to BugReportFAB
- Add all platform admin notification triggers
- Auto-include full page URL in bug reports (strip query params for privacy)
- Auto-prefix https:// on website/URL fields
- Bulk actions on admin agencies page

### ✨ Improved
- Tasks page — moved List/Board/Workload view toggle into the filter bar on the same line as search, filters, and '+ New Task' button
- Tasks page — '+ New Task' button now uses compact sizing to match the other buttons in the filter bar
- Unify bug report modals — page & FAB now share the same BugReportModal

### 🐛 Fixed
- Bug Reports page — restored the '+ Report a Bug' button in the page header (was missing due to a rendering issue with the Page component)
- Bug Reports — status dropdown on the last row no longer goes off-screen; it now opens upward when near the bottom of the viewport
- Bug Reports — sort icons now display beside column headings instead of below them
- Isolate PlatformAdmin auth from per-agency passwords
- Verify Now button — wrong PlatformAdminLog fields
- Replace browser confirm() with inline confirmation for Verify Now button
- Admin.eidoncore.com — use NEXT_PUBLIC_APP_DOMAIN in Edge middleware
- Admin.eidoncore.com 'Workspace Not Found' — login page didn't exclude admin subdomain
- BugReportFAB modal stays centered after screenshot, add close X button
- Submit button always visible in BugReportFAB modal — disabled state uses opacity instead of transparent bg
- Replace emoji icons with SVG icons in contact modal
- Restructure admin layout — bell in header, user info in sidebar footer
- Add debug logging to bugReport notification catch + cleanup
- Make invoice rows clickable on org detail page → navigates to /invoices/:id

</Update>

<Update label="2026-01-16" description="v7.1.0 — Monetization Fixes, Consolidated Invoice Settings & UI Polish" tags={["Security", "Billing", "Notifications"]}>

> Aligned monetization plan data with spec, merged duplicate Invoice Settings into Branding, removed misleading email badge, and relocated team invite button to filter bar.

### 🚀 New
- Replace all alert() with showToast() toast notifications
- Email-confirmed agency registration + workspace-not-found
- Enforce branded email PRO+ gate & portal branding PRO+
- 7-day unverified agency cleanup + 2-min resend cooldown
- Add 'Change email' option on registration check-email screen
- Move 2FA fields to OrganizationMember for per-tenant isolation

### ✨ Improved
- Plan settings page — updated all plan cards and comparison table to match platform_monetization.md spec (corrected team members, storage, services, automations, intake forms)
- Consolidated Invoice Settings — merged the standalone Invoice Settings page into the Branding → Invoices tab, eliminating 4 duplicate fields and adding Print & Display Options section (show/hide logo, payment history, bank details, notes + paper size)
- Team page — moved 'Invite Member' button from page header into the filter bar (right-aligned) with UserPlus icon, matching the Projects page pattern
- Removed misleading 'Email Unverified' badge from profile page — email verification is handled at the organization level, not per-user
- Updated platform_monetization.md — documented intakeForms limits, serviceTemplates, fullBranding flags, and corrected exportData description
- Scope session cookie per-subdomain — remove shared .eidoncore.com domain
- Fix cross-tenant password leakage in authorize + settings

### 🐛 Fixed
- Fixed FREE plan automations limit — was 1, now correctly set to 0 per spec
- Added intakeForms checkLimit enforcement — intake form creation now respects FREE:1 / PRO:10 / ENTERPRISE:∞ limits
- Fixed sidebar lock icon — replaced emoji with proper IconLock SVG component
- File downloads — add Supabase to CSP, force download disposition, error handling
- Cross-tenant profile data isolation via per-membership overrides
- Sidebar live-updates after profile save + per-agency profile isolation
- Per-agency password consistency across all password flows
- Set per-agency nickname on team invite and client invite memberships
- Per-agency password for reauth + mfaDisable; update all docs
- Clarify addContact comment — membership created in resendContactInvite
- Wrap login page useSearchParams in Suspense boundary for build
- Validate subdomain slug matches session in dashboard layout — prevent cross-subdomain auto-login
- Set invoiceReminders=true for FREE plan, update docs
- Consistent action button placement in filter bar across tasks, projects, organizations
- Tenant isolation sweep — scope dashboard queries by organizationId
- Scope resolveOrgScope userId lookup + getSecurityEvents by organizationId
- Scope file operations in project.ts by organizationId
- Scope email-digest cron by organizationId per membership
- Scope exportAccountData and requestAccountDeletion to current org
- Close 5 remaining v2 audit tenant isolation gaps
- Scope team.ts getWorkload assignedTasks by organizationId
- Align plan data with spec, enforce intakeForms limit, use IconLock SVG

</Update>

<Update label="2026-01-03" description="v7.0.0 — Redesigned Headers, Cleaner Settings & Sidebar Polish" tags={["Major Update", "Billing", "Settings"]}>

> Major UI overhaul — simplified settings page, more compact sidebar, redesigned page headers that align with the sidebar, and consistent styling across all pages.

### 🚀 New
- Password toggle, folder icon, trial banner fix, file upload fix
- Show trial days on plan page, always show trial banner, sidebar avatar
- Improve Files page UI, fix delete modal
- Add detailed plan comparison table to Plan & Billing page
- Flat file list with filter sidebar, remove confusing folder hierarchy
- Add bulk download button for selected files
- Add styled file type icons (PDF/DOC/XLS/generic) to icons.tsx and FileThumbnail

### ✨ Improved
- Simplified the Settings page — removed redundant settings cards since buttons for each setting already exist in the sidebar
- More compact sidebar — tightened spacing between menu items to feel cleaner and match the settings sidebar style
- Redesigned page headers — headers are now minimal with only the page title, shopping cart, and notification bell
- Headers now perfectly align with the sidebar logo section — the divider line runs straight across for a polished, consistent look
- Action buttons (like 'New Project' and 'Add Organization') moved from the header into the filter bar alongside search and filters
- Header shows a subtle border line at rest, which smoothly transitions to a shadow when you scroll — giving a cleaner feel
- Standardized button sizes across Organizations and Projects pages for visual consistency
- View toggle icons (grid/list) on Projects page now use proper icons from the icon library instead of inline SVGs, matching the style of other filter icons
- Remove redundant settings cards grid, keep audit trail as landing page content
- Compact main sidebar — tighter padding, smaller font, reduced section gaps
- Minimal page headers — smaller title, white bg, scroll shadow, info bar for detail pages

### 🐛 Fixed
- Fixed view toggle icons showing reversed colors — default and hover states were swapped
- Show actual upload error message for debugging
- Remove test script breaking build
- Sidebar flex-direction column for vertical filter stacking
- Download button now triggers real file download instead of opening in new tab

</Update>

<Update label="2025-12-26" description="v6.9.0 — Platform Monetization — Subscription Billing, Plan Gating & Security Hardening" tags={["Security", "Billing", "Services"]}>

> Full platform monetization system with FREE/PRO/ENTERPRISE tiers, Stripe subscription billing, plan-gating middleware, quantity limits, billing lifecycle management, global status banners, and comprehensive security hardening across auth, rate limiting, and encryption.

### 🚀 New
- 3-tier subscription plans (FREE/PRO/ENTERPRISE) — self-serve Stripe Checkout with monthly and annual pricing, 14-day PRO trial for new agencies
- Plan management page — Settings → Plan with tier comparison cards, usage bars, upgrade/downgrade flow, billing portal link, billing history, and data export
- requirePlan() middleware — 16 plan gates across 10 routers blocking feature access by tier (PRO+ for recurring invoices, automations, reports; ENTERPRISE for SMTP, domains, impersonation)
- checkLimit() enforcement — 9 quantity limits (team members, clients, projects, services, automations, recurring invoices, custom roles, intake forms, storage) with live COUNT queries
- 5 Stripe webhook handlers — checkout.session.completed, subscription.updated, subscription.deleted, invoice.paid, invoice.payment_failed with plan status sync and pausedBySystem management
- Plan status lifecycle — ACTIVE → PAST_DUE → FROZEN with global PlanStatusBanner (amber warning for payment issues, red critical for frozen accounts)
- Billing sync cron — daily Stripe subscription reconciliation and trial expiry enforcement with automatic downgrade to FREE
- 5 plan notification types — PLAN_UPGRADED, PLAN_DOWNGRADED, PLAN_PAYMENT_FAILED (P1 critical), PLAN_CANCELLATION_SCHEDULED, PLAN_TRIAL_ENDING with icons and email deep-links
- Sidebar plan badges — 🔒 lock icon on Reports, Automations, and Intake Forms for agencies below required tier
- Soft downgrade behavior — existing data never deleted, excess automations and recurring invoices auto-paused with pausedBySystem flag, auto-restored on re-upgrade
- Branding field stripping — updateBranding silently strips tier-restricted fields (portal/white-label for non-ENTERPRISE, email/invoice for FREE) instead of blocking
- Cancel with reason tracking — 6 structured reasons (too expensive, missing features, switching competitor, business closed, temporary pause, other) with reactivation before period end

### ✨ Improved
- Security hardening — rate limiting on registration/login/2FA, AES-256-GCM encryption for SMTP passwords and 2FA secrets, HMAC-signed impersonation cookies, timing-safe cron secret comparison
- Password strength enforcement — minimum 8 chars with uppercase, lowercase, number, and special character required on registration, change password, and contact password reset
- Contact invite security — cryptographically random passwords with password-reset-link flow replacing hardcoded temporary passwords
- Fix 9 audit findings (IDOR, XSS, open redirect, email escaping)

### 🐛 Fixed
- Fixed TRIALING missing from PlanStatus enum — registration would fail when setting planStatus to TRIALING
- Fixed webhook planStatus sync — handleSubscriptionUpdated now correctly maps Stripe subscription status (active/past_due/canceled/trialing) to internal PlanStatus
- Fixed PlanStatusBanner CTA — 'Upgrade' button now correctly links to /settings/plan instead of /billing
- Security hardening and domain management improvements
- Custom domain DNS verification, routing, auth cookies, and docs

</Update>

<Update label="2025-12-18" description="v6.8.0 — Task Assignment Emails, Team Invitations & Agency Name in Sidebar" tags={["Tasks", "Projects", "Team"]}>

> Rich task assignment email on drawer close, branded team invitation email with password-setup link and workspace URL, and agency name now displays in sidebar from registration.

### 🚀 New
- Task assignment email — rich branded email sent on TaskDrawer close with task title, description, priority badge, due date, project, and direct link to the task
- Team invitation email — branded email with inviter name, agency name, role, workspace URL (custom domain if available), and a 'Set Your Password' button for new users
- Agency name now appears in the sidebar — registration sets brandName from organizationName so agencies see their real name instead of 'Agency'
- Limit changelog notifications to 7-day rolling window
- Service slug-based URLs, edit multi-step form, fix Save & Continue icon

### ✨ Improved
- Notification docs reorganized — task assignment email documented as 'Rich Email Supplement' alongside the existing bell notification
- HTML sanitization added to task description on create, update, public share, and assignment email rendering

### 🐛 Fixed
- Handle FK errors in notification changelog dismissal gracefully
- Multi-tenant auth — subdomain-aware login, tRPC context validation, forgot-password routing
- SignOut uses redirect:false + manual redirect to stay on agency subdomain
- Defer task_created automation + notification for placeholder tasks, fix record payment modal overlay

</Update>

<Update label="2025-12-14" description="v6.7.0 — Multi-Tenant Workspaces — Subdomains, Onboarding & Welcome Emails" tags={["Tasks", "Projects", "Settings"]}>

> Full subdomain-based tenant resolution with automated provisioning, post-registration onboarding questionnaire, workspace finder, welcome emails with SMTP fallback, wildcard domain support, and logout fix for agency portals.

### 🚀 New
- Subdomain-based tenant resolution — each agency gets its own subdomain (agency.eidoncore.com) with middleware slug extraction via x-workspace-slug header
- Automated subdomain provisioning — registration auto-creates Cloudflare CNAME + Vercel domain for each new agency workspace
- Post-registration onboarding questionnaire — 5-step animated survey (team size, agency type, experience, tools, referral source) with progress bar and auto-advance
- Workspace finder page — register.eidoncore.com/find-workspace lets users look up their agency URL by email
- Welcome email on registration — branded email sent to agency owner with workspace URL and getting started tips
- Platform-level SMTP fallback — agencies without custom SMTP config fall back to platform-wide SMTP settings for transactional emails
- Wildcard domain support — Vercel Pro wildcard domain (*.eidoncore.com) for instant subdomain resolution without per-subdomain DNS setup
- Clickable AUTOMATION_FAILED notifications → edit modal
- Add 4 new dashboard alert types + dashboard alerts documentation
- Sync account page tabs with URL hash (#subscriptions, #payments, #billing)
- Add email notifications (instant + digest + per-category control)
- Implement provider-specific SMTP support (SendGrid, Postmark, Mailgun, Resend, Emailit)
- Wire sendInvoice to actually send email via SMTP
- Add resend invitation email button to organization contacts tab
- Add forgot-password flow with branded reset email, HMAC tokens, and login link

### ✨ Improved
- Onboarding icons migrated from emojis to inline SVG components in icons.tsx for consistent styling across all themes
- Replace automation modal with page-based create/edit
- Use IconEmail/IconNotifications from global icons file

### 🐛 Fixed
- Fixed register.eidoncore.com routing — middleware now correctly rewrites register subdomain requests to the /register path
- Fixed cross-subdomain session cookie — session now persists across agency subdomains with .eidoncore.com domain cookie
- Fixed Vercel CNAME target — auto-provisioning now uses project-specific CNAME target instead of generic cname.vercel-dns.com
- Fixed logout redirect — signing out now returns to the current agency's login page instead of always redirecting to app.eidoncore.com
- Fixed invite modal role dropdown — now shows placeholder text while roles are loading instead of empty state
- Wrap otplib.verifySync in try/catch for recovery code login
- Create_comment automation action validates required fields
- Deduplicate saved cards on billing tab & show saved cards at checkout
- Move Invoices to Finance section, remove Cart from sidebar (header has CartButton)
- Remove custom save-card checkbox — Stripe CustomerSession handles it natively
- Complete remaining email notification items
- Add 14 missing notification categories to settings UI + update docs
- Add paymentFailed to Org Owner notification visibility
- Email toggle icon no longer overlaps main toggle
- Move email/bell icons to column headers above toggles
- Use title child element instead of title prop on SVGs
- Enlarge column header icons (20px) and align to toggle columns
- Move invoice email sending to correct procedure (invoice.send)
- Add resend invite button inside ContactProfileModal
- Send invite for no-account contacts, remove redundant button for existing accounts, update docs
- Show temp password only for new accounts, existing users see forgot-password link
- Wrap reset-password page in Suspense for Next.js 16 build
- Use CSS variable overrides for branding color on auth pages to prevent flash

</Update>

<Update label="2025-11-29" description="v6.6.0 — Automation Engine — Full Wiring & UI Upgrade" tags={["Billing", "Notifications", "Tasks"]}>

> Fixed 4 critical automation engine bugs, wired executeAutomations() into all 6 routers (11 triggers), added edit modal and enhanced execution logs with expandable detail rows and filtering, and added config forms for all 7 action types.

### 🚀 New
- AUTOMATION_FAILED notifications — P1 critical notification fired to agency owners when the automation engine encounters an error, bypassing digest and quiet hours
- Automation engine wiring — executeAutomations() now called from task, invoice, project, client, comment, and team routers as fire-and-forget (11 triggers total)
- Edit automation modal — 'Edit' button on each automation card opens pre-populated modal with name, description, trigger, and action config; saves via update mutation
- Enhanced execution logs — expandable rows showing error messages, action results, and trigger payloads; filter by status (All/Success/Failed) and by automation
- Harden agency catalog model — strip internal data, add CTA, fix visibility
- Shared PageLayout template — enhance Page.tsx, migrate orgs & projects list
- Migrate org detail page to shared Page component with breadcrumb, tabs, headerMeta
- Match catalog filters to services page — category pills + filter bar
- Add missing catalog features — links section, pricing model badge, included hours/credits
- Add seed-catalog-content script — 10 demo services with full catalog data
- Clickable active service cards + RichTextEditor for review form
- Redesign cart success page + add service/cart notifications
- Add My Account page for org owner/member roles
- Add Stripe saved payment methods to My Account
- Subscription cancellation with reason + agency notification
- Complete branding system — portal tab, audit fixes, docs
- Email SMTP transport + branding polish
- Allow re-purchasing active services + use logo as favicon fallback
- Optional save-card checkbox + subscription auto-renewal cron
- Add Intake Forms feature — schema, backend, frontend, docs

### ✨ Improved
- Action config forms for all 7 types — added UI fields for send_email (to/subject/body), update_task_status (status dropdown), update_project_status (status dropdown), and log_activity (message)
- Execution log limit increased from 20 to 50 for better debugging visibility
- Uplift service catalog card design — better spacing, hover effects, mobile proportions
- Catalog detail page — proper padding, hero margins, pricing card polish, mobile fixes
- Remove Reports Billing tab, enhance My Account with full spending

### 🐛 Fixed
- Fixed automation log status enum mismatch — changed from 'FAILURE' to 'FAILED' to match AutomationStatus enum
- Fixed send_notification action — now uses createNotification() helper with organizationId, cooldown, priority tiers, and Slack integration
- Fixed send_email action — now uses sendBrandedEmail() with organization SMTP settings and graceful fallback when SMTP is not configured
- Client catalog shows all published services, not just assigned ones
- Block client roles from internal /services management page
- Use SERVICES_CREATE/EDIT permission check instead of isRestrictedUser
- Catalog detail page works for services without slugs
- Project detail mobile header broken after Page migration
- Show notification bell on mobile detail headers (inline, no flex-grow)
- Scroll listener uses window fallback for mobile header collapse
- Eliminate header collapse flickering — hysteresis + grid-row transition
- Use display:none for header extras collapse — eliminates white space
- Review form layout — proper flex-column structure with labeled fields
- Seed script targets correct org via owner email instead of findFirst()
- Hide project creation UI from org roles
- Migrate Stripe Connect from OAuth to API-based Express onboarding
- Remove invalid Stripe API version + update docs
- Remove audit log from callback route (foreign key violation on userId: system)
- Pass stripeAccountId to Elements provider for Connect direct charges
- Keep cart visible during checkout by including CHECKOUT status in queries
- Make Stripe payment element theme-aware for light/dark mode
- Include CHECKOUT status in all cart mutations (addItem, removeItem, clear)
- TS build error (undefined in Tab bg) + cart orderBy for consistency
- Remove invalid COMPLETED enum value from OrgService queries
- Wrap OrgService spending query in try-catch, use select instead of include
- DatePicker positioning flash on first click after page load
- Remove setup_future_usage to hide Stripe save-card consent text
- Terms.card expects string not object for PaymentElement
- Eliminate branding FOUC with localStorage cache + blocking inline script
- Hide sidebar logo/name during hydration to prevent FOUC
- Add sidebar skeleton to prevent nav items loading in stages
- Prevent white flash when dark mode is active on page refresh
- 2FA login flow, addContact password overwrite, auth docs
- Prevent favicon reverting to default on client-side navigation

</Update>

<Update label="2025-11-07" description="v6.5.0 — Intake Forms — Client Onboarding Data Collection" tags={["Tasks", "Projects", "Services"]}>

> Custom intake forms that agency owners can create and assign to services. Clients fill them post-purchase on the success page, generating a pinned project document for the team.

### 🚀 New
- Intake Form builder — standalone /intake-forms page with drag-reorderable fields, 8 field types (text, textarea, email, phone, URL, number, dropdown, checkbox), required/optional toggle, and placeholder text
- Service assignment — assign one form to multiple services via checkbox selection; form auto-appears on the success page after purchase
- Success page integration — IntakeFormSection renders dynamically after the 'What happens next' stepper for services with assigned forms; validates required fields before submission
- Auto-generated ProjectDoc — form submission creates a pinned document in the project with formatted HTML table of all responses
- Submission tracking — IntakeFormSubmission model records who submitted, when, and links to the generated ProjectDoc

### ✨ Improved
- Sidebar gating — Intake Forms menu item visible only to Agency Owner, Admin, and Project Manager via SERVICES_EDIT or SERVICES_VIEW_ALL permissions
- Owner notification — agency owner receives INTAKE_FORM_SUBMITTED notification when a client completes an intake form

</Update>

<Update label="2025-11-05" description="v6.4.0 — Dual Service System — Client Catalog & Review Moderation" tags={["Tasks", "Services", "CRM"]}>

> Complete internal/external service separation with client-facing catalog, review moderation, visibility controls, slug-based routing, and per-user access grants

### 🚀 New
- Client service catalog — /catalog/offerings grid page showing published services with category filters, 'My Active Services' dashboard, and subscription badges
- Client service detail — /catalog/offerings/[slug] landing page with hero, description, deliverables, FAQ accordion, gallery, reviews, and pricing sidebar
- Service reviews — clients can submit star ratings and comments; agency moderates via Reviews tab with approve/reject queue and pending count badge
- Client visibility controls — 5 toggles in Edit Service modal (Pricing, FAQ, Deliverables, Gallery, Reviews) controlling what clients see on catalog pages
- Service slug editing — URL-friendly slugs with live preview, regex validation, and uniqueness enforcement per agency
- Per-user service access — ServiceAccess model with canView/canEdit/canAssign grants for agency staff without view_all permission
- Reviews tab on internal service detail — average rating summary, pending moderation queue with approve/reject, approved reviews list
- Threaded comment replies & subtask descriptions in TaskDrawer
- Mobile TaskDrawer resizable sidebar panel
- Clicking task notification opens TaskDrawer directly
- Comment interaction notifications + one-reaction-per-user + mobile sidebar 20%
- @mention support in task descriptions, comments, and replies
- Project file upload + fix RTE isEmpty for attachments
- ClickUp-style grouped collapsible task list
- File preview modal in project Files tab
- Image lightbox with zoom for all uploaded images
- Settings tab CSS uplift + save fix + backfill slugs
- V6.1 notification expansion — 10 new types, cron route, mutation triggers
- Notification Intelligence v7 — priority tiers, cooldown engine, escalation logic
- File pinning, file type icons, tab hash persistence, task list layout fixes
- Project URL slugs, docs/files hash, file styling, expanded settings
- Slug edit field in settings, replace date inputs with DatePicker

### ✨ Improved
- Role-based API scoping — clients see only published/assigned services; agency staff without services:view_all see only explicitly granted services
- Security hardening — all mutations verify organizationId, client roles blocked from create/edit/delete, slug-based endpoints strip all internal fields
- Sidebar routing — client roles automatically routed to /catalog/offerings instead of internal /services management page
- Rename /clients route to /organizations
- Refine TaskDrawer Details tab visual hierarchy
- Add gap between comment editor and first comment
- Rename Client → Organization across entire codebase
- Split TaskDrawer.tsx (93KB) into 6 focused components

### 🐛 Fixed
- Changelog notifications show 'just now' for today's entries
- Settings sidebar sticky behavior restored
- Service detail notification bell positioned top-right on desktop
- RichTextEditor list items now display bullets and numbers
- Notification bell now inline with action buttons on project/org pages
- Remove Enter-to-send, redesign comment/reply thread UI
- Change reaction button from laughing emoji to thumbs-up icon
- Kanban drag snap-back + changelog v5.8.0
- RTE link validation, attachment button, public HTML, print dark mode, heading dropdown
- Quote button now toggles off when clicked again
- Stricter link validation (TLD required) + link editing support
- Time entry form with hours + minutes inputs
- Move sort headers inside each status group table
- Allow org owners and members to upload project files
- TaskDrawer crash, code toggle, and RTE toolbar position
- Move hooks above early returns to fix React error #310
- Description blank on tab switch, PDF in attachments tab, PDF preview
- Kanban DnD middle columns, RTE code toggle, link Enter, services pricing
- Align columns consistently across task status groups
- Replace all remaining user-facing 'client' text with 'organization'
- Resolve all remaining client→org rename inconsistencies
- Resolve runtime bugs - CSS class mismatches and p.org guard
- Add 'as const' to entityType literals in notification arrays
- Project task list health column, dynamic title width, view URL persistence
- Settings tab crash from wrong router response shape, update docs
- Slug save overwritten by name - only regenerate from name if name changed
- Org slug auto-regeneration only when companyName actually changes
- Task list column cropping — switch from tableLayout fixed to auto
- Redirect to new slug URL after project rename
- Use cuid (not slug) for all task operations on project page
- Pin icon visual state + truncate long file names
- File name ellipsis now visible with proper flex layout

</Update>

<Update label="2025-10-13" description="v6.3.0 — Slug URLs, Hash Tab Persistence & File UX" tags={["Tasks", "Projects", "CRM"]}>

> Human-readable slug URLs for projects and organizations, hash-based tab and view persistence, file list UX polish, task list column fix, and settings improvements

### 🚀 New
- Project slug URLs — projects accessible via /projects/my-project-slug instead of cuid; slug auto-generated from name, editable in settings
- Organization slug URLs — organizations accessible via /organizations/company-slug; getById accepts both cuid and slug with automatic fallback
- Hash-based tab persistence for projects — URL hash (#tasks-board, #docs-files, #settings, etc.) persists active tab and view across reloads and browser navigation
- Hash-based tab persistence for organizations — URL hash (#contacts, #invoices, #settings, etc.) persists active tab across reloads
- URL slug field in project settings — editable slug input with /projects/ prefix, real-time sanitization (lowercase, alphanumeric, hyphens)
- Pinned files — toggle pin on project files with visual pin icon state (colored when pinned, dimmed when unpinned)

### ✨ Improved
- Slug-change redirect — renaming a project or organization automatically redirects to the new slug URL, preserving the current tab hash
- File name truncation — long file names in project file list truncated with visible ellipsis (...) instead of wrapping to multiple lines
- DatePicker integration — project settings Start Date and Due Date now use the global DatePicker component instead of raw date inputs

### 🐛 Fixed
- Fixed task list column cropping — switched to tableLayout auto with fixed pixel widths on non-title columns; title column takes remaining space
- Fixed slug rename breaking project data — task queries and mutations now use the resolved cuid instead of the URL slug, preventing 'Project not found' errors
- Fixed organization slug auto-sync — custom slugs no longer overwritten when saving settings without changing the company name

</Update>

<Update label="2025-10-09" description="v6.2.0 — Notification Intelligence v7" tags={["Billing", "Notifications", "CRM"]}>

> Priority tier system (P1-P4), notification cooldown engine, invoice escalation logic, PAYMENT_REMINDER downgrade, client-facing status filtering, and priority accent UI in the notification panel

### 🚀 New
- Priority tier system — 4-tier classification (P1 Critical, P2 Risk, P3 Action Required, P4 Informational) stored at creation time on every notification, controlling delivery behavior and visual weight
- Notification cooldown engine — prevents duplicate notifications (same type + entity + user) within 24 hours; P1 critical events bypass cooldown for escalation support
- Invoice escalation logic — cron checks for Day 7+ and Day 30+ overdue invoices, upgrading severity to P1 with stronger copy and Slack alerts to agency owners
- Priority accent UI — notification panel items now display colored left borders: red (P1 critical), orange (P2 risk), blue (P3 action required)

### ✨ Improved
- PAYMENT_REMINDER downgraded from critical to P2 — reminders now respect quiet hours for org users instead of bypassing them
- PROJECT_STATUS_CHANGED client filtering — org users only notified on meaningful status shifts (Delayed, Completed, On Hold, Blocked, Cancelled), not internal workflow transitions
- PriorityTier enum (P1-P4) and priorityTier field added to Notification model in schema

</Update>

<Update label="2025-10-07" description="v6.1.0 — Notification System — Full Coverage" tags={["Notifications", "Tasks", "Projects"]}>

> 10 new notification types with mutation-based triggers, cron-driven time-based alerts, and 2 new preference categories (timeTracking, projectDocs)

### 🚀 New
- Task intelligence — TIME_LOGGED notifies assignees when someone else logs time; SUBTASK_COMPLETED alerts parent task owners; CHECKLIST_COMPLETED fires when all items are done; MENTION detects @[Name](userId) in comments
- Project awareness — SERVICE_ASSIGNED notifies project lead when a service is linked; DOC_CREATED and DOC_UPDATED types registered for future project document mutations
- Organization — NEW_ORG_CREATED notifies agency owners when a new client organization is created
- Cron-based alerts — /api/cron/notifications runs daily checks for TASK_DUE_TOMORROW, FOLLOW_UP_DUE/OVERDUE, CONTRACT_EXPIRING, PAYMENT_REMINDER, and PROJECT_DEADLINE_APPROACHING with built-in deduplication

### ✨ Improved
- PAYMENT_REMINDER added to critical events list — bypasses digest batching for urgent invoice reminders
- Two new preference categories (timeTracking, projectDocs) added to all role configs and visibility arrays

</Update>

<Update label="2025-10-05" description="v6.0.0 — Comprehensive Notification System Expansion" tags={["Billing", "Notifications", "Projects"]}>

> 18 new notification types covering project lifecycle, CRM & client management, invoice awareness, team operations, and operational intelligence — with role-based visibility and per-type icons

### 🚀 New
- Project lifecycle notifications — PROJECT_COMPLETED, PROJECT_STATUS_CHANGED, MILESTONE_COMPLETED trigger for all project members when statuses change
- Project membership notifications — PROJECT_MEMBER_ADDED and PROJECT_MEMBER_REMOVED notify affected users with project name and role context
- Invoice awareness — INVOICE_VIEWED notifies creator + agency owners when a client views an invoice; INVOICE_VOIDED alerts client contacts
- Team operations — ROLE_CHANGED notifies users when their role is updated (with from/to names); MEMBER_REMOVED alerts the member and agency owners
- Budget threshold alerts — BUDGET_THRESHOLD warns agency owners when project budget reaches 80%+ utilization
- File upload notifications — FILE_UPLOADED notifies project members when new files are added
- CRM notifications — FOLLOW_UP_DUE, FOLLOW_UP_OVERDUE, CONTRACT_EXPIRING, CLIENT_HEALTH_CHANGED types registered for future CRM automation
- Operational intelligence — TASK_DUE_TOMORROW and AUTOMATION_FAILED types registered for future cron-based triggers

### ✨ Improved
- 4 new critical event types — CONTRACT_EXPIRING, CLIENT_HEALTH_CHANGED, BUDGET_THRESHOLD, AUTOMATION_FAILED bypass digest batching
- 10 new notification categories with per-role visibility and default preferences configured for all 7 roles
- 16 new SVG icons in NotificationPanel for visual distinction of each notification type

</Update>

<Update label="2025-10-01" description="v5.9.0 — Grouped Task List, File Preview & Image Lightbox" tags={["Tasks", "Projects", "Files"]}>

> ClickUp-style collapsible task list grouped by status, file preview modal for project files, image lightbox with zoom/pan across all uploaded images, and rich text editor improvements

### 🚀 New
- Grouped Task List — tasks organized into collapsible sections by status (To Do, In Progress, In Review, Done) with colored borders, chevron toggle, and task count badges
- Sortable column headers — Task, Priority, Health, Assignee, Due Date, Project columns with A→Z / Z→A sort toggle, sorting within each status group
- File Preview Modal — click any file name in project Files tab to preview images inline, PDFs in iframe, video/audio with native controls
- Image Lightbox with Zoom — click any uploaded image in comments, descriptions, or project files to open full-screen modal with zoom in/out (25%–500%), mouse wheel zoom, drag-to-pan
- RTE Link Editing — click link button while cursor is inside an existing link to edit it in-place; link button highlights when active
- RTE Attachment Support — file picker for images (embed inline) and other files (download links); Send button enables with attachment-only content

### ✨ Improved
- URL validation now requires a valid TLD (e.g. example.com) — random strings are rejected with user-friendly alert
- Time Entry form upgraded to dual Hours + Minutes inputs; duration column shows 'Xh Ym' format
- Reusable GroupedTaskList component shared across All Tasks page and Project Tasks page

### 🐛 Fixed
- RTE isEmpty — editor no longer considered empty when only images, file attachments, or @mentions are present
- Quote button now toggles off properly when clicked again

</Update>

<Update label="2025-09-27" description="v5.8.0 — Smart Notifications, Kanban Polish & Mobile UX" tags={["Security", "Mobile", "Notifications"]}>

> Comment interaction notifications, Kanban drag-and-drop fix, mobile TaskDrawer resizable sidebar, reaction system improvements, and notification deep-linking

### 🚀 New
- Notifications for comment replies — parent comment author is notified when someone replies
- Notifications for comment reactions — comment author is notified when someone reacts with an emoji
- Mobile TaskDrawer resizable sidebar — drag handle between description and metadata panel; default 20% height
- Clicking a task notification now opens the TaskDrawer directly instead of just navigating to tasks list

### ✨ Improved
- Reaction system enforces one reaction per user per comment — new emoji overwrites the previous one
- Reaction button changed from smiley emoji to a cleaner thumbs-up outline icon
- Service detail header actions (Assign, Edit, Archive) and notification bell aligned to the right on desktop

### 🐛 Fixed
- Fixed Kanban board drag-and-drop snap-back — tasks no longer visually return to original position after being dropped

</Update>

<Update label="2025-09-24" description="v5.7.0 — Mobile UI Polish & Team Page Upgrade" tags={["Mobile", "Major Update", "Billing"]}>

> Comprehensive mobile responsiveness fixes across Service Detail, Invoice Analytics, Team cards, and Reports pages, plus team page filter modernization

### 🚀 New
- Stack project dropdown items vertically
- Safe rich paste in RichTextEditor
- Use RichTextEditor in project docs
- Revamp RichTextEditor to premium Asana-level editor
- Sortable columns in task list view
- Auto-populate bill-to on org change in edit form + remove Company Name
- Replace all native date inputs with DatePicker component
- Clicking pinned docs in project overview navigates to Docs tab

### ✨ Improved
- Service Detail mobile layout — header now stacks vertically: breadcrumb, title, badges, action buttons; notification bell positioned top-right
- Service description moved from header to dedicated card in Overview tab for cleaner mobile layout
- Invoice analytics cards now stack into single column on mobile instead of overflowing
- Team member cards — removed duplicate Owner badge, name on its own line, badges grouped on same row, metrics stay inline
- Team page filters upgraded from inline selects to shared FilterIconBtn component with icon dropdowns for Role, Department, and Status
- Move RichTextEditor to components/shared/

### 🐛 Fixed
- Reports page notification bell no longer pushed off-screen by date range buttons on mobile
- Team card actions moved to dedicated bottom row to prevent cramped horizontal layout
- Changelog summary text clipping
- Render comments as HTML instead of markdown
- Add rich-text styles for comment/description HTML rendering
- Notification system for all user roles
- Notify client contacts on invoice edit-after-send + hide Record Payment for org roles
- Align invoice edit form with create form
- Restore Pay button for org users + rename to Pay
- Line items CSS layout and handle-only drag
- DatePicker dropdown overflow in narrow containers
- DatePicker now uses position:fixed to escape overflow clipping
- Mobile responsive fixes for all pages
- Project detail stat cards and overview grid stacking on mobile
- Task drawer description and fields un-editable on mobile
- Services page search input too large and filters not compact on mobile
- Client detail header - add left padding to clear hamburger menu
- Add spacing between CHURNED badge and tags row
- Restructure contact cards into 3 clear rows

</Update>

<Update label="2025-09-12" description="v5.6.0 — Task Visibility Scoping & Assignee Improvements" tags={["Tasks", "Projects", "Team"]}>

> Role-based task visibility, project-scoped assignees, mandatory project selection, and bug fixes

### 🚀 New
- Role-based task visibility — Agency Owner sees all tasks, Agency Staff sees assigned/created tasks, Org Owner/Member sees tasks in their organization's projects
- Project-scoped assignee dropdown — shows only project team members + Agency Owner when editing tasks within a project
- Mandatory project selection — new tasks now require a project via a searchable dropdown in the task drawer sidebar
- Auto-cleanup of untouched tasks — closing a task with default title and no description automatically deletes it
- Role-specific dashboards, settings for all, org reports
- View As / Impersonation for agency owners
- Contact profile modal on clients page
- Password reset for contacts in profile modal
- Add per-project invoice tracking with projectId on Invoice
- Add full header actions to CreateTaskDrawer matching TaskDrawer
- Convert RichTextEditor to true WYSIWYG

### ✨ Improved
- WYSIWYG comment/description editor — real-time formatting with bold, italic, links, lists, code blocks, and blockquotes
- Org Owner & Org Member can now create, edit, assign, and change status on tasks
- Delete CreateTaskDrawer, use instant-create + TaskDrawer

### 🐛 Fixed
- Fixed double placeholder text in the comment editor
- Fixed negative 'Avg Completion' hours caused by tasks with null completedAt dates
- Fixed tasks page not showing newly created tasks due to default 'My Tasks' filter and client scoping
- Auto-migrate old role names in database on load
- Dashboard crash for org owner — category was a relation object
- View As now fully switches to target user's experience
- Auto-sync permissions on existing system roles
- Strictly separate Team (agency staff) from Organization (client contacts)
- Impersonation bugs — settings respects client role, View As for pending users
- Hide agency-only buttons from org owners on invoice page + fix edit grid
- Replace old Add Task modal with Asana-like CreateTaskDrawer on project page
- Invoice page — hide drafts, simplify stats & analytics for org users
- Remove misleading per-project invoice stats (same values for all projects)
- Scope getAnalytics to client for org users — stats were showing agency-wide totals
- Restore financial strip on project cards with client-level fallback
- Repair CreateTaskDrawer CSS — use correct td-* class names
- Notification panel empty state + hide service buttons for org users
- Scope task analytics to client projects for org owners
- Add error handling to +New Task button to surface failures
- Render markdown formatting in task comments
- Link modal z-index — use position:fixed with z-index:10000

</Update>

<Update label="2025-08-30" description="v5.5.0 — Multi-Layer Permission System & Public Task Sharing" tags={["Major Update", "Billing", "Tasks"]}>

> Complete permission architecture overhaul with per-item sidebar filtering, role-based access aligned to the multi-tenant hierarchy (Agency → Team → Organization → Client), public shared task pages, and rich text editor fix

### 🚀 New
- Per-nav-item sidebar filtering — each menu item is shown/hidden based on the user's actual permissions instead of binary all-or-nothing
- NAV_PERMISSION_MAP — centralized permission map for sidebar items: Billing (owner-only), Team (manage_team), Reports (reports_view), etc.
- Public shared task page at /shared/task/[token] — read-only view with no login required, premium card layout for external sharing
- Add Asana-style rich text toolbars to task description & comments
- Fix task print, Asana close icon, and public share toggle
- Multi-layer permission system v5.5.0

### ✨ Improved
- Role defaults aligned to spec — PM gets invoice view/edit + team management, Team Member gets invoice create only, Client gets services view + task status change
- Settings restricted — non-admin users only see Account + About sections; org management sections hidden

### 🐛 Fixed
- Rich text editor toolbar — fixed blur/focus conflict preventing formatting buttons from inserting markdown
- Role label display — sidebar now shows actual role name from session instead of hardcoded 'Member'

</Update>

<Update label="2025-08-27" description="v5.4.0 — Updated Task Details Panel" tags={["Major Update", "Tasks"]}>

> Complete redesign of task details from a basic 520px drawer to a premium 860px two-column detail panel inspired by Asana/Linear, with rich metadata, tabbed content, and modern micro-interactions

### 🚀 New
- Two-column detail panel — main content area (65%) with tabbed interface and metadata sidebar (35%) replacing the narrow drawer
- Three-tab interface — Details (description, checklist, dependencies, comments), Subtasks (progress bar, inline creation), Activity (time tracking, timeline)
- Custom status pill selector — colored dot indicators with dropdown, replacing native select elements
- Custom priority pill selector — directional icon-based selector with color coding
- Dependency visualization — blocking/blocked-by chips with task status indicators
- Inline subtask creation — dashed-border input with progress bar and completion counter
- Labels and tags display — colored tag pills from task labels with per-label color theming
- Time tracking stats in sidebar — logged and billable time displayed with formatted hours/minutes
- Add portal password field to Add Contact form
- Suppress browser print headers, add org tagline, inline org creation on invoices
- World-class task details panel redesign

### ✨ Improved
- Glassmorphic backdrop — blur(6px) overlay with smooth fade-in animation
- Gradient accent bar — primary → secondary → info gradient at panel top
- Spring-like slide animation — cubic-bezier(0.16, 1, 0.3, 1) easing for premium feel
- Searchable assignee dropdown — avatar-based team member selector with search filtering
- Rich comment section — avatar bubbles, relative timestamps, Enter-to-send
- Health badge — visual health status indicator in header (On Track, At Risk, Overdue, Blocked, Stalled)
- Responsive layout — two-column on desktop, stacked with grid sidebar on tablet, single column on mobile
- Keyboard shortcut — Esc to close the detail panel

### 🐛 Fixed
- Blank print page — use visibility trick instead of nuclear display:none
- Add display:block to print-invoice in @media print
- Rename Organization to Agency in settings, add contact permission gating, sync tagline column to DB

</Update>

<Update label="2025-08-19" description="v5.3.0 — Printable Invoices Revamp" tags={["Major Update", "Billing", "CRM"]}>

> Dedicated premium print template with agency branding, professional layout, and configurable print settings

### 🚀 New
- Premium print template — dedicated branded header (logo, agency info, invoice number, status badge, dates), two-column bill-to/org block, enhanced line items table, totals section, payment history, notes, legal footer
- Invoice Print Settings page — configure what appears on printed invoices (logo, payments, bank details, notes, paper size) from Settings > Organization > Invoice Settings
- Organization branding integration — printed invoices pull logo, legal name, address, tax ID, registration number, footer note, bank details, and payment instructions from org settings

### ✨ Improved
- Template-based print approach — hides all app chrome and shows only the dedicated print template, ensuring clean paper output
- Configurable paper size — A4 and US Letter supported

</Update>

<Update label="2025-08-17" description="v5.2.0 — New Printable Invoices" tags={["Major Update", "Billing", "Notifications"]}>

> Complete overhaul of invoice print styles — clean, paper-ready layout with all app chrome hidden and professional typography

### 🚀 New
- Professional print layout — A4 page setup with proper margins, clean black-and-white typography
- All app chrome hidden in print — sidebar, hamburger menu, notifications, buttons, Activity Timeline, back links
- Professional printable invoice styles (v5.2.0)

### ✨ Improved
- Single-column layout — 2-column grid collapses for clean paper output
- Professional table formatting — uppercase headers, clean borders, proper alignment
- Totals section — bold amounts, clear visual hierarchy for subtotal/total/paid/due
- Page break control — sections avoid splitting across pages

</Update>

<Update label="2025-08-15" description="v5.1.0 — Organizations Rename & Contact Stakeholders" tags={["Major Update", "Billing", "Team"]}>

> Renamed 'Clients' to 'Organizations' across the entire UI for clarity, and upgraded contacts into operational stakeholders with billing, approver, and status flags

### 🚀 New
- Renamed 'Clients' → 'Organizations' across sidebar, list page, detail page, invoices, and permissions
- Contact stakeholder flags — isBilling and isApprover booleans for operational role assignment
- Contact status — ACTIVE/INACTIVE enum for soft-disabling contacts without deletion
- Contact business title field — separate from role for clearer stakeholder identification
- Flexible socials storage — JSON field supporting any number of social/communication channels
- Replace all native date inputs with premium DatePicker component
- Rename Clients → Organizations + upgrade contacts to stakeholders (v5.1.0)

### ✨ Improved
- Email uniqueness constraint per organization prevents duplicate contacts
- Contacts tab upgraded with toggle actions for Billing, Active/Inactive, and badge indicators
- Organization detail page shows Primary, Billing, Approver, and Inactive badges on contacts

</Update>

<Update label="2025-08-12" description="v5.0.0 — Service Builder & Financial Intelligence" tags={["Billing", "Tasks", "Services"]}>

> Multi-step service creation wizard with draft/publish lifecycle, flexible billing intervals (monthly/quarterly/yearly), normalized ARR/MRR dashboard reporting, and in-app changelog

### 🚀 New
- Multi-step Service Builder — 4-step wizard at /services/new (Basics, Description, Pricing, Review & Publish) replacing the single modal
- Draft/Publish lifecycle — services start as drafts, publish requires name + pricing validation, drafts blocked from client assignment
- Flexible billing intervals — monthly, quarterly, and yearly recurring options with per-interval pricing
- Rich service content — cover images, gallery (up to 8), shareable links (up to 10), FAQ entries (up to 15)
- Normalized MRR — dashboard MRR now includes yearly÷12 and quarterly÷3 equivalents alongside monthly direct
- ARR KPI — annual recurring revenue card with breakdown (fromMonthly, fromYearly, fromQuarterly)
- Changelog settings tab — full version history with timeline layout, type-colored badges, and release stats

### ✨ Improved
- Service cards now show Draft/Published status badges on the services list
- Server-side publish validation — recurring services must specify billing interval, all services need pricing
- Extended Prisma schema with BillingType, BillingInterval, ServiceStatus enums and 8 new Service fields

</Update>

<Update label="2025-08-09" description="v4.0.0 — CRM Command Center" tags={["Billing", "Projects", "CRM"]}>

> Comprehensive client relationship management with financial intelligence, follow-ups, communication logs, document hub, contract tracking, health scoring, and lead pipeline

### 🚀 New
- Financial intelligence panel — 6 stats: revenue, active projects, unpaid (with invoice count), overdue count, avg payment delay, on-time payment %
- Contract & renewal tracking — start/end dates, renewal type, notice period, SLA tier, approaching-expiry warnings
- Lead pipeline card — expected value, deal probability, weighted value, close date, source (visible for LEAD/CONTACTED/PROPOSAL_SENT)
- Follow-up engine — create/complete/delete follow-ups with priority levels, due dates, inline forms on Overview tab
- Communication log tab — log calls, meetings, emails, decisions, issues, change requests with pin-as-decision support
- Document hub tab — upload contracts, NDAs, SOWs, brand assets with categorization and team attribution
- Health scoring engine — deterministic server-side computation from overdue invoices, payment delays, activity gaps, overdue tasks
- Enhanced client list — Revenue, Unpaid, Health badge, Last Activity columns + 8 sort options
- Unified timeline API — aggregated events from audit logs, follow-ups, and communication logs
- Recurring invoice system + financial metric hardening
- Role-based defaults, critical events, scoped prefs, history, Slack webhook
- Advanced organization branding system
- Team page revamp

### ✨ Improved
- Client contact upgrades — role type (Decision Maker/Finance/Technical/Ops), preferred channel, timezone fields
- All mutations update lastActivityAt for accurate recency tracking
- Server-side permission checks on all 23 procedures with strict org-scoping
- Replace all emoji icons with minimalistic SVG icons across 18 files

### 🐛 Fixed
- Populate changelog entries in notification panel
- Team member profile 500 error — invalid ProjectStatus enum + unsynced schema

</Update>

<Update label="2025-08-02" description="v3.10.0 — Team Management Hub" tags={["Tasks", "Projects", "Team"]}>

> Full operational team hub with member profiles, workload analytics, pending invites, and department management

### 🚀 New
- 7-stat analytics strip — total, active, invited, active tasks, avg tasks/member, overloaded, overdue (all server-computed)
- Member profile modal — identity, 6 work metrics (assigned/completed/overdue/completion rate/active projects/billable hours), activity timeline
- Pending invites panel — separate section with resend and cancel actions
- Department management — assign departments to members, filter by department
- Member status system — active/invited/suspended with visual badges
- Employment type tracking — full-time, contractor, intern
- Team description block — editable org-level text above analytics
- Completion rate rings — SVG donut per member card
- Activity pulse indicator — green/yellow/gray dot based on last activity

### ✨ Improved
- 11 backend procedures with server-computed metrics, audit logging, and overload detection

</Update>

<Update label="2025-07-30" description="v3.9.0 — Team Page Revamp" tags={["Major Update", "Tasks", "Team"]}>

> Complete team page rewrite with analytics, search, role management, member removal, and workload capacity bars

### 🚀 New
- Team Analytics Strip — total members, active tasks, overdue tasks, avg tasks per member
- Search & Role Filter — search by name or email, filter by role
- Inline Role Management — change member roles directly from the member card dropdown
- Member Removal — remove button with confirmation modal, owner protection
- Workload Capacity Bars — color-coded indicators (green light / yellow medium / red heavy) per member

### ✨ Improved
- Enhanced member cards with joined date, active/overdue counts, task pills with overdue warnings

</Update>

<Update label="2025-07-28" description="v3.8.0 — Advanced Organization Branding System" tags={["Billing", "CRM", "Automations"]}>

> Centralized branding engine with 5-tabbed settings, email/invoice/portal identity, white label controls, and live preview

### 🚀 New
- Brand Identity — secondary color, semantic colors (success/warning/danger), font family selector (system/Inter/Poppins/Roboto/Outfit), border radius preference (sharp/medium/rounded)
- Email Branding Engine — from name/email, reply-to, header/footer logos, HTML signature, footer text, social links
- Invoice & Document Branding — invoice logo, accent color, footer note, bank details, payment instructions, signature image, tax ID display, registration number, powered-by toggle
- Portal Branding — background, headline, subtext, welcome message, 404 message, footer, default landing page selector
- White Label Control Panel — hide platform name/logo/footer credits, custom page title format, support email/URL

### ✨ Improved
- 5-tabbed branding settings UI with live color preview and unsaved changes warning
- 40+ new Organization schema fields with full server-side validation (hex colors, email format, enum values)

</Update>

<Update label="2025-07-26" description="v3.7.0 — Notifications System Enhancement" tags={["Billing", "Notifications", "Tasks"]}>

> Role-aware defaults, critical event system, scoped preferences, notification history, Slack webhook integration, and digest improvements

### 🚀 New
- Role-Based Notification Defaults — new users inherit preferences based on role (Owner/Admin/Finance/PM/Member)
- Critical Event System — INVOICE_OVERDUE, PAYMENT_FAILED, PROJECT_DELAYED, TASK_OVERDUE_BATCH bypass digest and quiet hours
- Scoped Notification Preferences — per-category scope selector (All / Only mine / My projects)
- Notification History Page — paginated log with type/unread/critical filters, mark-read, and delete
- Slack Webhook Integration — org-level incoming webhook URL, per-category toggles, test button

### ✨ Improved
- 5 new NotificationType values: INVOICE_OVERDUE, PAYMENT_FAILED, PROJECT_DELAYED, TASK_OVERDUE_BATCH, RECURRING_GENERATED
- Notification model enhanced with isCritical flag and deliveryChannel tracking
- Digest formatter groups notifications by project/entity, sorts critical-first
- Expanded notification categories: invoice overdue, payment failed, project delayed, recurring generated, deadline approaching

</Update>

<Update label="2025-07-23" description="v3.6.0 — Invoicing System Upgrade" tags={["Security", "Billing", "Automations"]}>

> Financial metric hardening and native recurring invoice creation with template-based MRR computation

### 🚀 New
- Recurring Invoice Creation — toggle in invoice form to create recurring templates with frequency, dates, lead days, auto-send/charge
- Recurring Template Management — list, get, pause, resume, cancel recurring templates with audit logging
- Invoice Generation Engine — idempotent generation from templates with line item cloning, dedup, and next-date computation

### ✨ Improved
- Collection Rate fixed — now uses total_collected / total_issued (excluding draft/void/bad debt) instead of paid/(paid+outstanding)
- Avg Days Late metric — new collection discipline metric showing 'X days early' or 'X days late' with color coding
- MRR recomputed from active recurring templates with monthly-equivalent conversion (weekly×4.33, quarterly÷3, yearly÷12)
- Monthly Collection Rate — this-month variant alongside lifetime rate
- Recurring stats in analytics — active templates count, recurring clients, upcoming invoices
- Recurring badge on invoice detail page for invoices generated from templates
- Forecast now includes SCHEDULED status invoices alongside unpaid

</Update>

<Update label="2025-07-20" description="v3.5.0 — Settings Security Upgrade" tags={["Security", "CRM", "Settings"]}>

> Comprehensive security hardening with re-auth gating, org policies, audit log, account deletion, and data export

### 🚀 New
- Re-authentication modal — password + TOTP verification before sensitive actions (2FA disable, backup code regen, account deletion)
- Backup codes regeneration — generate new recovery codes with re-auth, one-time display, copy-all support
- Security activity log — user-level append-only event feed with 15+ event types and icons
- Organization Security Policies page — enforce 2FA with member compliance table, session idle/max timeouts, domain restrictions
- Organization Audit Log page — paginated, filterable by event type, with actor details and change metadata
- Account deletion with 7-day grace period — request/cancel flow, owner transfer check, scheduled deletion countdown
- Data export — download profile, memberships, preferences, and security log as JSON
- Settings security upgrade v3.5.0 — reauth, org policies, audit log, account deletion, data export

### ✨ Improved
- Email verification badge on profile page — shows Verified/Unverified status
- Sign Out All Sessions — requires re-authentication, revokes all devices including current
- Sessions now show created timestamp alongside last active

</Update>

<Update label="2025-07-16" description="v3.4.0 — Task Management System Upgrade" tags={["Tasks", "Automations"]}>

> Transformed the task board into an agency-grade operations engine with health intelligence, time tracking, workload view, and operational safeguards

### 🚀 New
- Task Health Intelligence — auto-computed ON_TRACK / AT_RISK / OVERDUE / BLOCKED / STALLED status with colored indicators
- Task Detail Command Center — tabbed panel with details, time tracking, checklist, and activity timeline
- Time Tracking — start/stop timer, manual time logging, logged vs billable hours
- Checklist System — nested items with auto-progress bar calculation
- Task Dependencies — circular detection, blocking safeguards, lock icons on blocked tasks
- Workload View — per-team-member capacity bars, active/overdue counts, hours tracking
- Analytics Strip — 7 real-time metrics (active, overdue, due today/this week, completion rate)
- Activity Timeline — auto-logged events for all task mutations
- Changelog Notifications — new versions broadcast to all team members via notification bell
- Task management system upgrade v3.4.0 — health intelligence, time tracking, workload, checklists, analytics, changelog notifications

### ✨ Improved
- Advanced task filters — health status, priority, project, date range, stale days, dependency presence
- Operational safeguards — block DONE if deps incomplete, soft-delete tasks with time logs, prevent overlapping timers

</Update>

<Update label="2025-07-12" description="v3.3.0 — Invoicing System Upgrade" tags={["Billing", "Tasks", "CRM"]}>

> Full finance control center with analytics, recurring invoices, credit notes, refunds, and activity timeline

### 🚀 New
- Finance Analytics Dashboard — MRR, collection rate, avg days to pay, aging buckets, revenue by client
- Recurring Invoice Engine — templates, auto-generation on schedule
- Credit Note System — issue and apply credit notes to invoices
- Refund Processing — partial/full refunds with audit trail
- Invoice Timeline — chronological view of all invoice events
- Invoice system upgrade v3.3.0 — analytics, recurring, credit notes, refunds, timeline

### ✨ Improved
- Bad Debt marking capability with financial impact tracking
- Invoice type badges and enhanced status management

### 🐛 Fixed
- Settings cards + mobile hamburger alignment + notification bell fix
- Mobile notification dropdown now visible — removed conflicting CSS

</Update>

<Update label="2025-07-09" description="v3.2.2 — Settings Cards + Mobile Hamburger Fix" tags={["Performance", "Mobile", "Billing"]}>

> Added missing Integrations & Billing cards to settings, fixed mobile hamburger to sit beside page title

### 🐛 Fixed
- Mobile hamburger now sits beside the page title instead of floating above it
- Added missing Integrations and Billing & Plans cards to settings dashboard
- Removed duplicate Settings title (layout provides it via page-header)
- Notification bell on mobile now has proper 40x40 touch target and z-index for reliable taps

</Update>

<Update label="2025-07-08" description="v3.2.1 — Inline Breadcrumbs + Settings Header" tags={["Notifications", "Projects", "Settings"]}>

> Breadcrumbs now sit inline with page titles, settings pages get a proper header with notification bell

### ✨ Improved
- Breadcrumb back links now display inline with page titles (← Projects / Project Name) instead of floating on a separate row
- Settings layout now has a proper page-header with title, description, and notification bell

</Update>

<Update label="2025-07-07" description="v3.2.0 — Project Workspace Header Upgrade" tags={["Notifications", "Projects", "Services"]}>

> Upgraded single project page header to match the polished service detail layout, added notification bell to detail pages

### ✨ Improved
- Project detail page header now matches the service detail layout — back link, title with inline status/health badges, metadata row (client, dates, PM)
- Project header uses page-header class for consistent sticky positioning and background

### 🐛 Fixed
- Notification bell now present on single project and single service detail pages
- Notification deep links — clicks go to specific entity pages
- Mobile UI polish — inline header, sidebar logo, responsive bell

</Update>

<Update label="2025-07-05" description="v3.1.1 — Mobile UI Polish" tags={["Performance", "Mobile", "Notifications"]}>

> Fixed mobile header layout and sidebar logo overlap for a clean responsive experience

### ✨ Improved
- Smaller buttons and bell icon on mobile for better touch targets
- Subtitle/description hidden on mobile to save space

### 🐛 Fixed
- Page header stays as single row on mobile — title truncates, actions stay right
- Sidebar logo no longer hidden by hamburger close button on mobile
- Notification dropdown properly fills mobile width with correct z-index

</Update>

<Update label="2025-07-04" description="v3.1.0 — Notification UX + Mobile Polish" tags={["Mobile", "Billing", "Notifications"]}>

> Fixed notification click navigation, full-width mobile dropdown, and responsive header layout across all pages

### 🚀 New
- Relocate notification bell to top-right + seed test notifications
- Reviewer micro-upgrades — client pill, PAID tag, invoice action

### ✨ Improved
- Mobile page headers reorganized: notification bell, actions, and hamburger menu no longer overlap
- Notification bell moved inline into every page header — consistent position beside action buttons
- Client names now display as clickable pill badges linking to client detail page
- Green PAID ✓ tag appears on project cards when all invoices are fully settled

### 🐛 Fixed
- Clicking a notification now navigates to the relevant page (tasks, projects, invoices, clients)
- Notification dropdown now appears correctly on mobile — full-width with proper z-index
- Projects page UI issues — header bg, search alignment, card styling

</Update>

<Update label="2025-07-01" description="v3.0.0 — Projects → Agency Command Center" tags={["Billing", "Tasks", "Projects"]}>

> Transformed the All Projects page into an intelligent agency control center with financial visibility, automated health scoring, and rich project intelligence

### 🚀 New
- Circular progress rings replacing linear bars — color-coded by completion rate with smooth animated transitions
- Financial metrics strip on each card: Invoiced, Paid, and Outstanding amounts with formatted currency
- Automated project health scoring (On Track / At Risk / Delayed) computed server-side from overdue tasks, deadline proximity, and completion rate
- Activity pulse indicators: green (active), yellow (stale 3+ days), red (inactive 7+ days) — computed automatically from task activity
- Urgency timeline with days remaining counter: color-coded from neutral → warning → high alert → critical/overdue
- Hover-reveal quick action buttons on each project card for instant navigation
- In-app notification system: bell icon in sidebar with unread badge, dropdown panel, mark-as-read, and clickable notifications
- Auto-notifications: task assigned, invoice paid/sent, new team member joined, and comment on task

### ✨ Improved
- Enhanced table view with Health, Budget, Activity columns and priority border accents
- Priority-based left border accent on all project cards for instant visual differentiation
- Team avatars with member count badges on each card for ownership visibility
- All enrichment data (financial, overdue, time, activity, health) computed server-side with batched queries — zero N+1 issues

</Update>

<Update label="2025-06-27" description="v1.1.0 — Service Page UX + Categorization Upgrade" tags={["Major Update", "Projects", "Services"]}>

> Redesigned the All Services page with structured categorization, visual card improvements, and enhanced filtering capabilities

### 🚀 New
- Service Categories: create named categories with custom colors and workspace-scoped slugs to organize your service catalog
- Category pills filter bar: horizontal scrollable row with color dots and count badges for instant filtering
- Redesigned service cards: gradient cover areas (driven by category color), status/pricing badges, category labels, and footer metadata
- Category creation modal with 10-color picker, accessible inline from the service creation form
- Status filter (Active/Inactive) and pricing model dropdown alongside search and sort controls
- Replace project page emoji icons with minimalistic SVG vectors
- Service page UX + categorization upgrade (v1.1.0)

### ✨ Improved
- Service cards now show client count and project count in a styled footer with icons
- Search input has integrated icon and focus ring; filters row is compact and responsive
- Empty state uses SVG icon instead of emoji; messaging adapts to active filters

### 🐛 Fixed
- Hide logo entirely when sidebar collapsed
- Redesign sidebar collapse/expand button
- Remove border from sidebar collapse button, match nav icon style

</Update>

<Update label="2025-06-22" description="v1.0.0 — Executive Dashboard" tags={["Major Update", "Billing", "Notifications"]}>

> Complete dashboard redesign — strategic executive control center with financial intelligence, project health, workload visibility, and smart alerts

### 🚀 New
- Executive KPI snapshot: Total Revenue, MRR, Outstanding, Overdue, Active Clients, Active Projects, At Risk, Tasks Due This Week — all with trend indicators
- Revenue & Cash Flow: 6-month revenue trend bar chart, outstanding vs overdue split, upcoming payments due in 14 days
- Project Health Matrix: server-side health scoring (Green/Yellow/Red) based on deadline proximity, task completion %, overdue tasks, and milestone status
- Workload & Team Utilization: tasks by status breakdown, team load by assignee, top 5 overdue tasks
- Intelligent Alerts: auto-detects overdue invoices, critical projects, stale tasks (3+ days overdue), and inactive clients (30+ days) — clickable and dismissible
- Time period filtering (This Month, Last 30 Days, This Quarter, This Year) with previous-period trend comparison
- Portfolio dashboard revamp for All Projects page
- Stripe Connect integration in Settings > Integrations
- Full Stripe payment flow — Checkout, webhook, public pay page
- Add comprehensive Reports module with 5 tabs
- Reports page header/padding + collapsible sidebar
- TOTP Multi-Factor Authentication
- Replace emoji icons with SVG vectors, fix collapsed sidebar logo
- Executive Dashboard v1.0.0 — complete redesign

### ✨ Improved
- MRR now correctly calculated from active RECURRING_MONTHLY services instead of dividing total revenue by 12
- All financial and risk calculations are server-side with batched queries for performance
- Every KPI card is clickable and routes to the relevant filtered page

### 🐛 Fixed
- Wire up Invite Member button with modal on team page
- Changelog Next button now advances to next entry instead of staying in place
- Remove max-width constraint on settings page content area
- Stripe Connect auth — use tRPC instead of API route
- Add Stripe env vars + speed up integrations page
- Reports page responsiveness - mobile layout, KPI grid, donut charts

</Update>

<Update label="2025-06-14" description="v0.4.1 — Icon Overhaul & UI Refinement" tags={["Major Update", "Settings", "UI/UX"]}>

> Replaced all emoji icons with minimalistic SVG vector icons and fixed collapsed sidebar

### ✨ Improved
- Replaced all emoji icons across sidebar navigation, settings sidebar, and settings overview with clean, minimalistic SVG vector icons (Lucide-inspired stroke style)
- Created shared icon library (icons.tsx) with 22 reusable SVG icon components
- Hamburger menu, close button, and collapse toggle now use SVG icons instead of text characters

### 🐛 Fixed
- Fixed logo peeking through when sidebar is collapsed (added overflow clipping)

</Update>

<Update label="2025-06-13" description="v0.4.0 — Security & UI Polish" tags={["Security", "Settings", "UI/UX"]}>

> Two-Factor Authentication, collapsible sidebar, and page consistency improvements

### 🚀 New
- TOTP Multi-Factor Authentication: enable 2FA via authenticator app (Google Authenticator, Authy, etc.) from Settings → Security
- QR code setup flow with manual secret key fallback and 8 one-time recovery codes
- Login now supports two-step verification: enter email/password, then 6-digit TOTP code
- Collapsible sidebar: toggle button to collapse to icon-only mode (64px), state saved across sessions

### ✨ Improved
- Reports page now uses the shared Page component for consistent header background, sticky header, and padding
- Smooth CSS transitions on sidebar width and main content area when collapsing/expanding

</Update>

<Update label="2025-06-11" description="v0.3.2 — Stripe Payment Flow" tags={["Billing", "CRM"]}>

> End-to-end payment collection via Stripe Checkout

### 🚀 New
- Stripe Checkout integration: send invoice pay links to clients, they pay via Stripe-hosted checkout
- Public pay page (/pay/[token]): branded invoice summary with line items, totals, and Pay with Stripe button
- Stripe webhook handler: auto-records payments and updates invoice status (PAID/PARTIALLY_PAID) on checkout completion
- Copy Pay Link button on invoice detail page — share a payment link with clients
- Pay with Stripe button on invoice detail page for quick staff-initiated payments

### ✨ Improved
- Payment model extended with Stripe session and payment intent IDs for audit trail

</Update>

<Update label="2025-06-10" description="v0.3.1 — Stripe Integration" tags={["Major Update", "Billing", "Tasks"]}>

> Connect your Stripe account to accept payments

### 🚀 New
- Stripe Connect integration: link your Stripe account to accept invoice, subscription, and one-time payments
- Stripe status dashboard showing account ID, onboarding status, and payouts state
- One-click connect and disconnect with audit logging

### ✨ Improved
- Integrations page redesigned with Stripe card and upcoming integrations preview
- Settings page now uses full width layout to match other pages

</Update>

<Update label="2025-06-09" description="v0.3.0 — Project Management System" tags={["Tasks", "Projects", "Team"]}>

> Full project workspace, portfolio dashboard, and team management

### 🚀 New
- 8-tab Project Workspace: Overview, Tasks, Timeline, Docs & Files, Team, Budget & Time, Activity, and Settings
- Portfolio dashboard with executive summary bar showing total, active, completed, overdue, on hold, and at-risk projects
- Project card grid view with real-time progress bars, urgency indicators, and quick action menus
- Bulk actions: multi-select projects to change status, archive, or delete in one click
- Project documents system with create, edit, pin, and delete support
- Milestone tracking with status, due dates, ownership, and task counts
- Budget and time tracking: budget configuration (fixed/hourly/retainer), time entry logging, and billable/non-billable breakdowns
- Project team management: add/remove members, assign roles (Lead, Member, Viewer)
- Comprehensive activity log with filtering for all project changes
- Project archiving (soft-delete) with restore capability

### ✨ Improved
- Server-side at-risk detection: projects with 20%+ overdue tasks or due within 3 days at under 50% progress
- Enhanced table view with column sorting, inline status editing, and multi-filter search
- Editable project header with inline status, health, dates, and PM controls
- Full audit logging on all project mutations with old/new value tracking

</Update>

<Update label="2025-06-04" description="v0.2.1 — What's New Popup" tags={["Mobile", "Major Update", "Billing"]}>

> Stay in the loop with every update

### 🚀 New
- In-app changelog popup that appears when you log in
- Missed updates stack so you never miss a release
- Phase 1 - Agency Management Platform foundation
- Phase 2 (Billing & Client Portal) + Phase 3 (Automations)
- Premium UI overhaul - light/dark mode, Plus Jakarta Sans, responsive design
- Task system overhaul — drag-and-drop Kanban, task drawer, assignee picker
- Agency CRM upgrade — client profiles, notes, contacts, activity
- Services overhaul + schema fixes + new routes
- Upgrade invoicing module — full agency-grade system

### ✨ Improved
- Version tracking with semantic versioning across the platform

### 🐛 Fixed
- Prisma v7 adapter with pg.Pool for Supabase pooler
- Layout full-width, add Page wrapper, Tasks sidebar + /tasks route
- Core platform bugs - client creation, optional project/client, task visibility, Add Task button

</Update>

<Update label="2025-06-02" description="v0.2.0 — Major Platform Upgrade" tags={["Major Update", "Tasks", "Projects"]}>

> Services catalog, Kanban tasks, and much more

### 🚀 New
- Full services catalog with 5 pricing models (recurring, one-time, credit packs, hourly blocks, hourly rate)
- Client service management with balance tracking, rollovers, and credit ledger
- Kanban board view for tasks with drag-and-drop support
- List ↔ Board view toggle on the tasks page
- Service templates for quick project creation

### ✨ Improved
- Redesigned services page with detailed service profiles
- Active services now visible on client detail pages
- Enhanced project page with service linkage

### 🐛 Fixed
- Fixed task creation foreign key constraint error
- Resolved build errors across all platform modules
- Fixed tRPC router name collisions

</Update>
