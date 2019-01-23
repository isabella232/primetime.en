---
seo-title: Packaging content
title: Packaging content
uuid: 5d1d4b9d-f241-4291-9577-e9de5a8b92be
index: y
internal: n
snippet: y
---

# Packaging content{#packaging-content}

When packaging content, the license server URL must be specified. The Adobe Access Server URL has the format:

```
http(s)://
<i class="+ topic ph hi-d="" i "="">
 license-server-host:port/flashaccessserver/
 <i class="+ topic ph hi-d="" i "="">
   tenant-name
 </i class="+ topic>
</i class="+ topic>
```

For example, for license server hostname "mylicenseserver.com" listening on port 8080 and a tenant named "tenant1", the license server URL to specify at packaging time is:

```
https://mylicenseserver.com:8080/flashaccessserver/tenant1
```

If each tenant uses a different License Server and Transport Credential, be sure to specify the correct tenant's certificate in the packager.

To ensure the server issues licenses only to content packaged by known packagers, include the packager's certificate in the packager whitelist of the tenant configuration file. 
