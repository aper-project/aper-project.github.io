---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---

---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | MemeTastic |     1.6.7    |

---

{% include videopages/type1/memetastic.html %}

##### Description
The calling context has a permission check, but the returned file path is read/write without check, thus a crash happens when re-entering the app, when the `onResume` is invoked.

Reproduce crash:

1. enter the app from the home screen and allow the permission request
2. choose one meme item and enter the ``create meme activity''
3. go to system setting and revoke the storage permission
4. go back to the app and it crashes

##### Aper Outputs
```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	net.gsantner.memetastic.activity.MemeCreateActivity.onResume()void
	 net.gsantner.memetastic.activity.MemeCreateActivity.initMemeSettings(android.os.Bundle)boolean
	  net.gsantner.memetastic.activity.MemeCreateActivity.extractBitmapFromIntent(android.content.Intent)android.graphics.Bitmap
	   net.gsantner.opoc.util.ShareUtil.extractFileFromIntent(android.content.Intent)java.io.File
	    android.os.Environment.getExternalStorageDirectory()java.io.File

======

DANGEROUS: android.permission.READ_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <net.gsantner.memetastic.activity.MemeCreateActivity: void onRequestPermissionsResult(int,java.lang.String[],int[])>

---
DANGEROUS: android.permission.WRITE_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: in <net.gsantner.memetastic.service.AssetUpdater$LoadAssetsThread: void run()>
	Request Sites: NONE
	Has Handle: in <net.gsantner.memetastic.activity.MemeCreateActivity: void onRequestPermissionsResult(int,java.lang.String[],int[])>
```
