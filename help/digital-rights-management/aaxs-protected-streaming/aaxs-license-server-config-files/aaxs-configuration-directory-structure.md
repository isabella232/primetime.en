---
description: The Adobe Access Server for Protected Streaming requires two types of configuration files  a global configuration file (flashaccess-global.xml) and a tenant configuration file for each tenant (flashaccess-tenant.xml).
seo-description: The Adobe Access Server for Protected Streaming requires two types of configuration files  a global configuration file (flashaccess-global.xml) and a tenant configuration file for each tenant (flashaccess-tenant.xml).
seo-title: Configuration Directory Structure
title: Configuration Directory Structure
uuid: c6cfc734-6b7c-4502-9bdb-c7aaca156e0e
index: y
internal: n
snippet: y
---

# License server configuration files & Configuration Directory Structure {#configuration-directory-structure}

The Adobe Access Server for Protected Streaming requires two types of configuration files: a global configuration file (flashaccess-global.xml) and a tenant configuration file for each tenant (flashaccess-tenant.xml).

After editing the configuration files, Adobe recommends using the utilities provided with the Adobe Access Server for Protected Streaming to verify that the files are well-formed. For more information, see "[Configuration Validator](../../aaxs-protected-streaming/aaxs-protected-streaming-utilities/configuration-validator.md)".

To avoid making passwords available in clear text in the configuration files, all passwords specified in the global and tenant configuration files must be encrypted. For more information on encrypting passwords, see "[Password Scrambler](../../aaxs-protected-streaming/aaxs-protected-streaming-utilities/password-scrambler.md)".

The configuration directories have the following structure:

```
<i class="+ topic ph hi-d="" i "="">
  LicenseServer.ConfigRoot/  
  flashaccess-global.xml  
  pkcs11.cfg (optional)  
  flashaccessserver/  
   libs/ (optional)  
   tenants/  
     
 <i class="+ topic ph hi-d="" i "="">
   tenantname/  
      flashaccess-tenant.xml  
       
  <i class="+ topic ph hi-d="" i "="">
    credential.pfx (optional)  
        
   <i class="+ topic ph hi-d="" i "="">
     packagercert.cer (optional) 
   </i class="+ topic> 
  </i class="+ topic> 
 </i class="+ topic> 
</i class="+ topic>
```

