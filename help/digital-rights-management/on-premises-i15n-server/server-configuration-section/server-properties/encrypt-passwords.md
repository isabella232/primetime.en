---
seo-title: Encrypt Passwords
title: Encrypt Passwords
uuid: 94dc7fe9-fe40-4779-912a-d84b58e4ee36
---

# Encrypt Passwords{#encrypt-passwords}

The properties files include several password values that you should not enter as plain text. Encrypt these values using the following command: 

1. `java -jar adobe-flashaccess-i15n-setup.jar password`
>This command will output an encrypted password, which you then use in the properties files. >
>>[!NOTE]
>>
>>This is not the utility used for encrypting License Server passwords. 
>

