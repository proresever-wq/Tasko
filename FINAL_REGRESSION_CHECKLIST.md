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
