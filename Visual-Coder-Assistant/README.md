# Visual Coder Assistant

تطبيق تعليمي يعرض تنفيذ كود JavaScript خطوة بخطوة، مع متغيرات ومخرجات ومخطط خوارزمي (Flowchart) متزامن.

## التقنيات
Frontend: HTML/CSS/Vanilla JS · Backend: Node.js + Express · DB: SQLite · Parser: Acorn

## الهيكل
```
frontend/   واجهة المستخدم (العضو 1)
backend/    السيرفر والتحليل والتنفيذ (العضو 2)
database/   schema.sql + سكربتات القاعدة (العضو 3)
docs/       العقود المشتركة (API + JSON)
```

## التشغيل
```bash
npm install
npm run db:init     # ينشئ database/database.sqlite من schema.sql
npm start           # السيرفر على http://localhost:3000
```

## الفريق
| العضو | الدور | المجلد |
|---|---|---|
| 1 | Frontend | `frontend/` |
| 2 | Backend | `backend/` (عدا `backend/database/`) |
| 3 | Database | `database/` و `backend/database/db.js` |

قبل أي شغل اقرأ [CONTRIBUTING.md](CONTRIBUTING.md) و [docs/API_CONTRACT.md](docs/API_CONTRACT.md).
