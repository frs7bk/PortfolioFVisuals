# تعليمات النشر على Render

## متطلبات النشر

1. قاعدة بيانات PostgreSQL
2. بيئة تشغيل Python 3.9+

## المتغيرات البيئية المطلوبة:

```
# إعدادات قاعدة البيانات 
DATABASE_URL=postgresql://username:password@hostname:port/database_name
PGDATABASE=database_name
PGHOST=hostname
PGPORT=port
PGUSER=username
PGPASSWORD=password

# سر الجلسة
SESSION_SECRET=your_secure_random_string

# إعدادات تيليجرام (اختياري)
TELEGRAM_BOT_TOKEN=your_telegram_bot_token
TELEGRAM_CHAT_ID=your_telegram_chat_id
```

## خطوات النشر على Render:

1. قم بإنشاء قاعدة بيانات PostgreSQL جديدة.
2. قم بإنشاء خدمة Web Service جديدة مع الإعدادات التالية:
   - Runtime: Python 3
   - Build Command: `pip install -r requirements.txt`
   - Start Command: `gunicorn --bind 0.0.0.0:$PORT main:app`
3. قم بإضافة المتغيرات البيئية المذكورة أعلاه.

## ملاحظات هامة:

1. اسم مستخدم المسؤول الافتراضي: `admin`
2. كلمة مرور المسؤول الافتراضية: `admin123`
3. قم بتغيير كلمة المرور فور تسجيل الدخول الأول.
4. يمكنك رفع صور جديدة بعد تشغيل الموقع.

## الإصلاحات المضمنة:

- ✅ إصلاح مشكلة عرض رسائل النجاح بعد إرسال نماذج التواصل
- ✅ إصلاح مشكلة عرض رسائل النجاح بعد إرسال التقييمات
- ✅ إصلاح مشكلة عرض رسائل النجاح بعد طلب الخدمات
- ✅ إصلاح مشكلة الوصول إلى لوحة الإحصائيات للمسؤول

تم إعداد هذه الحزمة بتاريخ: 2025-05-10 22:42:54
