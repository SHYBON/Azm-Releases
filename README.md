# Azm AI — تحديثات التطبيق / Update feed

مستودع تغذية التحديثات لتطبيق **عزم / Azm AI**. التطبيق يفحص `update.json` تلقائيًا ويثبّت أحدث إصدار بصمت.

## رابط التغذية (يُلصق داخل التطبيق ← الإعدادات ← التحديثات)

```
https://raw.githubusercontent.com/SHYBON/Azm-Releases/main/update.json
```

## صيغة update.json

```json
{
  "version": "1.1.0",
  "installer": "https://github.com/SHYBON/Azm-Releases/releases/download/v1.1.0/Azm_AI_Setup.exe",
  "notes": ["وصف ميزة", "وصف ميزة أخرى"]
}
```

- `version` — رقم الإصدار (نقاط، يُقارن تلقائيًا مع إصدار التطبيق).
- `installer` — رابط تنزيل المثبت (لا يمكن أن يكون رابط OpenAI).
- `notes` — قائمة المميزات الجديدة، تظهر مع وسم `new`.

## إضافة إصدار جديد

1. ابنِ التطبيق (`npx tauri build`) وحدّث `version` في `src-tauri/tauri.conf.json` و`Cargo.toml`.
2. أنشئ Release بوسم `vX.Y.Z` وارفع `Azm_AI_Setup.exe`.
3. حدّث `update.json` هنا بنفس `version` ورابط المثبت الجديد، وادفع إلى `main`.
