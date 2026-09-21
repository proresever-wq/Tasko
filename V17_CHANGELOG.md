# Tasko V17 — Complete accumulated change set

V17 is an incremental modification of the existing Tasko V16/V14 structure. No rebuild or replacement of the product architecture was performed.

## Completed change set
- Fixed viewport/sidebar behavior, full-height sticky side navigation, internal scrolling and action-center positioning.
- Improved Control Center contrast and limited it to critical platform controls.
- Emergency controls are independent: registration, tasks, withdrawals and maintenance; sensitive actions use account-specific confirmation codes.
- Maintenance mode is real and blocks public access while authorized administration remains available.
- Browser/device language is the first-visit default; manual language selection persists.
- Central Arabic/English translation coverage expanded, including auth copy, acquisition sources, countries/cities, statuses and dynamic labels.
- User registration stores country, city, DOB, calculated age, gender, acquisition source and demographic/terms consent with version/timestamp.
- Country/city are structured and city choices are filtered by country; gender is Male/Female only.
- Referral flow: pending at signup, no immediate reward, qualification after configurable approved-task count, one-time referrer reward + referred-user gift, self/duplicate protection.
- Central Level definitions use Bronze/Silver/Gold/Platinum/Diamond and features reference level IDs rather than raw XP requirements.
- Sandbox/Test Center is restricted server-side to role=user accounts and supports Cash, Points, XP, Level, Package and account-state changes; direct level sets central minimum XP and XP recalculates level.
- Published campaigns are the real campaign tasks; unpublished campaigns are excluded from user APIs.
- Real campaign execution flow: Start → Execute → Submit → Pending/Approved, with idempotency and server-side eligibility.
- Campaign lifecycle/status transitions, workflow logging, targeting checks and linked attempt/reward/transaction history are retained.
- Advertiser Account Information is separate from My Campaigns; advertiser analytics show budget, spent, remaining, clicks, conversions and progress.
- Withdrawal flow supports CliQ/bank details, Pending/Processing/Approved/Rejected states, configurable percentage/fixed fees, idempotency, hold/refund accounting and linked transactions.
- Activity logs are human-readable with operation-specific details, pagination and date filters.
- Violations support search, recording, severity, actions and audit history.
- Action Center summarizes items needing action; workflow lists prioritize pending campaign/task/withdrawal work.
- Added system health, technical Error Center, active-session visibility, logout-all-sessions, Owner backup/restore and controlled feature flags.
- Added internal Admin/Owner notes, saved filters, bulk actions, archive/restore, global admin search, conflict detection and undo markers.
- Sensitive actions use confirmation and high-risk operations can require double confirmation.
- Environment-based per-account Owner/Admin PIN architecture is preserved; real secrets are not committed.

## Verification
- `node --check server.js`
- `node --check js/app.js`
- Local API health/login smoke test on isolated port.
- New system-health, workflow, errors, sessions and feature-flag endpoints smoke-tested.

## Final audit pass — 2026-09-19
- Added `/api/admin/violations` and `/api/admin/violations/action` aliases to the violations management workflow.
- Added real CSV export responses for admin reports and advertiser exports via `format=csv`.
- Expanded the centralized Arabic/English UI translation dictionary for common dashboard, workflow, campaign, withdrawal, security, and account strings.
- Re-ran server/client syntax checks and live API smoke tests after the final pass.

## Final implementation pass
- Campaign minimum eligibility is now selected by canonical Level (Bronze/Silver/Gold/Platinum/Diamond), not raw XP in the campaign form.
- Signup acquisition-source labels are localized while canonical stored values remain stable.
- Existing V17 architecture and data model retained; no rebuild.
