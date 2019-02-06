---
description: The SDK periodically downloads CRLs that are published by Adobe. You must ensure that access to these files is not blocked or the enforcement of these CRLs is not prevented.
seo-description: The SDK periodically downloads CRLs that are published by Adobe. You must ensure that access to these files is not blocked or the enforcement of these CRLs is not prevented.
seo-title: Consuming CRLs published by Adobe
title: Consuming CRLs published by Adobe
uuid: 7a9088bd-dde6-4445-958c-3e7272215b3c
---

# Consuming CRLs published by Adobe{#consuming-crls-published-by-adobe}

The SDK periodically downloads CRLs that are published by Adobe. You must ensure that access to these files is not blocked or the enforcement of these CRLs is not prevented.

The SDK has a configuration option to ignore errors when retrieving Adobe CRLs, and you can only apply this option in development environments. In production environments, the license server must retrieve the CRLs from Adobe. If the license server cannot obtain a valid CRL, an error has occurred. 
