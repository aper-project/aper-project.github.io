---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---

---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Pixel 2 (virtual device) |    8.0   | My Location |     1.3.3    |

---

{% include videopages/type1/mylocation.html %}

##### Description

Reproduce steps:
1. Install My Location and enter the app
2. Deny location permission (Deny My Position to access this device's location)
3. Deny location permission & don't ask again My location access location
4. Click "Get Fix" to start GetFixService, and the app crashes
