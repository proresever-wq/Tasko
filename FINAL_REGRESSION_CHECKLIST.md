# Tasko final regression checklist

- [x] Owner/Admin second 4-digit confirmation is required for sensitive operations.
- [x] Test-user package switching requires confirmation and updates the open profile modal in place.
- [x] Closing a user profile closes the modal; it does not use browser history/back navigation.
- [x] Owner/Admin has a dedicated Reward Management screen with create/edit/activate/deactivate/delete.
- [x] Reward management actions require the second confirmation code.
- [x] Referral records are shown on the referrer account, not the newly registered referred account.
- [x] Self/invalid referral IDs are ignored.
- [x] Referral qualification credits the referrer only once after a real approved task.
- [x] Referred user gift is credited on qualification only once.
- [x] Reward CRUD API is server-side permission protected.
- [x] Package switch API is server-side permission + confirmation protected.
- [x] Node syntax checks pass for server.js and js/app.js.
- [x] Health endpoint responds successfully in local smoke test.

## V14 consolidated checks
- [x] Per-admin/owner 4-digit security PIN is verified against the current authenticated account; no shared PIN is accepted when a personal PIN exists.
- [x] Second Owner account is seeded with full owner permissions.
- [x] Admin permission editing uses toggles; navigation is filtered by permission and server APIs remain permission-protected.
- [x] User/admin/advertiser/owner profiles expose a stable Account ID with copy action.
- [x] Admin user search includes Account ID.
- [x] User tasks include published additional/admin-created tasks when eligible.
- [x] User support tickets support replies; admin can close tickets; closed tickets are read-only.
- [x] Audit log is human-readable instead of raw JSON and is kept inside the main content area.
- [x] Desktop profile modal uses a wider responsive layout and keeps package controls from covering account data.
- [x] Browser routes are real paths with history/back/forward support; non-API routes fall back to index.html.
- [x] Advertiser refresh restores advertiser role and advertiser accounts do not expose user package switching.
- [x] Sandbox can edit test-user cash/points/XP/package/account state and is isolated behind sandbox permission.
- [x] Preview user flow supports task, package, support, and wallet simulation without real financial effects.
- [x] Arabic/English language switcher changes document direction and applies the central UI translation layer.
- [x] Premium theme includes restrained gold accents and motion.
