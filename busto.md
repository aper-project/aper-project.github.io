---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---
---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | Libre BusTO |     1.14    |

---

{% include videopages/type1/busto.html %}

##### Description
Reproduce steps:
1. enter the app from the home screen and allow the location permission request
2. go to system setting and revoke the location permission
3. go back to the app and it crashes

##### Aper Outputs

```
API:
	<android.location.LocationManager: void requestLocationUpdates(java.lang.String,long,float,android.location.LocationListener)>
---
PERMISSIONS:
	[android.permission.ACCESS_FINE_LOCATION,android.permission.ACCESS_COARSE_LOCATION]
---
CALLCHAIN:
	it.reyboz.bustorino.fragments.NearbyStopsFragment.onResume()void
	 it.reyboz.bustorino.middleware.AppLocationManager.addLocationRequestFor(it.reyboz.bustorino.middleware.AppLocationManager$LocationRequester)void
	  it.reyboz.bustorino.middleware.AppLocationManager.requestGPSPositionUpdates()void
	   android.location.LocationManager.requestLocationUpdates(java.lang.String,long,float,android.location.LocationListener)void

======

DANGEROUS: android.permission.ACCESS_FINE_LOCATION
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <androidx.fragment.app.Fragment: void onRequestPermissionsResult(int,java.lang.String[],int[])>

---
DANGEROUS: android.permission.ACCESS_COARSE_LOCATION
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <androidx.fragment.app.Fragment: void onRequestPermissionsResult(int,java.lang.String[],int[])>
```
