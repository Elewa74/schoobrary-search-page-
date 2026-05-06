# Schoobrary Platform

واجهة بحث عربية جاهزة للتسليم للمبرمج.

## Structure

- `index.html`: الصفحة الرئيسية (سكشن البحث فقط).
- `topic-material.html`: صفحة نتائج بحث بالموضوع.
- `curriculum.html`: صفحة نتائج بحث بالمنهج.
- `assets/logo.png`: favicon.
- `design-system/assets/logo-horizontal-schoobrary.png`: logo.

## Behavior

1. الصفحة الرئيسية تحتوي فقط على سكشن البحث.
2. تم حذف سيكشن `تصفح الموارد حسب النوع`.
3. عند الضغط على `بحث` داخل `بحث بالموضوع` يتم الانتقال إلى `topic-material.html`.
4. عند الضغط على `بحث` داخل `بحث بالمنهج` يتم الانتقال إلى `curriculum.html`.

## Run

افتح `index.html` مباشرة في المتصفح أو شغّل static server:

```bash
npx serve .
```
