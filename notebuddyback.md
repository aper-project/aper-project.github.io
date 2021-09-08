---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---

---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| NoteBuddy |      10      | NoteBuddy |     1.3.2    |

---

{% include videopages/type1/notebuddyback.html %}

##### Description

The app crashes when the storage permission is revoked but still performing file operations.

##### Aper Outputs

```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	nl.yoerinijs.nb.activities.NotesActivity$7.onClick(android.content.DialogInterface,int)void
	 nl.yoerinijs.nb.b.a.a.a(java.lang.String,java.lang.String,android.content.Context,boolean)void
	  nl.yoerinijs.nb.b.a.a$a.doInBackground(java.lang.Object[])java.lang.Object
	   nl.yoerinijs.nb.b.a.a$a.a(java.lang.Void[])java.lang.Boolean
	    nl.yoerinijs.nb.b.a.c.b(android.content.Context)java.io.File
	     nl.yoerinijs.nb.b.a.c.b()java.lang.String
	      android.os.Environment.getExternalStorageDirectory()java.io.File

======

DANGEROUS: android.permission.READ_EXTERNAL_STORAGE
	Is Declared: false
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
