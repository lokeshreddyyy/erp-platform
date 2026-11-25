# Architecture

## 1. Product shape

Build one application with a shared domain model and distinct role experiences. Do not create separate disconnected applications for each role.

### Shared application shell

- Brand header and academic-year context
- Dark left sidebar with grouped navigation
- Main content workspace with responsive cards, charts and data tables
- Shared page title, filters, breadcrumbs, alerts and action patterns
- Consistent typography, spacing, colors, icons and form controls

### Role dashboards

| Role | Primary workspace |
|---|---|
| Super Admin | Consolidated operations, branches, users, financial overview, reports and configuration |
| Branch Manager | Branch KPIs, enquiries, admissions, batches, attendance, collections and branch reports |
| Counsellor | Assigned leads, follow-up queue, pipeline, counselling and admission conversion |
| Accountant | Fee collection, instalments, receivables, receipts, expenses and finance reports |
| Faculty | Assigned cohorts, teaching timetable, attendance, assignments, learning materials and exams |
| Student | Enrolled courses, lesson progress, live classes, attendance, assignments, exams, results, fees and certificates |
| Parent (optional) | Linked learner progress, attendance, fee status and announcements, subject to approval |

Every role uses the same design system. Only its authorized navigation, actions and dashboard widgets differ.

## 2. Architectural layers

- Presentation: Blade views and reusable UI components.
- Application: controllers/actions, request validation and workflow orchestration.
- Domain: organization, admissions, academics, finance, learning and assessment rules.
- Persistence: relational database, migrations, repositories/query services where useful.
- Integrations: payment gateway, email/SMS/WhatsApp provider, live-class provider and object storage.

Keep controllers thin. Put multi-step business workflows in application services. Enforce authorization in policies/middleware and again at the data-query boundary where tenant scoping is required.

## 3. Organization and data isolation

Initial hierarchy:

Company -> Institute -> Branch -> Academic Year

Operational records should carry the appropriate organization and branch references. Every query and mutation must be scoped to the authenticated user's permitted company/institute/branch set. Super Admin access may span all authorized branches; branch users must not be able to read or alter another branch's records by changing an ID in a URL or request.

Confirm whether a customer can own multiple companies before finalizing tenant isolation strategy. Do not assume that a branch filter in the UI is a security boundary.

## 4. Authorization

Use role-based access control with granular permissions, for example:

- leads.view / leads.create / leads.assign / leads.update
- admissions.view / admissions.create / admissions.approve
- students.view / students.create / students.update
- attendance.view / attendance.mark / attendance.correct
- fees.view / fees.collect / fees.refund / receipts.issue
- courses.manage / batches.manage / timetable.manage
- lessons.publish / assignments.review / exams.manage
- reports.view / settings.manage / users.manage

Navigation visibility is only a usability feature. Server-side authorization must protect every route, action, file and API. Avoid trusting a role name, hidden button or client-provided branch ID.

## 5. Learning platform

- Course -> module -> lesson structure
- Video lessons with controlled access and progress records
- Live class schedule with provider integration and attendance
- Learning resources and downloadable handouts
- Assignments with due dates, submissions, review and feedback
- Question bank, timed assessments, attempts and results
- Course completion and certificate eligibility

Store media in private object storage or a controlled media service. Do not expose private storage paths as public URLs. Choose a video hosting/streaming provider after considering cost, access control, bandwidth, playback analytics and DRM requirements.

## 6. Finance

Maintain an auditable financial ledger for collections, allocations, refunds, discounts and expenses. Receipts must be immutable records with unique identifiers. Payment gateway callbacks must be authenticated and idempotent. Never store raw card data. Reconcile gateway transactions against internal payment records.

## 7. Audit, privacy and operations

- Audit sensitive actions: role changes, fee edits, refunds, attendance corrections, exam result changes and data exports.
- Validate input on the server and use CSRF protection.
- Rate-limit authentication and public verification endpoints.
- Use secure password hashing, session controls and least-privilege access.
- Keep secrets out of Git; use environment variables or a secret manager.
- Define backup, restore, retention and incident-response procedures before production.
- Log correlation IDs and operational errors without logging passwords, tokens or unnecessary student personal data.

## 8. UI principles

Preserve the reference application's visual language rather than redesigning it:
- Same dark sidebar and compact top navigation
- Same light-gray workspace and white content cards
- Similar KPI cards, charts, tables, status badges and action buttons
- Role-specific dashboard content and concise navigation
- Responsive behavior for desktop, tablet and mobile
- Accessible contrast, keyboard navigation and clear empty/loading/error states

Use reusable Blade components and design tokens so changes remain consistent.
