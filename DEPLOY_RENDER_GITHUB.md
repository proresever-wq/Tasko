# Tasko V15 — Render + GitHub deployment

## GitHub
1. Upload the project root to the repository.
2. Never commit `.env` or real production secrets.
3. Keep `.env.example` as a template only.

## Render
- Service type: Web Service
- Runtime: Node
- Build command: `npm install`
- Start command: `npm start`

### Required private environment variables
Set a different private 4-digit value for every seeded Owner/Admin account:

- `NODE_ENV=production`
- `TASKO_PIN_OWNER1=<private 4-digit PIN>`
- `TASKO_PIN_OWNER2=<different private 4-digit PIN>`
- `TASKO_PIN_ADMIN_OPERATIONS=<private 4-digit PIN>`
- `TASKO_PIN_ADMIN_USERS=<private 4-digit PIN>`
- `TASKO_PIN_ADMIN_TASKS=<private 4-digit PIN>`
- `TASKO_PIN_ADMIN_SUPPORT=<private 4-digit PIN>`
- `TASKO_POSTBACK_SECRET=<long random secret>`

`TASKO_CONFIRM_PIN` is optional and is only a fallback for accounts that do not have their own stored security PIN. Seeded Owners/Admins should use their dedicated variables above.

Do not place any of these values in frontend JavaScript, HTML, GitHub, or the UI.

## Important production note
This prototype stores data in `data/db.json`. Before real-money launch, move persistent user/financial/task data to a managed database, add backups/recovery, enforce verified phone/email before withdrawals, and perform an independent security review.
