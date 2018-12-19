---
seo-title: Generate CRLs to supplement those published by Adobe
title: Generate CRLs to supplement those published by Adobe
uuid: 4e93f6d3-5a04-44e9-9e6b-e878798b68f5
index: y
internal: n
snippet: y
---

# Generate CRLs to supplement those published by Adobe{#generate-crls-to-supplement-those-published-by-adobe}

Adobe Access lets you create CRLs to supplement the machine CRL published by Adobe. Adobe Access SDK checks and enforces the Adobe CRLs, however, you can disallow additional client machines by creating a CRL that revokes additional machine credentials. To do this, you must pass the CRL to Adobe Access SDK, then, when issuing a license, the SDK checks both the Adobe CRL and your own CRL.

To learn more about generating CRLs, see `RevocationListFactory` in *Adobe Access API Reference*. 
