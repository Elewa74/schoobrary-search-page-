# Schoobrary Search Single Page

واجهة بحث عربية لصفحة مكتبة Schoobrary، مبنية كصفحة واحدة بدون `iframe` ومهيأة للربط لاحقًا مع Backend وDatabase.

## الملفات

- `index.html`: الصفحة الرئيسية الكاملة.
- `assets/logo.png`: أيقونة المتصفح.
- `design-system/assets/logo-horizontal-schoobrary.png`: شعار الهيدر.

## طريقة التشغيل

افتح الملف مباشرة في المتصفح:

```text
index.html
```

أو استخدم أي static server مثل:

```bash
npx serve .
```

## ملاحظات تقنية للمبرمج

- الصفحة تستخدم React من CDN داخل ملف HTML واحد.
- لا يوجد `iframe`.
- كل نتائج البحث تظهر داخل نفس الصفحة.
- تم تقسيم الواجهة داخليًا إلى مكونات:
  - `SearchHero`
  - `SearchFilters`
  - `ResourceTypeBrowse`
  - `SearchResults`
  - `ResultsSidebar`
  - `ResourceCard`
- يوجد كائن `ApiService` داخل `index.html` يحاكي استجابة backend.

## الربط مع Backend

استبدل دالة:

```js
ApiService.search(payload)
```

بطلب API حقيقي، مثال:

```js
const response = await fetch("/api/search", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify(payload)
});

return response.json();
```

صيغة البيانات المتوقعة:

```json
{
  "count": 306,
  "items": [
    {
      "title": "عنوان المورد",
      "type": "نوع المورد",
      "typeSub": "وصف قصير",
      "meta1": "فيديو تعليمي",
      "meta2": "8:45",
      "bg": "#E3F2FD",
      "accent": "#2196F3",
      "badge": "play"
    }
  ],
  "filters": [
    ["الدرس", "الدرس"],
    ["النوع", "النوع"]
  ]
}
```

## الروابط

بعد تفعيل GitHub Pages، تكون صفحة المعاينة عادة بهذا الشكل:

```text
https://elewa74.github.io/schoobrary-search-single-page/
```
