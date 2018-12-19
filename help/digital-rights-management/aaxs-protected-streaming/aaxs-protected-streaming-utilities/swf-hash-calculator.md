---
seo-title: SWF Hash Calculator
title: SWF Hash Calculator
uuid: c1823208-92d9-47c5-b550-f9cc370b543d
index: y
internal: n
snippet: y
---

# SWF Hash Calculator{#swf-hash-calculator}

The SWF Hash Calculator utility calculated the digest of a SWF application located in a file. To run the hasher, run the command:

```
Hasher.bat 
<i class="+ topic ph hi-d="" i "="">
  filename.swf
</i class="+ topic>
```

or the command:

```
java -jar libs/flashaccess-hasher.jar 
<i class="+ topic ph hi-d="" i "="">
  filename.swf
</i class="+ topic>
```

The utility output the following message:

```
SWF Hash: 
<i class="+ topic ph hi-d="" i "="">
  hash-of-swf
</i class="+ topic>
```

This value can be used to specify the SWF digest in [!DNL flashaccess-tenant.xml]. 
