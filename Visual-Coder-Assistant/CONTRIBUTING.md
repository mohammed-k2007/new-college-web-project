# النمط الموحد للفريق

## 1. الفروع
- `main`: مستقر فقط، للتسليم.
- `develop`: التجميع اليومي.
- فرع لكل مهمة: `feature/<الدور>-<الميزة>`
  - أمثلة: `feature/fe-editor`، `feature/be-parser`، `feature/db-crud`
  - الأدوار: `fe` / `be` / `db`

## 2. رسائل Commit
`نوع: وصف قصير`

الأنواع: `feat` `fix` `docs` `test` `chore`

مثال: `feat: add flowchart node highlighting`

## 3. الدمج
- ممنوع الدفع المباشر على `main` و `develop`.
- كل شي عبر Pull Request إلى `develop`، ويوافق عليه عضو ثاني.
- PR صغير (ميزة وحدة).
- قبل فتح PR: `git pull origin develop` وحل التعارض عندك.

## 4. ملكية الملفات
| المسار | المسؤول |
|---|---|
| `frontend/` | العضو 1 |
| `backend/` (عدا `backend/database/`) | العضو 2 |
| `database/` و `backend/database/db.js` | العضو 3 |
| `docs/`، `README.md`، `package.json` | مشترك، التعديل بعد اتفاق وفي PR مستقل |

## 5. العقد المشترك
`docs/` هو مصدر الحقيقة. أي تغيير بالـ API أو بشكل الـ JSON:
1. افتح Issue واتفقوا.
2. PR على `docs/` أول.
3. بعدها الكود.

## 6. الروتين اليومي
```bash
git checkout develop && git pull
git checkout -b feature/fe-xxx
# اشتغل + commits صغيرة
git push -u origin feature/fe-xxx
# افتح PR إلى develop
```
بعد الدمج احذف الفرع.

## 7. Definition of Done للـ PR
- [ ] يشتغل محلياً
- [ ] ما يكسر ملفات الغير
- [ ] فيه اختبار إذا هو منطق (parser / flowchart / CRUD)
- [ ] التوثيق محدّث

## 8. ما ينرفع وما ما ينرفع
- ينرفع: `schema.sql`، `init-db.js`، `seed.js`.
- ما ينرفع: `node_modules/`، `.env`، `database.sqlite`.
