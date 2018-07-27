---
description: 302 redirect optimization minimizes the number of 302 redirect responses, which allows your application to load balance more effectively.
seo-description: 302 redirect optimization minimizes the number of 302 redirect responses, which allows your application to load balance more effectively.
seo-title: HTTP 302 redirect optimization
title: HTTP 302 redirect optimization
uuid: 1846af82-2e9e-474e-81f3-0802c862510d
index: n
internal: n
snippet: y
translate: y
---

# HTTP 302 redirect optimization

If a main manifest request is redirected, and 302 optimization is enabled in your player, subsequent requests made for assets from that manifest will use the final domain location, which avoids additional 302 responses.
This feature is disabled by default, and you can change this setting.
If you enable this feature, it works correctly only if *all* of the following conditions are true; otherwise, no redirect optimization occurs, and 302 responses continue to occur: 
* Your application was compiled for  <!-- PH element: phrases/flash-player-long --> 11.8, using ` -swf-version` 21 or higher.
* Your end users have  <!-- PH element: phrases/flash-player-long --> 11.8 or later installed.


>[!IMPORTANT]
>
>To ensure that cookies are passed with ad requests, disable 302 redirect. When 302 redirect is enabled, the ad request might be redirected to a domain that is different from the domain from which the cookie originated.

