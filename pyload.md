---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---

---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | pyLoad |     0.3.7    |

---

{% include videopages/type1/pyload.html %}

##### Description
The app does not check and request the `WRITE_EXTERNAL_STORAGE` permission when choosing a container file form storage.
There are two unexpected behaviors:

1. choose file page is empty until this permission is granted

2. it will crash if I continue chose Parent Directory

Reproduce steps:

1. Open pyLoad and select Add Links button
2. Click "CHOOSE" for choose container file
3. Go to system setting , grant the storage permission
4. Repeat step 1 and step 2


##### Aper Outputs
```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	org.pyload.android.client.module.FileChooser.onCreate(android.os.Bundle)void
	 org.pyload.android.client.module.FileChooser.<clinit>()void
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
