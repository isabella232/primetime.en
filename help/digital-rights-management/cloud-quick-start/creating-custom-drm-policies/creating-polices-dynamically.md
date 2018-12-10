---
seo-title: Create policies dynamically for Custom Auth/Entitlement
title: Create policies dynamically for Custom Auth/Entitlement
uuid: 49e3e959-96f8-44ef-9140-8fabf1825df8
index: y
internal: n
snippet: y
---

# Create policies dynamically for Custom Auth/Entitlement{#create-policies-dynamically-for-custom-auth-entitlement}

If you are using  Primetime Cloud DRM Custom Authentication/Entitlement and want to dynamically create a new DRM policy for each license request (instead of pulling policies from a pre-generated pool), Adobe recommends that you use the Primetime DRM Java SDK directly. Using the Java SDK directly is faster than the [!DNL AdobePolicyManager.jar] tool, which automatically outputs the policy file to disk, incurring disk I/O overhead.

Sample code using the Java SDK can be found in the [!DNL /Primetime DRM PolicyManager/sampleCode/] directory, named [!DNL CreatePolicy.java] and [!DNL CreatePolicyWithOutputProtection.java]. Javadocs and documentation for the Java SDK can be found at: [http://help.adobe.com/en_US/primetime/drm/#DRM-concept-Adobe_Primetime_DRM_Guides](http://help.adobe.com/en_US/primetime/drm/#DRM-concept-Adobe_Primetime_DRM_Guides)

To build and run the samples, please copy the .java files into the ../libs/ folder and run:

```
javac -cp adobe-flashaccess-sdk.jar:. CreatePolicy.java
java -cp adobe-flashaccess-sdk.jar:. CreatePolicy
```

