---
seo-title: Troubleshooting
title: Troubleshooting
uuid: b7a41ea7-86c5-442c-b751-86a9055c5e35
index: y
internal: n
snippet: y
---

# Troubleshooting{#troubleshooting}

* For some older devices that are running API level 10 or older, logcat is unable to open the log device because of a permissions issue. The following exception appears: `java.lang.Exception: logcat returns error: Unable to open log device '/dev/log/main': Permission denied` **Workaround:**

    1. Open [!DNL AndroidManifest.xml] under the [!DNL CatalogActivity] project in the workspace. 
    
    1. Add the following permission to the [!DNL AndroidManfest.xml] file:     
    
       ```    
       android.permission.READ_LOGS
       ```

