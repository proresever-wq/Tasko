# Tasko V17 Final Checklist

## UI / navigation
- [x] Sticky full-height sidebar with internal scroll.
- [x] No unnecessary Control Center normal-settings clutter.
- [x] Control Center contrast improved.
- [x] Header account button routes to role-specific profile/account page.
- [x] Browser back/fallback navigation retained.
- [x] Action Center fixed at top.
- [x] Needs-action workflow data sorted separately from completed work.

## Localization / signup
- [x] First visit uses browser/device language.
- [x] Manual Arabic/English choice persists.
- [x] Auth/navigation/status labels have centralized translation coverage.
- [x] Countries and cities are structured.
- [x] City list filters by country.
- [x] DOB + calculated age stored.
- [x] Gender restricted to Male/Female.
- [x] Acquisition source single-choice with Other text.
- [x] Demographic declaration and Terms/Fair Play consent stored with version/timestamp.

## Users / levels / referrals
- [x] Central level ladder with progressive XP thresholds.
- [x] Features use level IDs rather than raw XP requirements.
- [x] Referral pending state at registration.
- [x] Qualification uses approved task count.
- [x] One-time referrer reward and referred-user gift.
- [x] Self/duplicate referral protection.
- [x] Test Center server-side restricted to user accounts.
- [x] Sandbox Cash/Points/XP/Level/Package/account state controls.
- [x] Level change synchronizes XP to central minimum.

## Tasks / campaigns
- [x] Published campaigns are actual user tasks.
- [x] Unpublished campaigns are hidden from user task API.
- [x] Real Start/Submit campaign execution flow.
- [x] Server-side eligibility checks.
- [x] Idempotency for task/campaign/withdrawal financial paths.
- [x] Campaign lifecycle statuses.
- [x] Campaign targeting fields supported.
- [x] Campaign analytics include budget/spend/remaining/clicks/conversions/progress.
- [x] Advertiser campaign analytics separated from advertiser account information.
- [x] Reference IDs on important records.
- [x] Linked task → attempt → reward → transaction chain available.

## Money / withdrawals
- [x] CliQ withdrawal data.
- [x] Bank withdrawal data.
- [x] Pending → Processing → Approved/Rejected.
- [x] Configurable percentage/fixed withdrawal fees.
- [x] Balance hold and rejection refund.
- [x] Failed invalid requests do not create financial transactions.
- [x] Idempotency prevents duplicate withdrawal creation.

## Admin / Owner operations
- [x] Violations management.
- [x] Sensitive action confirmation.
- [x] High-risk double confirmation.
- [x] Action Center.
- [x] Human-readable activity log.
- [x] Pagination/date filtering support.
- [x] Bulk actions.
- [x] Archive/restore.
- [x] Internal notes.
- [x] Saved filters.
- [x] Global admin search.
- [x] Conflict/stale-update protection.
- [x] Undo marker for reversible audit operations.
- [x] Session/device visibility and logout-all.
- [x] System Health.
- [x] Error Center.
- [x] Owner backup/restore.
- [x] Feature flags.

## Security / deployment
- [x] Per-account Owner/Admin PIN environment variables.
- [x] Postback secret environment variable.
- [x] No real PINs committed to source.
- [x] Rate limiting retained.
- [x] Security headers retained.
- [x] Atomic DB save retained.
