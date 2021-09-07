---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---
---

|      Device Name (left)     | Android Version (left) | Device Name (middle) | Android Version (middle) | Device Name (right) | Android Version (right) |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Pixel XL | 8.1.0 | Pixel 2 | 9 | Pixel 3 | 10 | P2P Chat Beta | 2.0 |

---

{% include videopages/type2/p2pchat.html %}

##### Description
This inconsistent behavior relates to the API `WifiP2pManager.createGroup()`, which needs ACCESS_FINE_LOCATION permission since API 29.
In the app P2PChat, this permission is not declared, checked or requested, thus all related functionalities cannot be used, such as create P2P group.
That's why the inconsistency happens in the three devices, with API levels 27-29.
