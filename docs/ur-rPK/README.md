[English](../../README.md) | [Español](../es/README.md)
| [Português](../pt/README.md) | [Bahasa Indonesia](../in/README.md)
| [Русский](../ru/README.md) | [中文 (简体)](../zh-rCN/README.md) | [中文 (繁體)](../zh-rTW/README.md)
| [日本語](../ja-rJP/README.md) | [Tiếng Việt](../vi/README.md)
| [Türkçe](../tr/README.md)
| [हिन्दी](../hi/README.md) | [বাংলা (ভারত)](../bn-rIN/README.md) | [ਪੰਜਾਬੀ (ਭਾਰਤ)](../pa-rIN/README.md) | [తెలుగు](../te-rIN/README.md) | <u>[اردو (پاکستان)](README.md)</u> | [العربية](../ar/README.md) | [ไทย](../th/README.md)

----------------------

### مختصر خلاصہ (TL;DR)

* یہ کمانڈ چلائیں:  
  `adb shell appops set com.tribalfs.realtimefps PROJECT_MEDIA allow`
* اگر آپ کسی اینڈرائیڈ ٹرمینل ایپ کو اضافی اجازت (Elevated Permission) کے ساتھ استعمال کر رہے ہیں
  تو:  
  `pm grant com.tribalfs.realtimefps android.permission.PROJECT_MEDIA`

----------------------

پی سی (PC) کے ذریعے اجازت دینے کا طریقہ:
----------------------

<details>

### 1. فون کی سیٹنگز میں ڈیولپر آپشنز فعال کریں

<details>

* _سیٹنگز_ > _فون کے بارے میں_ > _سافٹ ویئر کی معلومات_ پر جائیں اور  
  _بلڈ نمبر_ پر لگاتار سات (7) بار ٹیپ کریں تاکہ **ڈیولپر آپشنز** فعال ہو جائیں۔

  <img src="res/about_phone.jpg" width=320 height=640 alt="about phone">

</details>

---

### 2. USB ڈی بگنگ فعال کریں

<details>

* _سیٹنگز_ > _ڈیولپر آپشنز_ پر جائیں  
  (پرانے اینڈرائیڈ ورژنز میں یہ _سیٹنگز_ > _سسٹم_ > _ڈیولپر آپشنز_ ہو سکتا ہے)،  
  نیچے اسکرول کریں اور _USB ڈی بگنگ_ کا آپشن تلاش کریں۔

  <img src="res/usb_debugging.jpg" width=320 height=600 alt="adb">

#### MIUI جیسے کچھ ڈیوائسز کے لیے نوٹس:

* اگر ڈیولپر آپشنز میں _سیکیورٹی سیٹنگز کے لیے USB ڈی بگنگ_ موجود ہو تو اسے بھی آن کریں۔

* اگر ڈیولپر آپشنز میں _پرمیژن مانیٹرنگ غیر فعال کریں_ کا آپشن موجود ہو تو اسے بھی آن کریں۔  
  اس کے بعد ڈیوائس کو ری بوٹ کرنا ضروری ہے۔

</details>

---

### 3. اپنے کمپیوٹر پر ADB ڈاؤن لوڈ کریں

<details>

* ADB (platform-tools) اپنے کمپیوٹر پر ڈاؤن لوڈ کریں:  
  [ونڈوز](https://dl.google.com/android/repository/platform-tools-latest-windows.zip)|
  [میک](https://dl.google.com/android/repository/platform-tools-latest-darwin.zip)|
  [لینکس](https://dl.google.com/android/repository/platform-tools-latest-linux.zip)

* ڈاؤن لوڈ کی گئی ZIP فائل کو ایکسٹریکٹ کریں۔

</details>

---

### 4. `platform-tools` فولڈر کے اندر جائیں

Windows Explorer یا Finder (macOS) میں اس `platform-tools` فولڈر کو کھولیں  
جو آپ نے ایکسٹریکٹ کیا ہے۔

---

### 5. کمانڈ لائن انٹرفیس کھولیں

<details>

#### ونڈوز کے لیے: CMD کھولیں

* ایڈریس بار میں `cmd` لکھیں اور Enter دبائیں۔  
  اس سے Windows Command Prompt کھل جائے گا۔

![opening_cmd](docs/en/res/opening_cmd.png)

#### macOS کے لیے:

* ڈاؤن لوڈ کردہ زپ فائل کو کھولنے کے لیے ڈبل کلک کریں، سیاق و سباق کا مینو کھولنے کے لیے
  `platform-tools` فولڈر پر دائیں کلک کریں اور پھر _Services_ > _New Terminal at Folder_ پر کلک
  کریں۔

</details>

---

### 6. فون کو کمپیوٹر سے منسلک کریں

<details>

* اگر USB ڈی بگنگ موڈ میں پہلی بار فون کنیکٹ کیا جا رہا ہو تو  
  فون پر _USB ڈی بگنگ کی اجازت دیں_ کا پیغام آئے گا۔  
  _اجازت دیں_ یا _اوکے_ پر ٹیپ کریں۔

* آپ _اس کمپیوٹر سے ہمیشہ اجازت دیں_ کا آپشن بھی منتخب کر سکتے ہیں  
  (USB ڈی بگنگ فعال رکھنے سے متعلق نوٹ نیچے دیا گیا ہے)۔

  <img src="res/usb_debugging_prompt.jpg" width=320 height=640 alt="adb prompt">

* کنکشن چیک کرنے کے لیے یہ کمانڈ چلائیں:

```adb devices```

اگر کنکشن درست ہے تو آپ کی ڈیوائس آئی ڈی ظاہر ہو جائے گی۔

![adb devices](docs/en/res/adb_devices.png)

* اگر ڈیوائس کنیکٹ نہ ہو تو:
    - کسی اور USB پورٹ سے کنیکٹ کریں
    - یا کوئی دوسری USB ڈیٹا کیبل استعمال کریں

  اگر پھر بھی کنیکٹ نہ ہو تو ممکن ہے USB ڈرائیور انسٹال نہ ہوں۔  
  OEM USB ڈرائیورز ڈاؤن لوڈ کرنے کے لیے  
  [یہاں دیکھیں](https://developer.android.com/studio/run/oem-usb#Drivers)۔  
  انسٹال کرنے کے بعد PC ری بوٹ کریں اور مرحلہ 6 دوبارہ کریں۔

</details>

---

### 7. Real-time FPS Monitor کو PROJECT_MEDIA کی اجازت دینا

<details>

* کامیابی سے کنیکٹ ہونے کے بعد یہ کمانڈ چلائیں:

```adb shell appops set com.tribalfs.realtimefps PROJECT_MEDIA allow```

اگر کمانڈ درست چلی تو کوئی آؤٹ پٹ ظاہر نہیں ہو گا۔

* اگر یہ پیغام آئے:  
  `adb.exe: more than one device/emulator...`  
  تو یہ کمانڈ استعمال کریں:

```adb -s [مرحلہ 6 میں دکھائی گئی ڈیوائس آئی ڈی] shell appops set com.tribalfs.realtimefps PROJECT_MEDIA allow```

![write secure settings](docs/en/res/PROJECT_MEDIA.png)

#### MIUI، OnePlus اور کچھ دیگر ڈیوائسز کے لیے نوٹ

اگر `java.lang.SecurityException: grantRuntimePermission` ایرر آئے تو:

1. _سیٹنگز_ > _ڈیولپر آپشنز_ پر جائیں
2. **USB ڈی بگنگ (سیکیورٹی سیٹنگز)** فعال کریں
3. اگر کوئی تنبیہی پیغام آئے تو اس کی ہدایات پر عمل کریں
4. ڈیوائس ری بوٹ کریں اور مرحلہ 7 دوبارہ آزمائیں

**بس اتنا ہی!**

</details>

### اب آپ USB ڈی بگنگ غیر فعال کر سکتے ہیں

* _سیٹنگز_ > _ڈیولپر آپشنز_ میں جا کر  
  _USB ڈی بگنگ_ کو **غیر فعال** کر دیں۔

</details>

----------------------

پی سی کے بغیر اجازت دینے کا طریقہ (Shizuku کے ذریعے):
----------------------

<details>

### آپشن 1: Shizuku انسٹال کریں

[Shizuku](https://play.google.com/store/apps/details?id=moe.shizuku.privileged.api)* انسٹال کریں  
اور اس کی دی گئی ہدایات کے مطابق اسے فعال کریں۔  
بعد میں Real-time FPS Monitor ایپ میں جا کر ریزولوشن لاگو کریں، اجازت خود بخود مل جائے گی۔

*اگر Play Store ورژن آپ کے آلے پر کام نہیں کرتا ہے، تو آپ اس کے بجائے
یہ [Shizuku fork](https://github.com/thedjchi/Shizuku/releases) استعمال کر سکتے ہیں۔

---


</details>

----------------------

### جب تک آپ ایپ کو مکمل طور پر اَن انسٹال کر کے دوبارہ انسٹال نہ کریں،

### اس عمل کو دہرانے کی ضرورت نہیں ہے۔
