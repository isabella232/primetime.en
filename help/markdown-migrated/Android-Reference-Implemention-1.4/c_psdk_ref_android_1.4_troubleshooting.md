---
seo-title: Troubleshooting
title: Troubleshooting
---

# Troubleshooting

* For some older devices that are running API level 10 or older, logcat is unable to open the log device because of a permissions issue. The following exception appears: `codeph java.lang.Exception: logcat returns error: Unable to open log device '/dev/log/main': Permission denied`
  **Workaround:**
  
    1. Open `filepath AndroidManifest.xml` under the `filepath CatalogActivity` project in the workspace.
    1. Add the following permission to the `filepath AndroidManfest.xml` file:
       ```
       android.permission.READ_LOGS
       ```
       
  
