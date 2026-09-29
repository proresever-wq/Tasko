# Tasko V18 — Comprehensive accumulated implementation

V18 is an incremental modification of the V17 base. The existing architecture was retained; the pass closes the accumulated requirements and the later clarifications.

## Included
- Responsive desktop/mobile sidebar behavior across roles, including desktop collapse and mobile auto-close after navigation.
- Control Center reduced to critical platform/emergency operations.
- Language behavior frozen to the existing mixed Arabic/English style; automatic translation output is disabled and account/company names are never translated.
- Public landing page plus separate public information pages and separate User / Advertiser / Admin / Owner login routes.
- Google/Facebook OAuth integration hooks and Cloudflare Turnstile frontend/backend verification, controlled by Render environment variables.
- Admin/Owner direct credentials remain separate from social login.
- Jordan / Amman time is the single system timezone; no manual timezone selector.
- User package subscription information includes package type, subscription date, expiration, days remaining and status.
- User packages remain separate from campaigns. Package management supports creation, Active/Inactive/Archived status, 1–5 real priority, historical snapshotting, and centralized levels.
- Campaign lifecycle: create → review/approve → configure Free/Plus/Premium independently → publish. Active campaigns open to analytics first, with logical Edit/Pause/Resume/Stop actions.
- Campaign package configuration carries eligibility, Cash, Points, XP, level, dates and limits; rewards use the selected package configuration at execution time.
- Published campaigns are real user tasks; unpublished campaigns are excluded from user task APIs.
- Additional tasks/challenges can be automatic or require explicit Start; future challenges can be shown as Upcoming; automatic completion rewards when conditions are met.
- User activity page shows meaningful activity only for the latest 14 days; older records remain stored for Admin/Owner history.
- Sandbox remains server-side restricted to User-role accounts; XP and Level remain synchronized and all five levels are available.
- Central level configuration/API added so future levels can propagate to selectors and level calculations.
- Advertiser approval now separates approval from account creation; account creation accepts editable email and an Owner/Admin-entered password.
- System Health / Security & Integrity now performs scheduled checks, stores findings/history, tracks severity and resolved issues, and reports real data counts.
- Session/device records include IP, user-agent and timestamps.
- Unsaved-change protection, idempotent task/campaign/withdrawal paths, human-readable activity logging, reference IDs, lifecycle-aware actions, and existing security/audit protections retained.
- Environment secrets expanded for OAuth and Turnstile; no secrets are embedded in UI/source.

## Verification
- `node --check server.js`
- `node --check js/app.js`
- Local API smoke tests for User/Admin/Owner login, package config, levels, tasks, System Health, provider configuration, emergency confirmation and signup validation.
- Existing V17 base copied incrementally; V14 remains untouched.

## V19 targeted fixes — 2026-09-29
- Removed duplicate top-level function declarations from `js/app.js`, keeping the last existing definition for each duplicated name.
- Added 5-per-hour-per-IP rate limiting to public `/api/advertiser/request`.
- Escaped JSON data interpolated into single-quoted `onclick` attributes with `&#39;` protection.
- Fixed the four login-page Turnstile initialization branches so `setTimeout(v18InitTurnstile,0)` is reached before returning.
- Confirmed `index.html` paths match `css/main.css` and `js/app.js`.
- No historical V15–V18 sections were removed.


## V20 — Comprehensive account/workflow pass
- Directly modified the V19 source without recreating the project.
- Added 248-country catalog (Israel excluded), bilingual country display, searchable city entry, backend country validation and country config API.
- Hardened User/Advertiser/Admin/Owner login/session flow, remember-device behavior, profile editing, password/security settings and session management.
- Added task/campaign submission rate limits, withdrawal rate limiting and optional email/phone verification gates, plus idempotent reward redemption and real package duration handling.
- Fixed the admin advertiser account endpoint and preserved the dedicated advertiser information model without user wallet/XP fields.
- Removed advertiser budget/spend from the User task presentation.
- Kept the DB and all existing V19 functionality in place; V20 ZIP includes data/db.json.
