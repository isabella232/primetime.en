---
seo-title: White-list for Adobe® Primetime applications allowed to play protected content
title: White-list for Adobe® Primetime applications allowed to play protected content
uuid: 3b1f938c-5c76-459e-a918-dfbec0fc2ff9
---

# White-list for Adobe® Primetime applications allowed to play protected content {#white-list-for-adobe-primetime-applications-allowed-to-play-protected-content}

Specifies the AIR/iOS applications that can play content. Specify the AIR/iOS application ID, minimum version, maximum version, and publisher ID.

Example use case: Use this rule to limit playback to a particular AIR/iOS application, or to control which version can access the content. 

>[!NOTE] {class="- topic/note "}
>
>If you are using Adobe Flash Builder to build protected applications, make sure that you do not deploy the application in ‘Debug' mode. When deploying an application in ‘Debug' mode, the Flash Builder will append “.debug” to the AIR application ID. This will cause the white-list functionality in Adobe Access to behave unexpectedly.

