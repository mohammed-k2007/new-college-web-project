# API Contract (مصدر الحقيقة)

أي تغيير هنا يمر عبر Issue "تغيير بالعقد المشترك".

## Projects
| Method | Path | الوصف |
|---|---|---|
| GET | `/api/projects` | كل المشاريع |
| GET | `/api/projects/:id` | مشروع واحد |
| POST | `/api/projects` | إنشاء `{ name, code }` |
| PUT | `/api/projects/:id` | تعديل `{ name?, code? }` |
| DELETE | `/api/projects/:id` | حذف |

كائن المشروع: `{ id, name, code, created_at, updated_at }`

## Execute
`POST /api/execute`

الطلب:
```json
{ "code": "let x = 5; console.log(x);" }
```

الاستجابة الناجحة: انظر `step-format.json` و `flowchart-format.json`.
```json
{ "success": true, "steps": [], "flowchart": { "nodes": [], "edges": [] } }
```

## الأخطاء (موحد)
```json
{ "success": false, "error": { "type": "syntax | unsupported | limit | not_found | validation", "message": "...", "line": 3 } }
```
- `400` كود غير صالح أو تركيب غير مدعوم
- `404` مشروع غير موجود
- `422` تجاوز حدود التنفيذ

## قواعد
- `step.nodeId` يجب أن يطابق `id` موجود في `flowchart.nodes`.
- `variables`: كائن `{ اسم: قيمة }`.
- `output`: مصفوفة نصوص، تراكمية (كل المخرجات لحد هذه الخطوة).
- `status`: `running` | `completed` | `error`.
- `explanation` و `branch` حقول اختيارية.
