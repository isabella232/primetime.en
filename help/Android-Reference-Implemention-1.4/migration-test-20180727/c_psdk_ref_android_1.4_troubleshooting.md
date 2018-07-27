---
seo-title: Troubleshooting
title: Troubleshooting
uuid: 4f8e519d-016f-4057-a609-411e63ed0237
index: n
internal: n
snippet: y
translate: y
---

# Troubleshooting


* For some older devices that are running API level 10 or older, logcat is unable to open the log device because of a permissions issue. The following exception appears: `java.lang.Exception: logcat returns error: Unable to open log device '/dev/log/main': Permission denied` **Workaround:** 

    1. Open `AndroidManifest.xml` under the `CatalogActivity` project in the workspace.
    1. Add the following permission to the `AndroidManfest.xml` file:     
       ```
       android.permission.READ_LOGS
       ```


