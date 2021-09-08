---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---

---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Xiaomi MIX 2S |      10      | TopoSuite |     1.2.0    |

---

{% include videopages/type1/toposuite.html %}

##### Description

Reproduce a stuck bug:
1. enter the app and allow the permission request
2. go the "Jobs" page, this page functions are normally
3. go to the system setting and revoke the storage permission
4. back to app and the app gets stuck

##### Aper Outputs

```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	ch.hgdev.toposuite.App.onCreate()void
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
