---
seo-title: Consume CRLs published by Adobe
title: Consume CRLs published by Adobe
uuid: 43f65edb-0c96-46ab-b787-1b5f0b4b093e
index: y
internal: n
snippet: y
---

# Consume CRLs published by Adobe{#consume-crls-published-by-adobe}

The SDK periodically downloads CRLs published by Adobe. Do not block access to these files or prevent enforcement of these CRLs.

The SDK has a configuration option to ignore errors when retrieving the Adobe CRLs. This option may only be used in development environments. In production environments, the license server must be able to retrieve the CRLs from Adobe. Failure to obtain a valid CRL is an error. 
