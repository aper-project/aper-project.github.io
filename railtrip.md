---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---

---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Xiaomi MIX 2S |      10      | RailTrip |     1.4.1    |

---

{% include videopages/type1/railtrip.html %}

##### Description

Reproduce crash:
1. Enter the app from the home screen and allow the permission request
2. Go to the system setting and revoke the location permission
3. Back to the app then the app gets stuck, then the app crashes

##### Aper Outputs

```
API:
	<android.location.LocationManager: void requestLocationUpdates(java.lang.String,long,float,android.location.LocationListener)>
---
PERMISSIONS:
	[android.permission.ACCESS_FINE_LOCATION,android.permission.ACCESS_COARSE_LOCATION]
---
CALLCHAIN:
	fr.nocle.passegares.LocationService.onStartCommand(android.content.Intent,int,int)int
	 android.location.LocationManager.requestLocationUpdates(java.lang.String,long,float,android.location.LocationListener)void

======

DANGEROUS: android.permission.ACCESS_FINE_LOCATION
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: NONE

---
DANGEROUS: android.permission.ACCESS_COARSE_LOCATION
	Is Declared: true
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: NONE
```
