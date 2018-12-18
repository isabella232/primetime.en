---
description: You can turn on this feature and check for related events.
seo-description: You can turn on this feature and check for related events.
seo-title: Use live master-manifest update
title: Use live master-manifest update
uuid: 4ec665ab-b7ce-4a45-a251-13a07eb4d789
index: y
internal: n
snippet: y
---

# Use live master-manifest update{#use-live-master-manifest-update}

You can turn on this feature and check for related events.

1. To turn on live master-manifest updates, set the update frequency (in minutes) by setting the `NetworkConfiguration.masterUpdateInterval` property.
1. Optionally, track successful manifest updates by listening for the `MediaPlayerItemEvent.MASTER_UPDATED` event.
