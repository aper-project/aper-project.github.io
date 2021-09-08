---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---

---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | Meshenger |     3.0.3    |

---

{% include videopages/type1/meshenger.html %}

##### Description
Reproduce crash

1. grant the storage permission for the app (in system setting)
2. in the app, click "Backup" at the top-right menu and enter the BackupActivity
3. go to system setting and revoke the storage permission
4. tap "BACK" button, then the app crashes

##### Aper Outputs
```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	com.github.isabsent.filepicker.SimpleFilePickerDialog.onStart()void
	 com.github.isabsent.filepicker.SimpleFilePickerDialog.isExternalStorageRoot(java.lang.String)boolean
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
