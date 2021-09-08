---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---
---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | Minetest |     5.2.0.26    |

---

{% include videopages/type1/minetest.html %}

##### Description
Reproduce steps:
1. enter the app from the home screen and allow the storage permission request
2. go to system setting and revoke the storage permission
3. go back to the app and it crashes

##### Aper Outputs
```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	net.minetest.minetest.MinetestAssetCopy.onCreate(android.os.Bundle)void
	 net.minetest.minetest.MinetestAssetCopy$copyAssetTask.doInBackground(java.lang.Object[])java.lang.Object
	  net.minetest.minetest.MinetestAssetCopy$copyAssetTask.doInBackground(java.lang.String[])java.lang.String
	   android.os.Environment.getExternalStorageDirectory()java.io.File

======

DANGEROUS: android.permission.READ_EXTERNAL_STORAGE
	Is Declared: false
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <android.app.Activity: void onRequestPermissionsResult(int,java.lang.String[],int[])>

---
DANGEROUS: android.permission.WRITE_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <android.app.Activity: void onRequestPermissionsResult(int,java.lang.String[],int[])>
```
