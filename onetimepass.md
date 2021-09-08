---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---


---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | OneTimePass |     1.2.2    |

---

{% include videopages/type1/onetimepass.html %}

##### Description

Reproduce crash:
1. grant the storage permission and go to the export data page
2. go to the system setting and revoke the storage permission
3. go back app, then the app crashes

##### Aper Outputs

```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	com.rustamg.filedialogs.SaveFileDialog.onViewCreated(android.view.View,android.os.Bundle)void
	 com.rustamg.filedialogs.FileDialog.onViewCreated(android.view.View,android.os.Bundle)void
	  com.rustamg.filedialogs.FileDialog.extractArguments(android.os.Bundle)void
	   com.rustamg.filedialogs.FileDialog.<clinit>()void
	    android.os.Environment.getExternalStorageDirectory()java.io.File

======

DANGEROUS: android.permission.READ_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <android.support.v4.app.Fragment: void onRequestPermissionsResult(int,java.lang.String[],int[])>

---
DANGEROUS: android.permission.WRITE_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <android.support.v4.app.Fragment: void onRequestPermissionsResult(int,java.lang.String[],int[])>
```
