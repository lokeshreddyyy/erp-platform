# Implementation plan

## Phase 0 — Foundation and decisions
- [x] Create clean repository.
- [x] Record product direction and reference UI principles.
- [x] Draft initial architecture and role/feature matrix.
- [ ] Confirm company/institute/branch tenancy model.
- [ ] Confirm supported payment methods and refund approval flow.
- [ ] Select video hosting, live-class and notification providers.
- [ ] Confirm production hosting, database and backup requirements.

## Phase 1 — Application foundation
- [ ] Scaffold Laravel application and pin supported dependency versions.
- [ ] Configure local development, environment examples and CI.
- [ ] Add migrations, factories and seed data.
- [ ] Implement authentication, password reset and session security.
- [ ] Implement roles, permissions, policies and branch scoping.
- [ ] Create shared Webotapp-style layout and reusable UI components.
- [ ] Add audit logging and error handling.

## Phase 2 — Core ERP
- [ ] Company, institutes, branches and academic years
- [ ] Leads, enquiries, follow-ups and counselling
- [ ] Admissions and enrolment
- [ ] Student directory and student 360 profile
- [ ] Courses, subjects, batches, classrooms and timetable
- [ ] Student/faculty attendance

## Phase 3 — Finance
- [ ] Fee plans, instalments, discounts and scholarships
- [ ] Payment collection and gateway integration
- [ ] Receipts, refunds and reconciliation
- [ ] Cashier desk and expenses
- [ ] Finance reports and audit trail

## Phase 4 — Learning platform
- [ ] Course/module/lesson hierarchy
- [ ] Secure video playback and progress tracking
- [ ] Live class schedule and attendance integration
- [ ] Study materials and handouts
- [ ] Assignments, submissions, reviews and feedback
- [ ] Question bank, online exams, attempts and results
- [ ] Certificates and verification

## Phase 5 — Role experiences and reporting
- [ ] Super Admin dashboard
- [ ] Branch Manager dashboard
- [ ] Counsellor dashboard
- [ ] Accountant dashboard
- [ ] Faculty dashboard
- [ ] Student dashboard
- [ ] Reports, notifications and exports

## Phase 6 — Quality and release
- [ ] Unit and feature tests for workflows and policies
- [ ] Cross-branch isolation tests
- [ ] Payment idempotency and reconciliation tests
- [ ] Accessibility and responsive UI checks
- [ ] Security review and dependency scanning
- [ ] Load/performance testing
- [ ] Backup/restore drill
- [ ] Staging deployment, UAT and production release

## Definition of done

A feature is not complete merely because its menu item or screen exists. It must include validated workflows, server-side authorization, tenant scoping, useful empty/error/loading states, audit coverage where sensitive, automated tests and documentation.
