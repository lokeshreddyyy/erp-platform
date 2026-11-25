# Feature and role matrix

This is the initial product scope. Permissions must be refined before implementation and enforced on the server.

| Feature area | Super Admin | Branch Manager | Counsellor | Accountant | Faculty | Student |
|---|---|---|---|---|---|---|
| Company / institute settings | Full | View branch scope | — | — | — | — |
| Branches and users | Full | Branch-scoped | — | — | — | — |
| Leads and follow-ups | Full | Branch-scoped | Assigned leads | — | — | — |
| Admissions | Full | Branch-scoped | Create/process | View limited | — | Own admission status |
| Student directory / 360 | Full | Branch-scoped | Relevant prospects | Fee-relevant fields | Assigned students | Own profile |
| Courses / curriculum | Full | Branch-scoped | View | — | Assigned courses | Enrolled courses |
| Batches / timetable | Full | Branch-scoped | View availability | — | Assigned batches | Own timetable |
| Attendance | Full | Branch-scoped | — | — | Mark assigned cohorts | View own |
| Fees / instalments | Full | Branch-scoped | Limited status | Collect/manage | — | View own |
| Receipts / refunds | Full | Branch-scoped | — | Authorized actions | — | View own receipts |
| Expenses | Full | Branch-scoped | — | Create/manage | — | — |
| Video lessons / materials | Full | View | — | — | Publish assigned content | Consume enrolled content |
| Live classes | Full | View | — | — | Schedule/host assigned | Join enrolled sessions |
| Assignments | Full | View | — | — | Create/review | Submit/view feedback |
| Exams / question bank | Full | View limited | — | — | Create/evaluate | Attempt/view results |
| Certificates | Full | Branch-scoped | — | — | Recommend/verify | View/download own |
| Reports | Consolidated | Branch reports | Lead funnel | Finance | Academic | Personal progress |
| Audit / security settings | Full | Limited operational | — | — | — | — |

Legend: Full = organization-wide authorized administration; Branch-scoped = limited to assigned branch; Own = the user's own records; Assigned = records explicitly assigned to that user; — = no default access.

## Dashboard content

### Super Admin
- Consolidated enrolments, leads, collections, expenses and operating surplus
- Branch filter and branch comparison
- Financial performance and enquiry pipeline
- Recent enquiries and receipts
- Operational alerts and audit activity

### Branch Manager
- Branch enrolments, admissions, active batches and attendance
- Branch collections and outstanding dues
- Lead/admission funnel
- Batch capacity, timetable and staff coverage
- Branch-level operational exceptions

### Counsellor
- Assigned leads and follow-ups due today
- Pipeline by status and conversion rate
- Priority enquiry queue
- Counselling schedule and admission actions

### Accountant
- Gross collections, today's inflow, receivables and expenses
- Recent receipts and pending instalments
- Collection actions and reconciliation exceptions
- Finance reports within authorized branch scope

### Faculty
- Active cohorts and enrolled learners
- Today's teaching schedule
- Attendance actions for assigned cohorts
- Assignments to review and exams to conduct
- Assigned course materials and learner progress

### Student
- Enrolled courses and next learning activity
- Continue-learning video progress
- Upcoming live classes
- Attendance, assignments and exam schedule
- Results, fee instalments, receipts and certificates

## Scope rules

- Hide irrelevant navigation, but never rely on hidden navigation for access control.
- Do not expose the demo role switcher in production.
- A user may hold multiple roles or branch assignments; resolve effective permissions from assignments, not a hard-coded single role assumption.
- Parent portal remains optional until its data relationships and consent requirements are confirmed.
