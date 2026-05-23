<div align="center">

# 🏛️ Riwaq Pi

**أول سوق عربي للمهارات الرقمية يعمل بـ Pi Network**

[![Sprint](https://img.shields.io/badge/Sprint-6-orange)](https://github.com/kraiem11/riwaqpi)
[![Status](https://img.shields.io/badge/Status-Beta%20Phase-blue)](https://github.com/kraiem11/riwaqpi)
[![Pi Network](https://img.shields.io/badge/Pi%20Network-Integrated-purple)](https://minepi.com)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

[🇹🇳 🇪🇬 🇸🇦 🇦🇪 🇲🇦 🇩🇿 🇯🇴]

</div>

---

## 🎯 ما هو Riwaq Pi؟

منصة عربية متكاملة تربط أصحاب المهارات الرقمية (مصممين، مبرمجين، مترجمين...) بعملاء يدفعون بعملة **Pi** — العملة الرقمية الأكثر انتشاراً في العالم العربي.

### الميزات الرئيسية:
- 🛡️ **KYC-First**: كل مستخدم موثق عبر Pi Network
- 💰 **مدفوعات آمنة**: نظام Escrow يحجز الأموال حتى استلام العمل
- ⭐ **تقييم 4 أبعاد**: جودة، تواصل، التزام، قيمة مقابل السعر
- ⚖️ **تحكيم ذكي**: نظام نزاعات عادل مع محكمين متخصصين
- 🚀 **نمو فيروسي**: اكسب 5-10 Pi لكل إحالة ناجحة
- 🏗️ **Pi App Studio**: أنشئ متجرك الخاص بخطوات بسيطة

---

## 📊 خارطة الطريق (Roadmap)

| Sprint | الميزة | الحالة |
|--------|--------|--------|
| 1 | الأساس (KYC, Auth) | ✅ منجز |
| 2 | الدفع والضمان (Escrow, Pi SDK) | ✅ منجز |
| 3 | لوحة التحكم (Dashboard) | ✅ منجز |
| 4 | التقييمات (4D Rating) | ✅ منجز |
| 5 | النزاعات (Dispute System) | ✅ منجز |
| 6 | **الإحالات والنمو** | 🔄 **قيد التنفيذ** |
| 7 | Pi App Studio | ⏳ قادم |
| 8 | الإطلاق الرسمي | ⏳ قادم |

---

## 🚀 برنامج الرواد (Pioneer Program)

**محدود لـ 100 رائد فقط**

🎁 **10 Pi مجانية** عند الإطلاق
🏅 **شارة "رائد أول"** ذهبية دائمة
🔓 **وصول مبكر** للميزات الجديدة
💸 **عمولة مخفضة** (3% بدلاً من 7%)

[سجّل كرائد](https://kraiem11.github.io/riwaqpi/pioneers.html)

---

## 🏗️ التقنية

### Backend
```
Node.js 18+ | Express.js | MongoDB | Mongoose
Pi Network SDK v2 | JWT | Helmet | CORS
```

### Frontend
```
HTML5 | CSS3 (Custom) | Vanilla JS
Pi Browser Compatible | Responsive | RTL
```

### DevOps
```
GitHub Actions | Render (Backend) | GitHub Pages (Frontend)
MongoDB Atlas | Environment Variables
```

---

## 📦 التشغيل محلياً

### Backend
```bash
cd backend
cp .env.example .env
# عدّل .env بمتغيراتك

npm install
npm run seed   # ملء مستويات السفراء
npm run dev    # http://localhost:5000
```

### Frontend
```bash
# افتح frontend/index.html مباشرة في المتصفح
# أو استخدم Live Server
```

---

## 🔗 API Endpoints

### Pioneers
```
POST /api/pioneers/register          ← تسجيل رائد
GET  /api/pioneers/stats/public      ← إحصائيات عامة
```

### Referrals
```
POST /api/referrals/generate         ← توليد كود إحالة
POST /api/referrals/track            ← تتبع نقرات
POST /api/referrals/claim            ← ربط إحالة بتسجيل
PUT  /api/referrals/complete/:id     ← إكمال الإحالة
PUT  /api/referrals/pay/:id          ← صرف مكافأة Pi
GET  /api/referrals/stats/:id        ← إحصائيات السفير
```

[توثيق API الكامل](docs/api-docs.md)

---

## 🥉🥈🥇 نظام السفراء

| المستوى | الحد الأدنى | المكافأة | العمولة |
|---------|------------|---------|--------|
| 🥉 Bronze | 5 إحالات | 5 Pi | 0% |
| 🥈 Silver | 25 إحالة | 7 Pi | 1% |
| 🥇 Gold | 100 إحالة | 10 Pi | 2% |

---

## 👥 الفريق

| الدور | الوصف |
|-------|-------|
| المشرف العام | [@kraiem11](https://github.com/kraiem11) — القرارات الاستراتيجية |
| المدير التنفيذي | AI CEO — التنفيذ التقني والتطوير |

---

## 📄 الترخيص

MIT License — انظر [LICENSE](LICENSE)

---

<div align="center">

**مبني بـ ❤️ على Pi Network**

[🐙 GitHub](https://github.com/kraiem11/riwaqpi) · [✈️ Telegram](https://t.me/riwaqpi) · [🐦 Twitter](https://twitter.com/riwaqpi)

</div>
