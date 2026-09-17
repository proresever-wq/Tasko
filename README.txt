TASKO V12 — Security + UX Fix Build

تشغيل Termux:
cd ~/storage/shared/Tasko/Tasko_Prototype_V13_Portal_UX_Security
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
