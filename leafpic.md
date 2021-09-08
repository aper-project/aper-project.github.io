---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---

---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | LeafPic Gallery |     0.6    |

---

{% include videopages/type1/leafpic.html %}

##### Description

Reproduce crash
1. Install LeafPic_v0.6
2. Enter the app from the home screen and allow the storage permission request
3. Go to the system setting and revoke the storage permission
4. Back to the app then the app crashes

##### Aper Outputs

```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	org.horaapps.leafpic.activities.SingleMediaActivity.onCreate(android.os.Bundle)void
	 org.horaapps.leafpic.util.ContentHelper.getMediaPath(android.content.Context,android.net.Uri)java.lang.String
	  android.os.Environment.getExternalStorageDirectory()java.io.File

======

DANGEROUS: android.permission.READ_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <android.support.v4.app.FragmentActivity: void onRequestPermissionsResult(int,java.lang.String[],int[])>

---
DANGEROUS: android.permission.WRITE_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <android.support.v4.app.FragmentActivity: void onRequestPermissionsResult(int,java.lang.String[],int[])>
```
