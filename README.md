<div align="center">
<img width="1200" height="475" alt="GHBanner" src="https://github.com/user-attachments/assets/0aa67016-6eaf-458a-adb2-6e31a0763ed6" />
</div>

# حسابات مستر إسلام

هذا المشروع هو تطبيق ويب لإدارة الحسابات تم إنشاؤه باستخدام React و Vite.

View your app in AI Studio: https://ai.studio/apps/drive/1kySRQdYZZWokL76ZHbyAM-XkV2Bjxw36

## متطلبات النظام

- Node.js (الإصدار 18 أو أحدث)
- npm (مدير حزم Node.js)

## تشغيل المشروع محلياً

1. قم بتثبيت التبعيات:
   ```bash
   npm install
   ```

2. قم بإنشاء ملف `.env.local` في المجلد الرئيسي للمشروع وأضف مفتاح API الخاص بك:
   ```
   GEMINI_API_KEY=<مفتاح-API-الخاص-بك>
   ```

3. قم بتشغيل المشروع محلياً:
   ```bash
   npm run dev
   ```

4. افتح المتصفح على العنوان: [http://localhost:3000](http://localhost:3000)

## بناء المشروع للإنتاج

لبناء المشروع للإنتاج، قم بتنفيذ الأمر التالي:

```bash
npm run build
```

سيتم إنشاء ملفات البناء في مجلد `dist`.

## رفع المشروع على GitHub Pages

1. قم بإنشاء مستودع جديد على GitHub.

2. قم بربط المستودع المحلي بمستودع GitHub:

```bash
git remote add origin <رابط-المستودع-الخاص-بك>
```

3. قم بإضافة الملفات وعمل commit ثم رفعها إلى GitHub:

```bash
git add .
git commit -m "النسخة الأولى من المشروع"
git push -u origin main
```

4. قم بتثبيت حزمة gh-pages:

```bash
npm install --save-dev gh-pages
```

5. أضف السطور التالية إلى ملف `package.json`:

```json
"homepage": "https://<اسم-المستخدم-الخاص-بك>.github.io/<اسم-المستودع>/",
"scripts": {
  // ... السطور الموجودة
  "predeploy": "npm run build",
  "deploy": "gh-pages -d dist"
}
```

6. قم بتعديل ملف `vite.config.ts` لإضافة base path:

```typescript
export default defineConfig(({ mode }) => {
    const env = loadEnv(mode, '.', '');
    return {
      base: '/<اسم-المستودع>/',  // أضف هذا السطر
      server: {
        port: 3000,
        host: '0.0.0.0',
      },
      // ... باقي الإعدادات
    };
});
```

7. قم بنشر المشروع على GitHub Pages:

```bash
npm run deploy
```

8. انتقل إلى إعدادات المستودع على GitHub، ثم إلى قسم "Pages" وتأكد من أن المصدر هو فرع "gh-pages".

9. يمكنك الآن الوصول إلى المشروع على الرابط: `https://<اسم-المستخدم-الخاص-بك>.github.io/<اسم-المستودع>/`

## ملاحظات هامة

- تأكد من عدم رفع ملف `.env.local` إلى GitHub لأنه يحتوي على مفتاح API الخاص بك.
- إذا واجهت مشكلة في الشاشة البيضاء بعد النشر، تأكد من أن جميع المسارات في المشروع تستخدم المسار النسبي الصحيح مع base path.
