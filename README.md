# رواق — AI-Powered Arabic Freelance Marketplace

<div align="center">
  <img src="https://img.shields.io/badge/Next.js-14-black?logo=next.js" />
  <img src="https://img.shields.io/badge/TypeScript-5.6-blue?logo=typescript" />
  <img src="https://img.shields.io/badge/Prisma-5.22-green?logo=prisma" />
  <img src="https://img.shields.io/badge/Claude-AI-orange?logo=anthropic" />
  <img src="https://img.shields.io/badge/PostgreSQL-15+-blue?logo=postgresql" />
</div>

---

## البنية الكاملة

```
riwaq/
├── prisma/
│   ├── schema.prisma          # نموذج البيانات الكامل (20+ جدول)
│   └── seed.ts                # بيانات أولية للتطوير
│
├── src/
│   ├── types/index.ts         # TypeScript types & DTOs
│   ├── middleware.ts           # Edge middleware (Auth + CORS + Security)
│   │
│   ├── lib/
│   │   ├── prisma.ts           # Prisma singleton
│   │   ├── auth.ts             # JWT + bcrypt + sessions
│   │   ├── validations.ts      # Zod schemas
│   │   └── api.ts              # Response helpers + utilities
│   │
│   └── app/api/
│       ├── health/             # GET  — liveness probe
│       ├── auth/
│       │   ├── register/       # POST — تسجيل حساب جديد
│       │   ├── login/          # POST — تسجيل دخول
│       │   └── me/             # GET  — بيانات المستخدم الحالي
│       │                       # DELETE — تسجيل خروج
│       ├── users/
│       │   ├── [username]/     # GET  — الملف الشخصي العام
│       │   └── me/
│       │       └── dashboard/  # GET  — بيانات لوحة التحكم (AI-powered)
│       ├── projects/
│       │   ├── route.ts        # GET (browse) + POST (create)
│       │   └── [id]/
│       │       ├── route.ts    # GET + PATCH + DELETE
│       │       └── proposals/  # GET (client) + POST (freelancer bid)
│       ├── proposals/
│       │   └── [id]/           # GET + PATCH (accept/reject/withdraw)
│       ├── contracts/
│       │   └── [id]/
│       │       ├── route.ts    # GET — contract details
│       │       └── milestones/
│       │           └── [milestoneId]/ # PATCH — submit/approve/revise
│       ├── messages/           # GET + POST (contract chat)
│       ├── payments/
│       │   ├── create-escrow/  # POST — fund escrow
│       │   └── release/        # POST — release to freelancer
│       ├── reviews/            # POST — submit review (AI-moderated)
│       ├── disputes/           # GET + POST (AI arbitration)
│       ├── notifications/      # GET + PATCH (mark read)
│       └── ai/
│           ├── generate-project/    # POST — مولّد المشاريع بـ Claude
│           └── match-freelancers/   # POST — AI matching engine
```

---

## البدء السريع

### 1. تثبيت المتطلبات
```bash
npm install
```

### 2. إعداد متغيرات البيئة
```bash
cp .env.example .env.local
# عدّل القيم في .env.local
```

### 3. إعداد قاعدة البيانات
```bash
npm run db:generate   # توليد Prisma Client
npm run db:push       # تطبيق الـ schema
npm run db:seed       # بيانات أولية
```

### 4. تشغيل التطوير
```bash
npm run dev
```

---

## API Reference

### Auth
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | تسجيل حساب جديد |
| POST | `/api/auth/login` | تسجيل دخول |
| GET | `/api/auth/me` | بيانات المستخدم الحالي |
| DELETE | `/api/auth/me` | تسجيل خروج |

### Projects
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/projects` | تصفح المشاريع (public) |
| POST | `/api/projects` | نشر مشروع جديد |
| GET | `/api/projects/:id` | تفاصيل مشروع |
| PATCH | `/api/projects/:id` | تعديل مشروع |
| DELETE | `/api/projects/:id` | حذف مشروع |
| GET | `/api/projects/:id/proposals` | عروض المشروع |
| POST | `/api/projects/:id/proposals` | تقديم عرض |

### AI Endpoints
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/ai/generate-project` | توليد مشروع بـ Claude |
| POST | `/api/ai/match-freelancers` | مطابقة ذكية بالـ AI |

### Payments
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/payments/create-escrow` | إنشاء ضمان دفع |
| POST | `/api/payments/release` | تحرير الدفع بعد الموافقة |

---

## المميزات التقنية

- **JWT Auth** — Access (15min) + Refresh (30d) tokens مع cookie httpOnly
- **Prisma ORM** — Type-safe queries مع PostgreSQL 15+
- **Zod Validation** — كل المدخلات تُتحقق منها قبل المعالجة
- **AI Integration** — Claude Sonnet 4 لتوليد المشاريع، المطابقة، وفض النزاعات
- **Escrow System** — نظام ضمان دفع آمن بالفلوس (1/100 SAR)
- **Edge Middleware** — Auth + CORS + Security headers على Edge Runtime
- **Soft Delete** — لا يُحذف أي سجل نهائياً (deletedAt)
- **Immutable Ledger** — سجل المعاملات للقراءة فقط
