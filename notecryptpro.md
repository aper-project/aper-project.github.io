---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---
---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | Note Crypt Pro |     1.44    |

---

{% include videopages/type1/notecryptpro.html %}


##### Description
Reproduce crash
1. grant the storage permission for the app
2. create a database in the main activity
3. select a database and enter the SelectDatabaseActivity
4. go to the system setting and revoke the storage permission
5. back to the app and it crashes

##### Aper Outputs
```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	com.notecrypt.ui.SelectDatabaseActivity$2$2.onClick(android.content.DialogInterface,int)void
	 com.notecrypt.ui.SelectDatabaseActivity.a(com.notecrypt.ui.SelectDatabaseActivity,java.lang.String,boolean)void
	  com.notecrypt.ui.SelectDatabaseActivity.a(java.lang.String,boolean)void
	   com.notecrypt.utils.StringMethods.fixPath(java.lang.String)java.lang.String
	    android.os.Environment.getExternalStorageDirectory()java.io.File

======

DANGEROUS: android.permission.READ_EXTERNAL_STORAGE
	Is Declared: false
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <com.notecrypt.ui.SelectDatabaseActivity: void onRequestPermissionsResult(int,java.lang.String[],int[])>

---
DANGEROUS: android.permission.WRITE_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <com.notecrypt.ui.SelectDatabaseActivity: void onRequestPermissionsResult(int,java.lang.String[],int[])>
```

