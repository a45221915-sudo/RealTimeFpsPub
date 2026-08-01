[English](../../README.md) | [Español](../es/README.md)
| [Português](../pt/README.md) | [Bahasa Indonesia](../in/README.md)
| [Русский](../ru/README.md) | [中文 (简体)](../zh-rCN/README.md) | [中文 (繁體)](../zh-rTW/README.md)
| [日本語](../ja-rJP/README.md) | [Tiếng Việt](../vi/README.md)
| [Türkçe](../tr/README.md)
| [हिन्दी](../hi/README.md) | [বাংলা (ভারত)](../bn-rIN/README.md) | [ਪੰਜਾਬੀ (ਭਾਰਤ)](../pa-rIN/README.md) | <u>[తెలుగు](README.md)</u> | [اردو (پاکستان)](../ur-rPK/README.md) | [العربية](../ar/README.md) | [ไทย](../th/README.md)

----------------------

### సంక్షిప్తంగా (TL;DR)

* `adb shell appops set com.tribalfs.realtimefps PROJECT_MEDIA allow` అమలు చేయండి
* ఎలివేటెడ్ అనుమతులు ఉన్న ఆండ్రాయిడ్ టెర్మినల్ యాప్‌ను ఉపయోగిస్తుంటే,  
  `appops set com.tribalfs.realtimefps PROJECT_MEDIA allow` అమలు చేయండి

----------------------

పీసీ (PC) ఉపయోగించి అనుమతి ఇవ్వడం:
----------------------

<details>

### 1. ఫోన్ సెట్టింగ్‌లలో డెవలపర్ మోడ్‌ను ప్రారంభించండి

<details>

* _సెట్టింగ్‌లు_ > _ఫోన్ గురించి_ > _సాఫ్ట్‌వేర్ సమాచారం_ కు వెళ్లి _బిల్డ్ నంబర్_
  పై వరుసగా ఏడు (7) సార్లు నొక్కండి తద్వారా **డెవలపర్ ఆప్షన్స్** ప్రారంభమవుతాయి.

<img src="res/about_phone.jpg" width=320 height=640 alt="ఫోన్ గురించి">

</details>

### 2. USB డీబగ్గింగ్‌ను ప్రారంభించండి

<details>

* _సెట్టింగ్‌లు_ > _డెవలపర్ ఆప్షన్స్_ కు వెళ్లండి (పాత ఆండ్రాయిడ్ వెర్షన్‌లలో ఇది _సెట్టింగ్‌లు_ >
  _సిస్టమ్_ > _డెవలపర్ ఆప్షన్స్_ గా ఉండవచ్చు), క్రిందికి స్క్రోల్ చేసి _USB డీబగ్గింగ్_ ఆప్షన్‌ను
  కనుగొనండి.
  ఆ ఎంపికను ప్రారంభించండి.

<img src="res/usb_debugging.jpg" width=320 height=640 alt="ADB">

#### MIUI వంటి కొన్ని పరికరాల కోసం గమనికలు:

* డెవలపర్ ఆప్షన్స్‌లో _USB డీబగ్గింగ్ (సెక్యూరిటీ సెట్టింగ్‌లు)_ ఉంటే దానిని కూడా ప్రారంభించండి.

* డెవలపర్ ఆప్షన్స్‌లో _పర్మిషన్ మానిటరింగ్‌ను నిలిపివేయి_ ఆప్షన్ ఉంటే దానిని ప్రారంభించండి.  
  అనంతరం పరికరాన్ని రీబూట్ చేయాలి.

</details>

### 3. మీ కంప్యూటర్‌లో ADBని డౌన్‌లోడ్ చేయండి

<details>

* మీ కంప్యూటర్‌లో ADB (platform-tools) డౌన్‌లోడ్ చేయండి:  
  [విండోస్](https://dl.google.com/android/repository/platform-tools-latest-windows.zip) |
  [మాక్](https://dl.google.com/android/repository/platform-tools-latest-darwin.zip) |
  [లినక్స్](https://dl.google.com/android/repository/platform-tools-latest-linux.zip)

* డౌన్‌లోడ్ చేసిన ZIP ఫైల్‌ను ఎక్స్‌ట్రాక్ట్ చేయండి.

</details>

### 4. ఫోల్డర్ లోపలికి వెళ్లండి

విండోస్ ఎక్స్‌ప్లోరర్ లేదా ఫైండర్ (macOS) లో మీరు ఎక్స్‌ట్రాక్ట్ చేసిన `platform-tools` ఫోల్డర్‌లోకి
వెళ్లండి.

### 5. కమాండ్-లైన్ ఇంటర్‌ఫేస్‌ను తెరవడం

<details>

#### విండోస్ కోసం: CMD తెరవండి

* అడ్రస్ బార్‌లో `cmd` టైప్ చేసి Enter నొక్కండి. ఇది విండోస్ కమాండ్ ప్రాంప్ట్‌ను తెరుస్తుంది.

![opening_cmd](../en/res/opening_cmd.png)

#### macOS కోసం:

* డౌన్‌లోడ్ చేసిన జిప్ ఫైల్‌ను తెరవడానికి దానిపై డబుల్ క్లిక్ చేయండి, కాంటెక్స్ట్ మెనూను తెరవడానికి
  `platform-tools` ఫోల్డర్‌పై రైట్ క్లిక్ చేసి, ఆపై _Services_ > _New Terminal at Folder_ పై క్లిక్
  చేయండి.

</details>

### 6. మీ ఫోన్‌ను కంప్యూటర్‌కు కనెక్ట్ చేయడం

<details>

* USB డీబగ్గింగ్ మోడ్‌లో మొదటిసారి కనెక్ట్ చేసినప్పుడు,  
  _Allow USB debugging (USB డీబగ్గింగ్‌కు అనుమతి ఇవ్వండి)_ సందేశం కనిపిస్తుంది.  
  _Allow (అనుమతించండి)_ లేదా _OK (సరే)_ నొక్కండి.

*

_Always allow from this computer (ఈ కంప్యూటర్ నుండి ఎల్లప్పుడూ అనుమతించండి)_ ఎంపిక చేయవచ్చు (దీనిపై
గమనిక ట్యుటోరియల్ చివరలో ఉంది).

<img src="res/usb_debugging_prompt.jpg" width=320 height=640 alt="ADB ప్రాంప్ట్">

* కనెక్షన్‌ను తనిఖీ చేయడానికి క్రింది కమాండ్ అమలు చేయండి. సరిగా కనెక్ట్ అయితే పరికరం ID చూపిస్తుంది.

```bash
adb devices
```

![adb_devices](../en/res/adb_devices.png)

* పరికరం కనెక్ట్ కాకపోతే, వేరే USB పోర్ట్ లేదా డేటా కేబుల్ ఉపయోగించండి.  
  అవసరమైతే USB డ్రైవర్లు ఇన్‌స్టాల్
  చేయండి: https://developer.android.com/studio/run/oem-usb#Drivers  
  తరువాత PC రీబూట్ చేసి 6వ దశను మళ్లీ చేయండి.

</details>

### 7. పిక్సెల్స్‌కు PROJECT_MEDIA అనుమతి ఇవ్వడం

<details>

* విజయవంతంగా కనెక్ట్ అయిన తర్వాత, క్రింది కమాండ్ అమలు చేయండి.  
  సరిగ్గా అమలైతే ఎలాంటి అవుట్‌పుట్ కనిపించదు.

```bash
adb shell appops set com.tribalfs.realtimefps PROJECT_MEDIA allow
```

* `adb.exe: more than one device/emulator...` లోపం వస్తే:

```bash
adb -s [6వ దశలో చూపిన పరికరం ID] shell appops set com.tribalfs.realtimefps PROJECT_MEDIA allow
```

![PROJECT_MEDIA](../en/res/PROJECT_MEDIA.png)

#### MIUI, OnePlus మరియు ఇతర పరికరాల కోసం గమనిక

`java.lang.SecurityException: grantRuntimePermission` వస్తే:

1. _సెట్టింగ్‌లు_ > _డెవలపర్ ఆప్షన్స్_
2. **USB డీబగ్గింగ్ (సెక్యూరిటీ సెట్టింగ్‌లు)** ప్రారంభించండి
3. హెచ్చరికలు వస్తే సూచనలు అనుసరించండి
4. పరికరాన్ని రీబూట్ చేసి 7వ దశ మళ్లీ ప్రయత్నించండి

**అంతే!**

</details>

#### ఇప్పుడు మీరు USB డీబగ్గింగ్‌ను నిలిపివేయవచ్చు

* _సెట్టింగ్‌లు_ > _డెవలపర్ ఆప్షన్స్_ > _USB డీబగ్గింగ్_ → **నిలిపివేయండి**

</details>

----------------------

పీసీ లేకుండా అనుమతి ఇవ్వడం (Shizuku ఉపయోగించి):
----------------------

<details>

### ఆప్షన్ 1: మీరు [Shizuku](https://play.google.com/store/apps/details?id=moe.shizuku.privileged.api)* ఇన్‌స్టాల్ చేయవచ్చు

మరియు అది అందించిన గైడ్‌ను అనుసరించి దానిని సక్రియం చేయండి. తర్వాత Shizuku ఉపయోగించి అనుమతి మంజూరు
చేయడానికి _Real-time FPS_ యాప్‌కు తిరిగి వెళ్లండి.

*ఒకవేళ ప్లే స్టోర్ వెర్షన్ మీ పరికరంలో పనిచేయకపోతే, మీరు దానికి బదులుగా
ఈ [Shizuku fork](https://github.com/thedjchi/Shizuku/releases)ను ఉపయోగించవచ్చు.


</details>

----------------------

### యాప్‌ను పూర్తిగా అన్‌ఇన్‌స్టాల్ చేసి మళ్లీ ఇన్‌స్టాల్ చేయకపోతే, ఈ ప్రక్రియను మళ్లీ చేయాల్సిన అవసరం లేదు.
