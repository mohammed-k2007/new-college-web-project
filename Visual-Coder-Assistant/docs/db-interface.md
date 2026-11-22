# Database Interface (`backend/database/db.js`)

العضو 3 ينفذ، والعضو 2 يستدعي. كل الدوال ترجع Promise أو قيمة مباشرة (يتفقون على واحد منهما).

| الدالة | الإرجاع |
|---|---|
| `createProject({ name, code })` | المشروع المنشأ |
| `getAllProjects()` | مصفوفة مشاريع |
| `getProjectById(id)` | مشروع أو `null` |
| `updateProject(id, { name?, code? })` | المشروع بعد التعديل أو `null` |
| `deleteProject(id)` | `true` إذا انحذف، `false` إذا غير موجود |

القواعد:
- استعلامات Parameterized فقط.
- `name` و `code` مطلوبين وغير فارغين، وإلا يرمي خطأ validation.
- `updated_at` يتحدث عند كل تعديل.
- الـ DB لا يعرف شي عن الواجهة.
