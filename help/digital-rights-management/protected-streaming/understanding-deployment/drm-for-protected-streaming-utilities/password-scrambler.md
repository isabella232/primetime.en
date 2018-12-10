---
description: The Password Scrambler utility encrypts a password for the Adobe Primetime DRM Server for Protected Streaming configuration files.
seo-description: The Password Scrambler utility encrypts a password for the Adobe Primetime DRM Server for Protected Streaming configuration files.
seo-title: Password scrambler
title: Password scrambler
uuid: f4ff9444-978a-4803-bc53-e21cd31802d8
index: y
internal: n
snippet: y
---

# Password scrambler{#password-scrambler}

The Password Scrambler utility encrypts a password for the Adobe Primetime DRM Server for Protected Streaming configuration files.

To run the scrambler, type:

```
Scrambler.bat  
<i class="+ topic ph hi-d="" i "="">
  password 
</i class="+ topic>
```

or

```
java -jar libs/flashaccess-scrambler.jar  
<i class="+ topic ph hi-d="" i "="">
  password  
</i class="+ topic>
```

The utility displays the following message:

```
Encrypted password:  
<i class="+ topic ph hi-d="" i "="">
  scrambled-password 
</i class="+ topic>
```

All passwords that you have specified in the [!DNL flashaccess-global.xml] and [!DNL flashaccess-tenant.xml] files must be encrypted.

>[!NOTE] {class="- topic/note "}
>
>The Password Scrambler utility in the Primetime DRM Server for Protected Streaming is not interchangeable with the scrambler that is provided with the Reference Implementation License Server.

