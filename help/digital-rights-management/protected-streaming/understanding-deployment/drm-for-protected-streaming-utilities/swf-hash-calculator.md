---
description: The SWF Hash Calculator utility calculates the digest of a SWF application that is located in a file.
seo-description: The SWF Hash Calculator utility calculates the digest of a SWF application that is located in a file.
seo-title: SWF hash calculator
title: SWF hash calculator
uuid: 61c4e356-2902-4c41-b500-e699445dd5b0
index: y
internal: n
snippet: y
---

# SWF hash calculator{#swf-hash-calculator}

The SWF Hash Calculator utility calculates the digest of a SWF application that is located in a file.

To run the hasher, type:

```
Hasher.bat 
<i class="+ topic ph hi-d="" i "="">
  filename.swf
</i class="+ topic>
```

or

```
java -jar libs/flashaccess-hasher.jar 
<i class="+ topic ph hi-d="" i "="">
  filename.swf
</i class="+ topic>
```

The utility displays the following message:

```
SWF Hash: 
<i class="+ topic ph hi-d="" i "="">
  hash-of-swf
</i class="+ topic>
```

You can use this value to specify the SWF digest in [!DNL flashaccess-tenant.xml]. 
