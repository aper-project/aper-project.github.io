---
layout: page
css: ["index.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---
{% include index.html %}

##### Empirical Study
To understand the practices of runtime permissions and exposethe limitations of existing work, we conducted an empirical studyto investigate the following three research questions
##### Type-1
(Missing Permission Checks): A dangerous API iscalled without a guarding permission check.
##### Type-2
(Incompatible Permission Usages): A new dangerousAPI is called on lower platforms, or the evolution of permissionspecifications is not fully handled.
##### Case Study
- Type-1 misuse bug
- Safe inter-component ARP usage
- Type-2 bug in TPL
- Countermeasure against permission evolution

##### Benchmarks
We built a benchmark,ARPfix, that contains buggy ARPusages in real open-source apps, and the corresponding patches.Specifically, we collected ARP issues from GitHub [6] that havingboth: issues related to permission check APIs and dangerous APIs,and, commits or pull requests that fix the issues. This resulted in61 projects that include 71 seeding ARP issues.