# مهندس حياتي — نسخة Bitrise

هذا المستودع مهيأ ليُبنى سحابيًا دون الحاجة إلى وجود مجلد Android مسبقًا.
ملف `bitrise.yml` ينشئ ملفات Android الرسمية باستخدام Flutter ثم يبني APK Release.

## رفع المشروع بصورة صحيحة

يجب أن تكون هذه الملفات في جذر مستودع GitHub مباشرة:

- `pubspec.yaml`
- `bitrise.yml`
- مجلد `lib`
- مجلد `.github`

لا ترفع مجلدًا أبًا يحتوي المشروع داخله، وإلا لن يعثر Bitrise على `pubspec.yaml`.

## Bitrise

1. فك الضغط.
2. ارفع محتويات المجلد إلى مستودع GitHub.
3. اربط المستودع بـBitrise.
4. عند إعداد المشروع اختر Flutter يدويًا إن لم يكتشفه الماسح.
5. اجعل Project location مساويًا للنقطة: `.`
6. شغّل Workflow باسم `build_apk`.
7. بعد نجاح البناء افتح Artifacts ونزّل `app-release.apk`.

## GitHub Actions بديلًا عن Bitrise

افتح تبويب Actions في GitHub، ثم اختر `Build Android APK` واضغط Run workflow.
بعد اكتمال العملية نزّل الملف من قسم Artifacts.
