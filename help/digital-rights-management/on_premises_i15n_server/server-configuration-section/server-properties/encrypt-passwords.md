---
seo-title: Encrypt Passwords
title: Encrypt Passwords
uuid: b211a6af-f2f2-4d84-aeb9-855089edec89
index: y
internal: n
snippet: y
---

# Encrypt Passwords{#encrypt-passwords}

The properties files include several password values that you should not enter as plain text. Encrypt these values using the following command: 

1. `java -jar adobe-flashaccess-i15n-setup.jar password`
>This command will output an encrypted password, which you then use in the properties files. >
>>[!NOTE]
>>
>>This is not the utility used for encrypting License Server passwords. 
>

