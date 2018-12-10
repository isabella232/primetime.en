---
seo-title: Enable the usage model demo
title: Enable the usage model demo
uuid: 37ee35a1-c32c-402d-8d22-5386d16fc53a
index: y
internal: n
snippet: y
---

# Enable the usage model demo{#enable-the-usage-model-demo}

1. Specify the custom property `RI_UsageModelDemo=true` at packaging time.

   If you are packaging content using the Media Packager command line tool, enter: 

   ```
   java -jar AdobeMediaPackager.jar [
<i>source_file</i>] [
<i>dest_file</i>] -k RI_UsageModelDemo=true
   ```

>[!NOTE] {class="- topic/note "}
>
>If you do not activate the optional demo mode at packaging time, the license server issues a license based on the first valid DRM policy it processes.

