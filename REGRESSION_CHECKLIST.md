# Tasko Regression Checklist

Run after every functional change. Keep the baseline commit available before each change.

## Auth & Portals
- [ ] User login works at `/`
- [ ] User signup requires consent + Fair Play read/acceptance
- [ ] Admin login works only at `/admin`
- [ ] Advertiser login works only at `/advertiser`
- [ ] Cross-portal login is rejected server-side
- [ ] Remember-device behavior is correct
- [ ] Logout invalidates the user's sessions
- [ ] Login rate limiting still works

## Core Tasks
- [ ] Task list loads
- [ ] Eligibility by level/package is enforced server-side
- [ ] Start task creates an attempt
- [ ] Submit moves attempt to pending
- [ ] Duplicate/invalid submission is rejected
- [ ] Admin approval credits Points + XP once
- [ ] Admin rejection does not credit rewards
- [ ] Daily limits are enforced

## Wallet & Rewards
- [ ] Wallet displays correct Points/Cash
- [ ] Withdrawal request works
- [ ] Withdrawal approval works
- [ ] Withdrawal rejection refunds correctly
- [ ] Duplicate withdrawal processing is rejected
- [ ] Reward redemption validates Points/Level/Package server-side

## Admin & Advertiser
- [ ] Owner dashboard loads all sections
- [ ] Admin permissions are enforced server-side
- [ ] Package changes require secondary confirmation
- [ ] Emergency controls require secondary confirmation
- [ ] Audit logs record sensitive actions
- [ ] Advertiser request is stored
- [ ] Advertiser campaign flow loads
- [ ] Advertiser cannot access admin endpoints

## Security & Reliability
- [ ] Security headers are present
- [ ] Invalid JSON is rejected safely
- [ ] No secrets are hard-coded in frontend assets
- [ ] Postback secret is server-side and idempotent
- [ ] Database writes remain atomic
- [ ] Dynamic HTML uses the `esc()` helper where needed
- [ ] No unexpected `<script>` nesting exists in generated HTML/JS
- [ ] `node --check server.js` passes
- [ ] `data/db.json` remains valid JSON
