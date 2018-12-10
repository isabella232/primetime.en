---
seo-title: Implement identity-based domain registration
title: Implement identity-based domain registration
uuid: fbe4c505-973c-42b6-a4a4-3486d225ad8d
index: y
internal: n
snippet: y
---

# Implement identity-based domain registration{#implement-identity-based-domain-registration}

1. Create a DRM policy with mandatory domain registration.
1. Specify the server’s host and port for the domain server URL.

   In your [!DNL .properties] file, set: 

   ```
   policy.domain.url=http://[ 
<i>server:port</i>] 
   ```

1. Make authentication with a username and password mandatory.

   In your [!DNL .properties] file, set: 

   ```
   policy.domain.anonymous=false 
   ```

