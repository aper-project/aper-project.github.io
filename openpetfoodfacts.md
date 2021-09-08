---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---
---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | Open Pet Food Facts |     3.2.8    |

---

{% include videopages/type1/openpetfoodfacts.html %}

#### Description
The bug is related to the dangerous permission `android.permission.WRITE_EXTERNAL_STORAGE`. It happens when the app attempts to writing external storage without permission checking (via `checkSelfPermission`).

Reproduce crash

1. grant the storage permission in the system setting
2. scan a product (also need camera permission) and then enter the "add new product" page
3. type any information about the product
4. go to the system setting and revoke the permission
5. in the app, tape twice the "next" botton and reach the "nutrition facts" tab
6. click "add this product" and then the app crashes

#### Aper Outputs

```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	openfoodfacts.github.scrachx.openfood.views.g1.onClick(android.content.DialogInterface,int)void
	 openfoodfacts.github.scrachx.openfood.views.MainActivity.a(java.util.ArrayList,boolean,android.widget.EditText,java.lang.String,android.content.DialogInterface,int)void
	  openfoodfacts.github.scrachx.openfood.utils.r.a(android.content.Context,android.net.Uri)java.lang.String
	   openfoodfacts.github.scrachx.openfood.utils.r.c(android.content.Context,android.net.Uri)java.lang.String
	    android.os.Environment.getExternalStorageDirectory()java.io.File

======

DANGEROUS: android.permission.READ_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <openfoodfacts.github.scrachx.openfood.views.MainActivity: void onRequestPermissionsResult(int,java.lang.String[],int[])>

---
DANGEROUS: android.permission.WRITE_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <openfoodfacts.github.scrachx.openfood.views.MainActivity: void onRequestPermissionsResult(int,java.lang.String[],int[])>
```
