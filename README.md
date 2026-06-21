# WebStorm-Activation-Guide-Linux
آموزش گام به گام نصب، کرک و فعال‌سازی WebStorm 2025.3 در لینوکس با استفاده از ja-netfilter. شامل لینک دانلود، رفع مشکلات رایج و دریافت کد فعال‌سازی.

# آموزش کامل نصب و فعال‌سازی WebStorm در لینوکس

## 📥 مرحله ۱: دانلود WebStorm

از یکی از این راه‌ها WebStorm رو دانلود کن:

- **سایت رسمی جت‌برینز:** `https://www.jetbrains.com/webstorm/download/`
- **سایت soft98 (نسخه کرک شده):** `https://soft98.ir`
- **تلگرام:** کانال‌های کرک نرم‌افزار

فایل دانلودی معمولاً به صورت `tar.gz` هست.

---

## 📦 مرحله ۲: خارج کردن از حالت فشرده

```bash
cd ~/Downloads
tar -xzf WebStorm-*.tar.gz
mv WebStorm-* ~/Documents/

## 🛠️ مرحله ۳: دانلود ja-netfilter (ابزار کرک)
ja-netfilter یه ابزار جاوا هست که کرک رو ممکن می‌کنه.

از کجا دانلود کنم؟
سایت اصلی: https://jetbra.in/s

گیت‌هاب: https://github.com/ja-netfilter/ja-netfilter

تلگرام: کانال‌های کرک JetBrains (سرچ کن ja-netfilter jetbrains)

فایل رو دانلود کن و بذار توی ~/Downloads/

📂 مرحله ۴: آماده‌سازی ja-netfilter
bash
cd ~/Downloads
unzip ja-netfilter*.zip -d ja-netfilter
cp -r ja-netfilter ~/Documents/jetbra/

⚙️ مرحله ۵: اجرای اسکریپت نصب
bash
cd ~/Documents/jetbra/scripts
sudo sh install.sh
منتظر پیام Done باش.

📝 مرحله ۶: ویرایش فایل vmoptions
فایل webstorm64.vmoptions توی مسیر WebStorm/bin/ رو باز کن:

bash
nano ~/Documents/WebStorm-*/bin/webstorm64.vmoptions
این سه خط رو به آخر فایل اضافه کن:

text
--add-opens=java.base/jdk.internal.org.objectweb.asm=ALL-UNNAMED
--add-opens=java.base/jdk.internal.org.objectweb.asm.tree=ALL-UNNAMED
-javaagent:/home/username/Documents/jetbra/ja-netfilter.jar=jetbrains
⚠️ توجه: جای username اسم کاربری خودت رو بذار.

با Ctrl+O ذخیره کن و Ctrl+X خارج شو.

🔄 مرحله ۷: ریستارت سیستم
bash
sudo reboot
🚀 مرحله ۸: اجرای WebStorm
bash
cd ~/Documents/WebStorm-*/
./bin/webstorm
🔑 مرحله ۹: دریافت کد فعال‌سازی
۱. توی مرورگر برو به این آدرس:

text
https://jetbra.in/5d84466e31722979266057664941a71893322460
۲. کد فعال‌سازی رو از سایت کپی کن (تمام صفحه رو انتخاب کن و کپی).

۳. توی WebStorm گزینه Activation Code رو انتخاب کن.

۴. کد رو پیست کن و Activate رو بزن.

❌ رفع مشکلات رایج
خطای Key is invalid
مطمئن شو =jetbrains آخر خط javaagent نوشته شده

از سایت کد جدید بگیر، نه کد قدیمی

فایل vmoptions رو دوباره چک کن

خطای Address already in use
bash
pkill -9 -f webstorm
rm -rf ~/.config/JetBrains/WebStorm*/.lock
برنامه اجرا نمیشه
bash
# فایل vmoptions خود WebStorm رو چک کن
cat ~/Documents/WebStorm-*/bin/webstorm64.vmoptions
ℹ️ اطلاعات بیشتر
لایسنس fallback: تاریخ انقضا مهم نیست

آپدیت شدن: بعد از هر آپدیت، vmoptions رو دوباره ویرایش کن

ja-netfilter: ورژن ۲۰۲۵.۳.۰ به بالا کار می‌کنه

🔗 لینک‌های مفید
WebStorm: https://www.jetbrains.com/webstorm/

ja-netfilter: https://github.com/ja-netfilter/ja-netfilter

دریافت کد: https://jetbra.in/s

کانال تلگرام: @jetbrains_crack (در تلگرام سرچ کن)

text

---

**همینو کپی کن و توی یه فایل `README.md` بذار، بعد بزن توی گیت‌هاب!** 🎯
