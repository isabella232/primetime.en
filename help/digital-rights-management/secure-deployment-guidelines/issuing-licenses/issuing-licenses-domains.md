---
description: To prevent users from backing up and restoring files to bypass domain de-registration, you must implement some domain management approaches.
seo-description: To prevent users from backing up and restoring files to bypass domain de-registration, you must implement some domain management approaches.
seo-title: Managing Domains
title: Managing Domains
uuid: 755c3bd3-7c0a-4626-b5ac-319bd8548451
index: y
internal: n
snippet: y
---

# Managing Domains{#managing-domains}

To prevent users from backing up and restoring files to bypass domain de-registration, you must implement some domain management approaches.

Here are some domain management approaches:

* Limit the amount of time the domain credentials are valid.

  Clients need to contact the domain server to reacquire domain credentials when the credentials expire. At that time, the Domain Server can verify that the machine is still authorized to be a member of the domain. 
* Roll over the domain keys each time a user deregisters.

  The License Server should only issue licenses to clients that have the latest domain key. This approach assumes that the License Server can coordinate with the Domain Server to know which key is the latest. Rolling over the domain keys involves generating a new key pair for the domain. When you roll over the keys for a domain, increment the key version in `generateDomainCredential`. 
* If the domain server is the same as the license server, the server can use the rollback counter to detect a backup and restore.

  For more information, see [Processing Adobe Primetime DRM requests](http://help.adobe.com/en_US/primetime/drm/5.3/protecting_content/index.html#DRM-concept-Processing_Adobe_Primetime_DRM_requests).
