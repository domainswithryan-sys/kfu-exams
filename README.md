# KFU Exams Portal — دليل الإعداد والاستخدام

## هيكل المشروع
```
index.html              ← الصفحة الرئيسية (قائمة الامتحانات)
exams/
  carbohydrate-chemistry.html   ← أول امتحان
vercel.json              ← إعدادات الروابط النظيفة (من غير .html)
```

## الإعداد لأول مرة (خطوة واحدة، متعملش غير مرة)

1. اعمل حساب على https://github.com لو معندكش.
2. اعمل Repository جديد (زرار "New repository" الأخضر) — سمّيه مثلاً `kfu-exams`، خليه Public أو Private (مفيش فرق).
3. في صفحة الريبو الفاضية، دوس "uploading an existing file" وارفع كل الملفات اللي في المجلد ده (`index.html`, `vercel.json`, ومجلد `exams` بالكامل) — من غير أي حاجة تتكتب في Terminal.
4. اعمل Commit.
5. روح https://vercel.com/new وسجل دخول بنفس حساب GitHub، اختار الريبو `kfu-exams`، دوس Deploy.
6. فيرسل هيديك لينك ثابت زي `kfu-exams.vercel.app` — ده اللينك اللي هيفضل زي ما هو للأبد.

## إضافة امتحان جديد (كل مرة بعد كده)

1. ولّد ملف الامتحان (HTML) زي المعتاد.
2. في صفحة الريبو على GitHub، ادخل مجلد `exams/`، دوس "Add file" → "Upload files"، وارفع ملف الامتحان الجديد (مثلاً `amino-acids.html`).
3. افتح ملف `index.html` من على GitHub (زرار القلم ✏️ للتعديل)، وضيف سطر جديد في مصفوفة `EXAMS` زي:
   ```js
   { subject: "Biochemistry", title: "Amino Acids — Comprehensive Examination", path: "/exams/amino-acids", meta: "128 questions · 168 points · 120 minutes" },
   ```
4. احفظ (Commit changes مباشرة على main).
5. فيرسل هينشر التحديث تلقائيًا خلال ثواني — من غير ما تلمس فيرسل أصلاً.

اللينك الرئيسي `kfu-exams.vercel.app` ولينك كل امتحان قديم بيفضلوا شغالين زي ما هما، مفيش استبدال ولا كتابة فوق حاجة.

## ملاحظة تقنية
كل ملف امتحان مستقل بذاته (self-contained) وبيحفظ تقدم الطالب في متصفحه هو بس (localStorage) — مفيش قاعدة بيانات مركزية، فكل طالب لازم يفتح ويكمل من على نفس الجهاز/المتصفح اللي بدأ بيه.
