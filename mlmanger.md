---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---

---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Nexus 5 |      6.0.1      | ML Manager |     1.0.4.1    |

---

{% include videopages/type1/mlmanger.html %}

##### Description

Reproduce steps:
1. enter the app and grant the storage permission
2. go to settings page
3. revoke storage permission in system settings
4. go back to the app
5. click delete APKs item, and the app crashes

##### Aper Outputs

```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	com.javiersantos.mlmanager.activities.SettingsActivity$3.onPreferenceClick(android.preference.Preference)boolean
	 com.javiersantos.mlmanager.utils.UtilsApp.deleteAppFiles()java.lang.Boolean
	  com.javiersantos.mlmanager.utils.UtilsApp.getAppFolder()java.io.File
	   com.javiersantos.mlmanager.utils.AppPreferences.getCustomPath()java.lang.String
	    com.javiersantos.mlmanager.utils.UtilsApp.getDefaultAppFolder()java.io.File
	     android.os.Environment.getExternalStorageDirectory()java.io.File

======

DANGEROUS: android.permission.READ_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: NONE

---
DANGEROUS: android.permission.WRITE_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: NONE
```
