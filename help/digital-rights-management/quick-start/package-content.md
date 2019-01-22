---
seo-title: Package encrypted content
title: Package encrypted content
uuid: 1e271167-107d-41df-8a7c-3075cb3acc0c
index: y
internal: n
snippet: y
---

# Package encrypted content{#package-encrypted-content}

1. Copy the [!DNL <Primetime DRM DVD>\Reference Implementation\Command Line Tools\] directory to your local filesystem.
1. In your local [!DNL Command Line Tools\] folder, update the [!DNL flashaccesstools.properties] file to work with your server.

       You must modify at least the following properties:

    * `encrypt.keys.asymmetric.certfile=[license-server-certificate.cer]`: The path to your License Server Certificate (it usually ends with [!DNL .cer], [!DNL .der] or [!DNL .pem]). 
    
    * `encrypt.license.serverurl=[license-server-url]`: Your license server URL, e.g.: [!DNL https://<License Server Hostname>:8080/flashaccessserver/sampletenant]. 
    
    * `encrypt.license.servercert=[transport-certificate.cer]`: The path to your Transport certificate (it usually ends with [!DNL .cer], [!DNL .der], or [!DNL .pem]). 
    
    * `encrypt.sign.certfile=[packager-credentials.pfx]`: The path to your Packager certificate (this ends with [!DNL .pfx]). 
    
    * `encrypt.sign.certpass=[password]`: The password for your Packager certificate.     
    
      >[!NOTE]
      >
      >Ensure that you do not scramble the password.

1. Create a policy.

   In your local [!DNL Command Line Tools\] folder, run the following command: 

   ```
   java -jar libs/AdobePolicyManager.jar new examplepolicy.pol -n examplepolicy -x
   ```

   This command creates a policy file named [!DNL examplepolicy.pol] that uses anonymous license server authentication (the [!DNL -x] option).
1. Copy the MP4, FLV, or F4V video file that you want to encrypt into your local [!DNL Command Line Tools\] folder.
1. Package your content.

   Let's say that your source video file is [!DNL sample.mp4]. In your local [!DNL Command Line Tools\] folder, run the following command: 

   ```
   java -jar libs/AdobePackager.jar sample.mp4 sample_encrypted.mp4 -p examplepolicy.pol
   ```

   >[!NOTE]
   >
   >If you want to package HLS, HDS or DASH contents, you must use a different packager tool, such as [Adobe Primetime Offline Packager](https://help.adobe.com/en_US/primetime/packagers/offline/index.html#Packagers-concept-Primetime_Offline_Packager_Getting_Started).

1. Copy the encrypted file artifacts (in this case [!DNL sample_encrypted.mp4] and [!DNL sample_encrypted.mp4.metadata]) to [!DNL <Your Content Server - Tomcat Install Dir>\webapps\ROOT].
>At this point you have completed the packaging phase of the process. >
>>[!NOTE]
>>
>>For more detailed information on command-line tools for packaging content, creating policies, and more, see [Adobe Primetime DRM Command-line tools](https://help.adobe.com/en_US/primetime/drm/5.3/reference_implementations/index.html#concept-Commandline_tools). 
>
