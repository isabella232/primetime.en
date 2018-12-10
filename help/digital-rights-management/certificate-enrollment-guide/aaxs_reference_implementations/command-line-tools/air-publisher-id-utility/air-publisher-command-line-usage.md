---
seo-title: Command line usage
title: Command line usage
uuid: 56bf32c9-d5dc-42bb-9e3c-c57be6631bbc
index: y
internal: n
snippet: y
---

# Command line usage{#command-line-usage}

To run the tool, use the following syntax:

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

* * `signaturefile`* specifies the path to the AIR application’s signatures.xml file, located in the applications [!DNL META-INF] directory 

* `signingcert` specifies the certificate used to sign the AIR application

>[!NOTE] {class="- topic/note "}
>
>To determine the publisher ID for an iOS application, use the `-s` option and specify the certificate used to sign the iOS application. ***Adobe Primetime is required to build iOS applications that can play Access-protected content***.

