TASKO V17 — Complete accumulated change set

تشغيل Termux:
cd ~/storage/shared/Tasko/Tasko_Prototype_V14_Portal_UX_Security
node server.js
ثم افتح: http://127.0.0.1:3000

حسابات الاختبار:
Owner: owner@tasko.test / 123456
Admin Operations: admin@tasko.test / Tasko@Admin1
Admin Users: admin-users@tasko.test / Tasko@123
Admin Tasks: admin-tasks@tasko.test / Tasko@123
Admin Support: support@tasko.test / Tasko@123
User Demo: user@tasko.test / Tasko@User1
User 1: user1@tasko.test / Tasko@123
Advertiser Demo: advertiser@tasko.test / Tasko@Advert1
Advertiser 1: advertiser1@tasko.test / Tasko@123
VIP Advertiser: vip-advertiser@tasko.test / Tasko@123

ما تم إصلاحه في V12:
- إزالة توثيق الهاتف القديم من التسجيل والواجهة والـAPI.
- إضافة Rate Limiting لمحاولات الدخول والتسجيل واستعادة كلمة المرور.
- حفظ قاعدة البيانات بطريقة atomic عبر temp file + rename مع إنشاء مجلد data تلقائياً.
- إضافة Security Headers ورفض JSON غير صالح.
- رمز التأكيد الإداري لم يعد مكتوباً داخل العمليات؛ يقرأ من TASKO_CONFIRM_PIN مع fallback للتجربة المحلية.
- Postback secret أصبح إعداداً بيئياً بدلاً من قيمة ثابتة.
- إضافة استعادة كلمة المرور كنموذج تجريبي one-time token؛ في الإنتاج يجب إرسال الرابط عبر مزود بريد موثوق.
- عدم تخزين كلمة مرور المعلن المؤقتة داخل طلب المعلن؛ تظهر مرة واحدة في استجابة الموافقة فقط.
- تقارير وتحليلات تفصيلية + سجل عمليات قابل للبحث والتصفية والفترة الزمنية.
- الصفحة الرئيسية مختصرة، بينما التفاصيل الكاملة في التقارير.
- متجر المكافآت يعتمد على Points + XP/Level + Package ويقبل تصنيف الشريك/نوع الاسترداد.
- صفحة المهمة تعرض التفاصيل والمتطلبات قبل البدء.
- الملف الشخصي مرتب مع بيانات الحساب والمستوى والباقة والأمان.
- Premium يطبق الثيم الداكن فور تحديث الباقة في النموذج التجريبي.

ملاحظة مهمة:
هذه نسخة Prototype للاختبار وليست جاهزة لإطلاق مالي حقيقي. قبل الإنتاج الحقيقي يلزم قاعدة بيانات إنتاجية، جلسات إنتاجية، مزود دفع، بريد استعادة حقيقي، تكاملات معلنين حقيقية، مراجعة قانونية ومحاسبية، واختبار أمني مستقل/penetration test.


Portals:
- User: http://127.0.0.1:3000/
- Admin: http://127.0.0.1:3000/admin
- Advertiser: http://127.0.0.1:3000/advertiser

The public root does not display the Admin/Advertiser portal selector.


V14 note: each Admin/Owner has an individual 4-digit security PIN. Production should set unique TASKO_PIN_* values as private environment variables; never commit real PINs.


V17: Complete accumulated Tasko change set. V14 remains the untouched backup baseline.

TASKO V19 — targeted security/consistency fixes
- Removed duplicate top-level function declarations in js/app.js; the duplicate-name check must return [].
- Added IP rate limiting to the public advertiser account-request endpoint: 5 requests/hour.
- Escaped JSON values embedded in single-quoted onclick attributes with HTML apostrophe escaping.
- Fixed the four login-page Turnstile initialization branches so initialization is scheduled before return.
- index.html uses /css/main.css and /js/app.js, matching the project directories.
- V19 verification: server/client syntax checks and live role-login smoke tests.


V20 — Comprehensive Tasko workflow/account pass
- V19 retained as the direct base; no rebuild/recreation.
- Completed the requested account/login architecture across User, Advertiser, Admin and Owner portals, including session persistence/remember-device behavior, password recovery/change, profile settings, session visibility, role separation and direct administrative credentials.
- Added country catalog for all supported world countries except Israel, bilingual country presentation and free searchable city entry with capital suggestions; backend rejects Israel and invalid/empty locations.
- Strengthened task/campaign submission rate limits, withdrawal rate limits/verification gates, reward redemption idempotency, and package lifecycle snapshots/dates.
- Added user/advertiser settings access and removed advertiser financial/user-wallet fields from advertiser account views.
- User task cards no longer expose advertiser budget/spend.
- Added countries.json to the project and kept data/db.json in the V20 archive.


V21 — Public-site, authentication, mobile navigation, task/package/reward UX pass
- Reworked public pages into full, detailed user-facing content without repeated login/business buttons.
- Added searchable FAQ with a broad practical question set.
- Unified User Login/Create Account into one page with tabs and branded Google/Facebook buttons.
- Added bilingual country/city suggestions and retained free city entry for valid countries.
- Replaced duplicated authenticated menu buttons with one stable menu control and fixed Tasko branding placement.
- Reworked task cards/details by task type and added remaining participant information for campaigns when configured.
- Reworked user packages into publication-ready detail cards and a full detail modal; no direct activation from the package card.
- Reworked Rewards Store with search, real category filtering, sorting and pagination (24 per page) for large catalogs.
