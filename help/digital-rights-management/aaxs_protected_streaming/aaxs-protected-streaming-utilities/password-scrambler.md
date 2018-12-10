---
seo-title: Password Scrambler
title: Password Scrambler
uuid: f6c0926d-45cb-4e1c-a27c-8777b4327118
index: y
internal: n
snippet: y
---

# Password Scrambler{#password-scrambler}

The Password Scrambler utility encrypts a password so that it can be used in the Adobe Access Server for Protected Streaming configuration files. To run the scrambler, run the command:

```
Scrambler.bat  
<i class="+ topic ph hi-d="" i "="">
  password 
</i class="+ topic>
```

or the command:

```
java -jar libs/flashaccess-scrambler.jar  
<i class="+ topic ph hi-d="" i "="">
  password  
</i class="+ topic>
```

The utility outputs the following message:

```
Encrypted password:  
<i class="+ topic ph hi-d="" i "="">
  scrambled-password 
</i class="+ topic>
```

All passwords specified in flashaccess-global.xml and flashaccess-tenant.xml must be encrypted.

>[!NOTE] {class="- topic/note "}
>
>The Password Scrambler utility in the Adobe Access Server for Protected Streaming is not interchangeable with the scrambler provided with the Reference Implementation License Server.

