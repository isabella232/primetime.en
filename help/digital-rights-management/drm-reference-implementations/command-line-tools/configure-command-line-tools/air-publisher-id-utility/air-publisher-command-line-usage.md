---
description: null
seo-description: null
seo-title: AIR Publisher ID utility command-line usage
title: AIR Publisher ID utility command-line usage
uuid: 2797bb91-c57c-4855-98d5-f251a8df8db0
index: y
internal: n
snippet: y
---

# AIR Publisher ID utility command-line usage{#air-publisher-id-utility-command-line-usage}

```
java -jar AdobePublisherIDUtility.jar 
<i class="+ topic ph hi-d="" i "="">
 <i class="+ topic ph hi-d="" i "="">
  signaturefile 
  java -jar AdobePublisherIDUtility.jar -s 
  <i class="+ topic ph hi-d="" i "="">
    signingcert
  </i class="+ topic>
 </i class="+ topic>
</i class="+ topic>
```

* * `signaturefile`* specifies a path to the AIR application’s [!DNL signatures.xml] file, located in the applications [!DNL META-INF] directory 

* `signingcert` specifies the certificate that is used to sign an AIR application

>[!NOTE]
>
>To determine the publisher ID for an Android application, you need to use the `-s` option to specify the certificate used to sign the Android application package (APK). Primetime DRM is required to build Android applications that can play Primetime DRM-protected content.

