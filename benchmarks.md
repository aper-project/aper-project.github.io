---
layout: page
title: "Benchmarks"
css: ["categories.css"]
---

Link to ARPfix benchmark: [https://example.org](https://example.org)

Link to Aper executable: [https://example.org](https://example.org)

Link to Lint source code: [com/android/tools/lint/checks/PermissionDetector.kt](https://android.googlesource.com/platform/tools/base/+/refs/heads/studio-main/lint/libs/lint-checks/src/main/java/com/android/tools/lint/checks/PermissionDetector.kt#458)

Link to ARPDroid repository: [https://bitbucket.org/malindadoo/arpdroid/src/develop/](https://bitbucket.org/malindadoo/arpdroid/src/develop/)

Link to RevDroid repository: [https://github.com/letitb/revdroid](https://github.com/letitb/revdroid)


We compare the tools by their:

1. True positive ($$TP$$): For a buggy version, detected it as buggy

2. True negative ($$TN$$): For a patched version, no warning is reported

3. False positive ($$FP$$): For a patched version, detected it as buggy

4. False negative ($$FN$$): For a buggy version, no warning is reported

The evaluation metrics are:

$$Precison=\frac{TP}{TP+FP}$$

$$Recall=\frac{TP}{TP+FN}$$

$$F_1 score=\frac{2*Precision*Recall}{Precision+Recall}$$

$$FPR=\frac{FP}{FP+TN}$$


-----

{% include benchmarkstype-1.html %}


-----

{% include benchmarkstype-2.html %}
