---
layout: page
title: "Benchmark Results"
css: ["categories.css"]
---

Link to ARPfix benchmark: <a href="https://www.example.com" target="_blank">www.example.com</a>

<!-- Link to Aper executable: <a href="https://www.example.com" target="_blank">www.example.com</a> -->

Link to Lint source code: <a href="https://android.googlesource.com/platform/tools/base/+/refs/heads/studio-main/lint/libs/lint-checks/src/main/java/com/android/tools/lint/checks/PermissionDetector.kt#458" target="_blank">com/android/tools/lint/checks/PermissionDetector.kt</a>

Link to ARPDroid repository: <a href="https://bitbucket.org/malindadoo/arpdroid/src/develop/" target="_blank">https://bitbucket.org/malindadoo/arpdroid/src/develop/</a>

Link to RevDroid repository: <a href="https://github.com/letitb/revdroid" target="_blank">https://github.com/letitb/revdroid</a>

We compare the tools by their:

1. True positive ($$TP$$): For a buggy version, detected it as buggy

2. True negative ($$TN$$): For a patched version, no warning is reported

3. False positive ($$FP$$): For a patched version, detected it as buggy

4. False negative ($$FN$$): For a buggy version, no warning is reported

The evaluation metrics are:

$$Precision=\frac{TP}{TP+FP}$$

$$Recall=\frac{TP}{TP+FN}$$

$$F_1 score=\frac{2*Precision*Recall}{Precision+Recall}$$

$$FPR=\frac{FP}{FP+TN}$$

-----

{% include benchmarkstype-1.html %}

-----

{% include benchmarkstype-2.html %}
