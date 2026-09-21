# Tasko V16 — Incremental control, task execution, localization and workflow pass

Built incrementally from Tasko V15. V14 remains untouched as backup.

## Implemented
- Preserved the existing V15 structure; no rebuild/recreation.
- Fixed viewport sidebar behavior and internal scrolling; added responsive action-center bar.
- Improved control-center visual contrast and reduced Control Center scope to critical platform operations.
- Emergency/platform controls are independent: Registration, Tasks, Withdrawals, Maintenance; sensitive changes require the account-specific 4-digit PIN and save real server state.
- Maintenance mode now serves a clear public maintenance page while Owner/Admin access remains available.
- Added browser/device language as the first-visit default; manual Arabic/English selection remains persisted.
- Expanded localization coverage for authentication, navigation, countries/cities, acquisition sources, statuses, levels, admin labels and dynamic activity details.
- Added dedicated Owner/Admin account profile view through the header account button.
- Advertiser account information remains separate from campaign analytics.
- User-facing task list no longer exposes the legacy static core-task objects; published campaigns and explicit additional tasks are the real task sources.
- Added real campaign task execution flow: Start Task → execute → Submit → Approved/Pending Review, with server-side eligibility and idempotency protection.
- Campaigns not published/active remain unavailable to users through the user task API.
- Centralized Level ladder with Level IDs and progressively higher XP thresholds: Bronze, Silver, Gold, Platinum, Diamond.
- Sandbox now exposes only role=user test accounts; direct Level sets the exact central minimum XP, while manual XP recalculates Level.
- Expanded Violations into a searchable management flow with record/action endpoints and audit history fields.
- Activity Log now returns human-readable operation types and organized details instead of raw JSON as the primary display.
- Preserved environment-based per-account security PIN architecture; no real secrets are stored in source.
- Added/retained reference IDs and audit logging for sensitive workflows.

## Verification
- `node --check server.js`
- `node --check js/app.js`
- Health/login/task API smoke tests run against an isolated local port.
