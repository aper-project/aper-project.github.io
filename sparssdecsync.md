---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---


---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Xiaomi MIX 2S |      10      | SpaRSS DecSync |     1.15.2    |

---

{% include videopages/type1/sparssdecsync.html %}

##### Description

Reproduce crash:
1. install spaRSS DecSync_v1.15.2
2. enter the app from the home screen and change DecSync directory
3. allow the storage permission request
4. go to system setting and revoke the storage permission
5. back to app and click "next" button , then the app crashes
