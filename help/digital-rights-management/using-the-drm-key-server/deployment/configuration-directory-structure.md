---
seo-title: Configuration directory structure
title: Configuration directory structure
uuid: 043887cf-7b2c-4427-88e8-6273d8c0c3ea
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

