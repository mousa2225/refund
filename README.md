# نظام استرداد العملاء — V-SHAPE

نظام إدارة استرداد مبالغ العملاء مبني على Firebase Firestore.

## هيكل الملفات

```
vshape/
├── index.html          ← الصفحة الرئيسية
├── css/
│   └── styles.css      ← جميع أنماط CSS
├── js/
│   ├── config.js       ← إعدادات Firebase والمتغيرات العامة
│   ├── utils.js        ← دوال مساعدة (تاريخ، توست، فلترة...)
│   ├── auth.js         ← تسجيل الدخول، إنشاء حساب، طلبات كلمة المرور
│   ├── app.js          ← منطق التطبيق الرئيسي (جدول، إضافة عميل...)
│   ├── admin.js        ← لوحة تحكم المدير
│   └── export.js       ← تصدير Excel
└── README.md
```

## كيفية الرفع على GitHub Pages

### 1. أنشئ مستودع GitHub جديد
```
اسمه: vshape  (أو أي اسم تريده)
اجعله: Public
```

### 2. ارفع الملفات
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/USERNAME/vshape.git
git push -u origin main
```

### 3. فعّل GitHub Pages
```
Settings → Pages → Source: Deploy from a branch
Branch: main / root
Save
```

### 4. رابط موقعك
```
https://USERNAME.github.io/vshape/
```

---

## إعداد Firebase

1. روح [console.firebase.google.com](https://console.firebase.google.com)
2. أنشئ مشروع جديد أو استخدم الموجود
3. فعّل **Firestore Database** (وضع الاختبار)
4. في تبويب **القواعد** استبدل بـ:
```
allow read, write: if true;
```
5. غيّر بيانات `FC` في `js/config.js` ببيانات مشروعك

---

## المميزات
- ✅ إضافة / حذف / تعديل العملاء
- ✅ نظام حالات: تم الرفع → قيد المراجعة → تم الاسترداد
- ✅ تحويل تلقائي حسب وقت محدد
- ✅ تصدير Excel مع تنسيق احترافي
- ✅ لوحة تحكم للمدير (مستخدمين، صلاحيات، طلبات كلمة المرور)
- ✅ دعم الوضع الداكن / الفاتح
- ✅ فلترة متقدمة بالتاريخ
- ✅ حساب تلقائي للمبلغ المسترد
