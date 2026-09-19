# برنامج خادم KianDesk

[<a href="../README.md">English</a>] | [<a href="README-FA.md">فارسی</a>] | [<a href="README-ZH.md">中文</a>]

استضف خادم KianDesk الخاص بك بنفسك.

## كيفية البناء يدويًا

```bash
cargo build --release
```

سيتم إنشاء ثلاثة ملفات تنفيذية في target/release.

- hbbs - خادم ID/Rendezvous الخاص بـ KianDesk
- hbbr - خادم الترحيل (relay) الخاص بـ KianDesk
- rustdesk-utils - أدوات سطر الأوامر لـ KianDesk

يمكنك العثور على الملفات الثنائية المحدثة في صفحة [Releases](https://github.com/freeb5d/KianDesk-Server/releases).

## الإعدادات

يمكن ضبط `hbbs` و `hbbr` باستخدام أعلام سطر الأوامر، أو متغيرات البيئة، أو ملف `.env`/تكوين. شغّل `hbbs --help` أو `hbbr --help` لعرض الأعلام المتاحة.

الخيارات الأكثر شيوعًا:

| الخيار | العلم | متغير البيئة | ينطبق على | الغرض |
| --- | --- | --- | --- | --- |
| المفتاح | `-k` | `KEY` | hbbs, hbbr | يقوم `hbbs` بتحميل/إنشاء واحد افتراضيًا |
| عنوان الربط | `-b` | `BIND` | hbbs, hbbr | عنوان IP المحلي للاستماع (الافتراضي: كل الواجهات؛ يتطلب 1.1.17+) |
| المنفذ | `-p` | `PORT` | hbbs, hbbr | منفذ الاستماع (hbbs `21116`، hbbr `21117`) |
| خوادم الترحيل | `-r` | `RELAY-SERVERS` | hbbs | للتجاوز عندما يستخدم الترحيل عنوانًا مختلفًا أو منفذًا غير قياسي |
| فرض الترحيل | — | `ALWAYS_USE_RELAY` | hbbs | القيمة `Y` تعطّل الاتصالات المباشرة |
| مستوى السجل | — | `RUST_LOG` | hbbs, hbbr | مثال: `debug` (الافتراضي `info`) |

راجع **[docs/environment-variables.md](environment-variables.md)** للحصول على القائمة الكاملة للمتغيرات، وقواعد أولوية الملف/العلم/متغير البيئة، وضبط قاعدة البيانات وعرض النطاق الترددي للترحيل، ومتغيرات صورة Docker، والأمثلة.

## التثبيت

يرجى اتباع هذا [المستند](https://rustdesk.com/docs/en/self-host/rustdesk-server-oss/).
