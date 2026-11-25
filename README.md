# Coaching ERP Platform

A multi-branch coaching institute management platform combining an operations ERP with a structured online learning experience.

## Product direction

- Preserve the familiar Webotapp-style interface: dark left sidebar, compact top bar, light workspace, KPI cards, charts, tables, filters and consistent spacing.
- Provide separate role dashboards and role-specific navigation.
- Keep shared business data and workflows connected across admissions, students, academics, finance and learning.
- Add a focused student learning portal for recorded lessons, live classes, assignments, assessments and progress.
- Use BossCoder Academy only as a reference for learning-product capabilities. Do not copy its branding, assets, text or proprietary UI.

## Roles

- Super Admin
- Branch Manager / Branch Admin
- Counsellor
- Accountant
- Faculty
- Student
- Parent (optional portal; permissions and workflows to be confirmed)

The demo role switcher seen in the reference application is not a production authorization model. Production access must come from authenticated user roles and server-side permissions.

## Planned modules

1. Identity, roles, permissions and audit trail
2. Company, institutes, branches, academic years and configuration
3. Leads, enquiries, follow-ups, counselling and admissions
4. Student profiles and student 360 view
5. Courses, subjects, curriculum and learning paths
6. Batches, cohorts, classrooms, timetable and faculty allocation
7. Attendance for students and faculty
8. Fees, instalments, discounts, payments, receipts, cashier desk and expenses
9. Recorded video lessons, learning materials and progress tracking
10. Live class scheduling, meeting links and attendance
11. Assignments, submissions, reviews and feedback
12. Question bank, exams, online tests, results and scorecards
13. Certificates and public verification
14. Reports, dashboards, notifications and exports

## Technology baseline

The reference application uses Laravel 11, PHP 8.2+, Blade, Tailwind CSS, Alpine.js, Chart.js and a relational database. The new project will retain this familiar stack initially, with the production database selected during environment setup. Architecture decisions and version upgrades will be documented before implementation.

## Repository status

This repository is the clean successor project. The reference repository and any older private repositories remain untouched. Initial architecture and feature-planning documents are in `docs/`.

## Build sequence

1. Confirm architecture, tenant boundaries and role permissions.
2. Scaffold the Laravel application and shared UI shell.
3. Implement authentication, authorization and organization/branch scoping.
4. Build role dashboards and navigation.
5. Implement core ERP workflows.
6. Implement the learning portal and content workflows.
7. Add automated tests, observability, backups and deployment configuration.

See [Architecture](docs/ARCHITECTURE.md), [Feature matrix](docs/FEATURE-MATRIX.md) and [Implementation plan](docs/IMPLEMENTATION-PLAN.md).
