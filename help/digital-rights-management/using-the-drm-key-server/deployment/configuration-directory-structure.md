---
seo-title: Configuration directory structure
title: Configuration directory structure
uuid: d576185c-898d-45bd-b2f8-a53feea3ea43
index: y
internal: n
snippet: y
---

# Configuration directory structure{#configuration-directory-structure}

The configuration directories have the following structure: 

```
KeyServer.ConfigRoot/  
--flashaccess-keyserver-global.xml 
--pkcs11.cfg (optional) 
--faxsks/ 
----tenants/ 
------tenantname/
---------flashaccess-keyserver-tenant.xml 
---------credential.pfx (optional) 
```

