---
description: You can read quality of service (QoS) information about downloaded resources, such as fragments and tracks, from the LoadInformation class.
seo-description: You can read quality of service (QoS) information about downloaded resources, such as fragments and tracks, from the LoadInformation class.
seo-title: Track at the fragment level using load information
title: Track at the fragment level using load information
uuid: 6deaee91-af35-4c46-bc80-541a97b6480d
index: y
internal: n
snippet: y
translate: y
---

# Track at the fragment level using load information

You can read quality of service (QoS) information about downloaded resources, such as fragments and tracks, from the LoadInformation class.


1. Implement and register the `MediaPlayerEvent.LOAD_INFORMATION_AVAILABLE` event listener.
1. Call `event.getLoadInformation()` to read the relevant data from the `event` parameter that is passed to the callback.

   For more about `LoadInformation`, see [2.5 for Android (Java)](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_2.5/index.html) API docs.
