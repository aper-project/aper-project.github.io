---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---
---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | EtchDroid |     1.5    |

---

{% include videopages/type1/etchdroid.html %}

#### Description
Reproduce crash:
1. in the main activity, click "write apple DMG image" with granting the storage permission

2. select either storage directory (in the menu of "Choose Storage")

3. go to system setting and revoke the storage permission

4. go back to the app and it crashes

#### Aper Outputs
```
API:
	<android.os.Environment: java.io.File getExternalStorageDirectory()>
---
PERMISSIONS:
	[android.permission.READ_EXTERNAL_STORAGE,android.permission.WRITE_EXTERNAL_STORAGE]
---
CALLCHAIN:
	com.codekidlabs.storagechooser.fragments.SecondaryChooserFragment$7.onClick(android.view.View)void
	 com.codekidlabs.storagechooser.fragments.SecondaryChooserFragment.access$1700(com.codekidlabs.storagechooser.fragments.SecondaryChooserFragment)void
	  com.codekidlabs.storagechooser.fragments.SecondaryChooserFragment.performBackAction()void
	   com.codekidlabs.storagechooser.fragments.SecondaryChooserFragment.populateList(java.lang.String)void
	    com.codekidlabs.storagechooser.fragments.SecondaryChooserFragment.setBundlePathOnUpdate()void
	     android.os.Environment.getExternalStorageDirectory()java.io.File

======

DANGEROUS: android.permission.READ_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <android.app.Fragment: void onRequestPermissionsResult(int,java.lang.String[],int[])>

---
DANGEROUS: android.permission.WRITE_EXTERNAL_STORAGE
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <android.app.Fragment: void onRequestPermissionsResult(int,java.lang.String[],int[])>
```