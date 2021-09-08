---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---

---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | Minetest Mods |     1.9.1    |

---

{% include videopages/type1/minetestmods.html %}

##### Description

This crash can be reproduce by simply revoke the permission in the main page, once we've granted it.
This app has permission check in another activity:
```
com.rubenwardy.minetestmodmanager.views.SplashActivity.onCreate(android.os.Bundle)void
  com.rubenwardy.minetestmodmanager.views.SplashActivity.checkPermission()void
    android.support.v4.content.ContextCompat.checkSelfPermission(android.content.Context,java.lang.String)int
```
But it cannot protect this calling context.

##### Aper Outputs

```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	com.rubenwardy.minetestmodmanager.views.WorldConfigActivity.onCreate(android.os.Bundle)void
	 android.os.Environment.getExternalStorageDirectory()java.io.File

======

DANGEROUS: android.permission.READ_EXTERNAL_STORAGE
	Is Declared: false
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
