---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---

---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | OI Notepad |     1.5.4    |

---

{% include videopages/type1/oinotepad.html %}

##### Description

The bug is related to the dangerous permission `android.permission.WRITE_EXTERNAL_STORAGE` and is triggered during saving files, as the corresponding calling context does not check the permission.

Reproduce steps:
1. enter the app and click "create note" at top-right
2. type some texts
3. click "save to sd card" on the top-right option menu
4. select deny on the pop-up window (which requests a storage permission) and the app gets stuck

##### Aper Outputs

```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	org.openintents.notepad.activity.SaveFileActivity.onCreate(android.os.Bundle)void
	 org.openintents.notepad.activity.SaveFileActivity.getFilenameFromNoteTitle(android.net.Uri)android.net.Uri
	  org.openintents.notepad.activity.SaveFileActivity.getSdCardPath()java.io.File
	   android.os.Environment.getExternalStorageDirectory()java.io.File

======

DANGEROUS: android.permission.READ_EXTERNAL_STORAGE
	Is Declared: false
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <org.openintents.notepad.activity.SaveFileActivity: void onRequestPermissionsResult(int,java.lang.String[],int[])>

---
DANGEROUS: android.permission.WRITE_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <org.openintents.notepad.activity.SaveFileActivity: void onRequestPermissionsResult(int,java.lang.String[],int[])>
```
