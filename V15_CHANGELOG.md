# Tasko V15 — targeted update

Built incrementally from Tasko V14 without recreating the project.

- Fixed desktop sidebar viewport/sticky scrolling and added responsive overflow handling.
- Improved Owner Control Center card contrast.
- Extended language switching and dynamic text/alert translation behavior.
- Added dedicated advertiser Account Information page; campaign pages remain campaign-focused.
- Added advertiser-specific admin profile endpoint/view instead of user wallet/XP fields.
- Added sandbox account selector with Cash, Points, XP, package and direct Level controls.
- Centralized Level IDs and thresholds; task/reward/campaign requirements can use level IDs.
- Added user signup country/city, date of birth, gender, acquisition source, and demographic declaration fields with server-side validation.
- Added email/phone verification-ready fields to new user records.
- Changed referral qualification to the configurable default of 3 approved tasks and made reward credit auditable/idempotent.
- Added CliQ/bank withdrawal recipient fields while retaining Pending/approval/rejection workflow.
- Added published campaign visibility to eligible users and campaign progress visualization.
- Replaced raw Activity Log JSON display with organized human-readable details.
- Added Render-ready dedicated environment variable names for each Owner/Admin security PIN.
- Kept V14 untouched as the backup baseline.
