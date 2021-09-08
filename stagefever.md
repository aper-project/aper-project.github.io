---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---

---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | StageFever |     1.2.0    |

---

{% include videopages/type1/stagefever.html %}

##### Description

1. grant the storage permission and go to the File Picker page
2. go to the system setting and revoke the storage permission
3. go back to the app and click pick file button, then the app crashes

##### Aper Outputs

```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	com.fr3ts0n.stagefever.MainActivity.onOptionsItemSelected(android.view.MenuItem)boolean
	 com.fr3ts0n.stagefever.MainActivity.selectFileToLoad()void
	  com.fr3ts0n.stagefever.FileHelper.getPath(android.content.Context)java.lang.String
	   android.os.Environment.getExternalStorageDirectory()java.io.File

======

DANGEROUS: android.permission.READ_EXTERNAL_STORAGE
	Is Declared: true
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
