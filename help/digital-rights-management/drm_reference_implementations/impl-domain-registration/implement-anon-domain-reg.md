---
seo-title: Implement anonymous domain registration
title: Implement anonymous domain registration
uuid: 0721e3ea-8b90-4372-9373-c56d0b0e1c87
index: y
internal: n
snippet: y
---

# Implement anonymous domain registration{#implement-anonymous-domain-registration}

1. Create a DRM policy that specifies that domain registration is required.
1. Specify the domain server URL as:

   ```
   http://[ 
<i>host:port</i>]/flashaccess/domainserver/domainname/
   ```

1. Make anonymous authentication mandatory.

   In your [!DNL .properties] file, set: 

   ```
   policy.domain.anonymous=true 
   ```

