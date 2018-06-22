---
description: You can read quality of service (QoS) information about downloaded resources, such as fragments and tracks, from the LoadInformation class.
seo-description: You can read quality of service (QoS) information about downloaded resources, such as fragments and tracks, from the LoadInformation class.
seo-title: Track at the fragment level using load information
title: Track at the fragment level using load information
---

# Track at the fragment level using load information

>1. Implement and register the `codeph MediaPlayerEvent.LOAD_INFORMATION_AVAILABLE` event listener.
>   
>1. Call `codeph event.getLoadInformation()` to read the relevant data from the `codeph event` parameter that is passed to the callback.
>   For more about`codeph LoadInformation`, see [2.5 for Android (Java)](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_2.5/index.html) API docs.
>   
>   
