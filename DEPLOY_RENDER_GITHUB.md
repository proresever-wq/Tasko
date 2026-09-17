# Tasko — Render + GitHub deployment

## GitHub
1. Create a GitHub repository for Tasko.
2. Upload the project root (do not put the project inside another nested project folder).
3. Never commit `.env` or production secrets.
4. Keep `.env.example` as the template only.

## Render
- Service type: Web Service
- Runtime: Node
- Build command: `npm install`
- Start command: `npm start`
- Environment variables:
  - `NODE_ENV=production`
  - `TASKO_CONFIRM_PIN=<your private 4-digit PIN>`
  - `TASKO_POSTBACK_SECRET=<long random secret>`
- Deploy from the GitHub repository.

Render can automatically deploy a new commit when GitHub integration is enabled. Keep production secrets only in Render Environment Variables.

## Important production note
This prototype stores data in `data/db.json`. A production deployment should move persistent user/financial/task data to a proper managed database before real-money launch, and add backups/recovery plus an independent security review.
