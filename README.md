# montaqim-# منتقم — صفحة الهبوط 🚀

صفحة هبوط لبوت تيليجرام **@Inviteai_bot**، تنشر على **montaqim.com** عبر Cloudflare Workers (static assets).

## محتوى الحزمة

```
montaqim/
├─ public/
│  └─ index.html      ← الصفحة (ثيم داكن، RTL، تصميم متجاوب)
├─ wrangler.jsonc     ← إعدادات Cloudflare
├─ package.json       ← يثبّت إصدار wrangler
└─ README.md          ← هذا الملف
```

## ⚠️ قبل النشر — تأكد من شي واحد

افتح `wrangler.jsonc` وخلّي قيمة `"name"` **نفس اسم الـ Worker** الموجود عندك بالـ Cloudflare Dashboard.

- شوف الاسم بأعلى صفحة الـ Worker (تبويب **Overview**).
- إذا اسمه `montaqim-` بشرطة، غيّر السطر لـ `"name": "montaqim-"`.

## شلون تنشر (من الموبايل، عبر GitHub)

ارفع الملفات لمستودعك `Maliki313/montaqim-` على فرع `main`:

1. افتح المستودع على GitHub → **Add file** → **Create new file**.
1. بخانة اسم الملف اكتب: `public/index.html` (هيك يصير المجلد تلقائياً)، الصق محتوى الصفحة، واضغط **Commit changes** على `main`.
1. كرّر نفس الشي لـ `wrangler.jsonc` و `package.json` و `README.md` (بالجذر مباشرة بدون مجلد).
1. روح لـ Cloudflare → الـ Worker → **Deployments** → اضغط **Retry build**.

البناء راح يمرّ: **Cloning ✓ → Installing ✓ → Deploying ✓**.

## ربط الدومين montaqim.com

بعد نجاح النشر: من صفحة الـ Worker → **Settings** → **Domains & Routes** → **Add** → **Custom domain** → اكتب `montaqim.com`.
بما إن الدومين أصلاً على Cloudflare، راح يضيف سجلات DNS تلقائياً.

## شنو تعدّل بالصفحة

افتح `public/index.html` ودوّر على التعليقات `<!-- عدّل ... -->`:

- **العنوان والوصف** (داخل `<head>`) — مهم لمحركات البحث ومشاركة الرابط.
- **نص الـ Hero** — الجملة الرئيسية ووصف البوت.
- **المزايا** (قسم features) — الثلاث بطاقات.
- اسم العلامة `منتقم` يتكرر بأكثر من مكان لو حبيت تغيّره.

كل روابط “ابدأ” تروح لـ `https://t.me/Inviteai_bot` — غيّرها لو تغيّر اسم البوت.

## تجربة محلية (اختياري، على الكمبيوتر)

```bash
npm install
npm run dev      # معاينة محلية
npm run deploy   # نشر يدوي
```