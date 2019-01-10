---
seo-title: Custom authentication/entitlement overview (Optional)
title: Custom authentication/entitlement overview (Optional)
uuid: 8b5e38a5-562c-4781-ac40-4b3d6cdd97fe
index: y
internal: n
snippet: y
---

# Custom authentication/entitlement overview (Optional){#custom-authentication-entitlement-overview-optional}

Primetime Cloud DRM can be configured to reach out to your own Back-End Authentication/Entitlement service to determine:

* Is this user allowed to acquire a license? 
* What rights/restrictions should go into the license?

Primetime Cloud DRM includes a reference implementation of a back-end authentication/entitlement service. For demonstration purposes, this server is issuing "allow" responses to BEES requests. See [!DNL BEESServlet.java] to modify the server behavior. 

>[!NOTE]
>
>Previously, this was a separate product called *Back End Entitlement Server* (BEES), thus the references to BEES throughout this document and in the source files.

