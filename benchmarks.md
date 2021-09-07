---
layout: page
title: "Benchmark Results"
css: ["categories.css"]
---

Link to ARPfix benchmark: <a href="https://github.com/aper-project/arpfix-benchmark" target="_blank">https://github.com/aper-project/arpfix-benchmark</a>

Link to Aper executable: <a href="/aper-tool">APER</a>

Link to Lint source code: <a href="https://android.googlesource.com/platform/tools/base/+/refs/heads/studio-main/lint/libs/lint-checks/src/main/java/com/android/tools/lint/checks/PermissionDetector.kt#458" target="_blank">com/android/tools/lint/checks/PermissionDetector.kt</a>

Link to ARPDroid repository: <a href="https://bitbucket.org/malindadoo/arpdroid/src/develop/" target="_blank">https://bitbucket.org/malindadoo/arpdroid/src/develop/</a>

Link to RevDroid repository: <a href="https://github.com/letitb/revdroid" target="_blank">https://github.com/letitb/revdroid</a>

---

We compare the tools by their:

1. True positive ($$TP$$): numbers of buggy versions that have warnings

2. True negative ($$TN$$): numbers of patched versions that have no warnings

3. False positive ($$FP$$): numbers of patched versions that have warnings

4. False negative ($$FN$$): numbers of buggy versions that have no warnings

The evaluation metrics:

$$Precision=\frac{TP}{TP+FP}$$

$$Recall=\frac{TP}{TP+FN}$$

$$F_1\ score=\frac{2*Precision*Recall}{Precision+Recall}$$

$$FPR=\frac{FP}{FP+TN}$$

-----

{% include benchmarkstype-1.html %}

-----

{% include benchmarkstype-2.html %}
