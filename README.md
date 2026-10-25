# 🎮 Android SDK برای Unity — ویندوز (API 34)

پکیج کامل و آمادهٔ **Android SDK + NDK + OpenJDK** برای بیلد گرفتن پروژه‌های Unity روی ویندوز،
تنظیم‌شده برای **Minimum API 24 (اندروید ۷)** و **Target API 34 (اندروید ۱۴)**.

> 📥 **دانلود:** به صفحهٔ [Releases](https://github.com/Mojtabasamiee/android-sdk-unity/releases) بروید و هر سه فایل را دانلود کنید.

---

## 📦 محتویات پکیج

| فایل | حجم | توضیح |
|------|-----|-------|
| `android-sdk-unity-api34-windows.zip` | ~۲۸۵ MB | هستهٔ SDK: پلتفرم اندروید ۱۴ (API 34)، Build-Tools 34.0.0، Platform-Tools (adb)، Cmdline-Tools و لایسنس‌های قبول‌شده |
| `android-ndk-r23b-windows.zip` | ~۷۸۹ MB | نسخهٔ رسمی NDK r23b — دقیقاً همان نسخه‌ای که Unity 2022 LTS نیاز دارد (برای بیلد IL2CPP) |
| `openjdk-17-windows.zip` | ~۱۹۱ MB | OpenJDK 17 (Temurin) — نسخهٔ سازگار با Unity 2022 LTS |

## 🛠 راهنمای نصب گام‌به‌گام

### ۱) دانلود و اکسترکت
هر سه فایل را دانلود و اکسترکت کنید؛ مثلاً در مسیر زیر:

```
C:\Android\
├── android-sdk-unity\        ← از فایل اول
├── android-ndk-r23b\         ← از فایل دوم
└── jdk-17.0.x+x\             ← از فایل سوم (اسم پوشه بسته به نسخه فرق می‌کند)
```

⚠️ مهم: مسیرها را **کوتاه و بدون فاصله و بدون حروف فارسی** انتخاب کنید (مثل `C:\Android\`). از مسیرهایی مثل Desktop که داخلشان OneDrive است پرهیز کنید.

### ۲) معرفی مسیرها به Unity
در یونیتی به مسیر زیر بروید:

**Edit → Preferences → External Tools**

- تیک **Android SDK Tools Installed with Unity** را بردارید ← مسیر `C:\Android\android-sdk-unity` را بدهید
- تیک **Android NDK Installed with Unity** را بردارید ← مسیر پوشهٔ خود NDK یعنی `C:\Android\android-ndk-r23b` را بدهید
- تیک **Android JDK Installed with Unity** را بردارید ← مسیر پوشهٔ JDK (پوشه‌ای که داخلش `bin` هست) را بدهید
- **Gradle** را دست نزنید — Gradle همراه خود Unity نصب است و باید همین‌طور بماند ✅

### ۳) تنظیم نسخهٔ اندروید در پروژه
**File → Build Settings → Android → Player Settings → Other Settings → Identification**

- **Minimum API Level** → `Android 7.0 'Nougat' (API level 24)`
- **Target API Level** → `API 34` (یا `Automatic (highest installed)`)

### ۴) بیلد بگیرید
از منوی **Build Settings** دکمهٔ **Build** را بزنید. اولین بیلد کمی طول می‌کشد (Gradle باید کش شود) — این طبیعی است.

---

## ❓ سؤالات متداول

**Q: چرا NDK لازم است؟**
اگر Scripting Backend روی **IL2CPP** باشد (برای انتشار در گوگل‌پلی تقریباً اجباری است) حتماً به NDK نیاز دارید. اگر فقط Mono استفاده می‌کنید، NDK ضروری نیست ولی داشتنش ضرری ندارد.

**Q: چرا نسخهٔ NDK باید r23b باشد؟**
Unity 2022 LTS دقیقاً با NDK r23b تست و سازگار است. نسخه‌های خیلی جدیدتر (مثل r27) ممکن است در لینک‌کردن خطا بدهند.

**Q: خطای licenses گرفتم؟**
پوشهٔ `licenses` داخل SDK از قبل آماده شده، ولی اگر باز خطا گرفتید در CommandLine باز کنید: `sdkmanager --licenses` (داخل `cmdline-tools\latest\bin`).

**Q: Unity نسخهٔ Target API 34 را در لیست نشان نمی‌دهد؟**
نسخهٔ Unity شما قدیمی است؛ به آخرین نسخهٔ 2022.3 LTS آپدیت کنید (از 2022.3.12f1 به بعد API 34 پشتیبانی می‌شود) یا گزینهٔ `Automatic (highest installed)` را انتخاب کنید.

---

## 📝 مشخصات فنی

| کامپوننت | نسخه |
|----------|------|
| Android SDK Platform | API 34 (اندروید ۱۴) — Revision 1 (ext12) |
| Android SDK Build-Tools | 34.0.0 |
| Android SDK Platform-Tools | آخرین نسخه (adb، fastboot) |
| Android SDK Command-line Tools | آخرین نسخه (sdkmanager) |
| Android NDK | r23b (23.1.7779620) |
| OpenJDK | 17 (Temurin) |
| Minimum API | 24 (اندروید ۷ نوقا) |
| Target API | 34 (اندروید ۱۴) |

لایسنس‌های SDK از قبل accept شده‌اند تا هنگام بیلد خطای لایسنس نگیرید.

---

ساخته‌شده با ❤️ برای جامعهٔ گیم‌سازی ایران — [Mojtabasamiee](https://github.com/Mojtabasamiee)
