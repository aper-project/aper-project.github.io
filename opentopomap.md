---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---
---

|      Device Name (left)     | Android Version (left) | Device Name (right) | Android Version (right) |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 | 6.0.1 | Nexus 5X | 7.1.1 | OpenTopoMap Viewer |     1.11.6    |

---

{% include videopages/type2/opentopomap.html %}


##### Description
This crash relates to the API `LocationManager.addNmeaListener()`, whose parameter is `android.location.GpsStatus$NmeaListener` in 23, and `android.location.OnNmeaMessageListener` after 23.
Both versions need `ACCESS_FINE_LOCATION`. In the execution branches, permission is checked at 24 and above, but not checked in 23, thus will crash in 23 if no permission is granted.

<!-- ##### Aper Outputs
```
<path-to-cwd>/analyzerOutput/org.nitri.opentopo/reports/005-android.location.LocationManager.addNmeaListener(android.location.OnNmeaMessageListener)boolean.txt
23: RvProtectedAPI
24: OnlyC
25: OnlyC
26: OnlyC
27: OnlyC
28: OnlyC
``` -->
