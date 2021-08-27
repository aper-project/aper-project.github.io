---
layout: page
css: ["index.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---
{% include index.html %}

______

##### 1: Empirical Study
To understand the practices of runtime permissions and exposethe limitations of existing work, we conducted an empirical studyto investigate the following three research questions.

[**Click me see details**](https://aper-project.github.io/benchmarks)

___

##### 2: Type-1 Real Bugs
(Missing Permission Checks): A dangerous API iscalled without a guarding permission check.

[**Click me see details**](https://aper-project.github.io/benchmarks)

---

##### 3: Type-2 Real Bugs
(Incompatible Permission Usages): A new dangerousAPI is called on lower platforms, or the evolution of permissionspecifications is not fully handled.

[**Click me see details**](https://aper-project.github.io/benchmarks)

---

##### 4: Case Study
- * Type-1 misuse bug
- * Safe inter-component ARP usage
- * Type-2 bug in TPL
- * Countermeasure against permission evolution

[**Click me see details**](https://aper-project.github.io/benchmarks)

---

##### 5: Benchmarks
We built a benchmark, ARPfix, that contains buggy ARPusages in real open-source apps, and the corresponding patches.


[**Click me see details**](https://aper-project.github.io/benchmarks)