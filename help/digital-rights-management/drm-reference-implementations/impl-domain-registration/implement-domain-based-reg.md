---
seo-title: Implement identity-based domain registration
title: Implement identity-based domain registration
uuid: 4a71b2e0-d1a2-4d63-9cbd-980a292774ab
---

# Implement identity-based domain registration{#implement-identity-based-domain-registration}

1. Create a DRM policy with mandatory domain registration.
1. Specify the server's host and port for the domain server URL.

   In your [!DNL .properties] file, set: 

   ```
   policy.domain.url=https://[ 
<i>server:port</i>] 
   ```

1. Make authentication with a username and password mandatory.

   In your [!DNL .properties] file, set: 

   ```
   policy.domain.anonymous=false 
   ```

