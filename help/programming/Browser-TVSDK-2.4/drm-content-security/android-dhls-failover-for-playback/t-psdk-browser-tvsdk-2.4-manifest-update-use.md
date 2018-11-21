---
description: You can turn on this feature and check for related events.
seo-description: You can turn on this feature and check for related events.
seo-title: Use live master-manifest update
title: Use live master-manifest update
uuid: a06112aa-39fc-4b1f-8e89-71fd0851a7d7
index: y
internal: n
snippet: y
---

# Use live master-manifest update{#use-live-master-manifest-update}

You can turn on this feature and check for related events.

1. To turn on live master-manifest updates, set the update frequency (in minutes) by setting the `NetworkConfiguration.masterUpdateInterval` property.
1. Optionally, track successful manifest updates by listening for the `MediaPlayerItemEvent.MASTER_UPDATED` event.
