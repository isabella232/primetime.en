---
description: Here is some information and examples about how the accommodates updated master manifests.
seo-description: Here is some information and examples about how the accommodates updated master manifests.
seo-title: Live master-manifest update architecture
title: Live master-manifest update architecture
uuid: 7f0b5b95-5677-437a-9a5d-efa922a8bb9f
index: n
internal: n
snippet: y
translate: y
---

# Live master-manifest update architecture

By default, this feature is turned off. If your application turns it on by setting an update frequency in minutes, the following steps occur after every update interval:

1. The  <!-- PH element: phrases/primetime-sdk-name --> checks the master manifest's last modified time and etag to determine whether the file has been updated.If both the time and etag have changed, the file is deemed as modified.

1. The  <!-- PH element: phrases/primetime-sdk-name --> parses and analyzes the new manifest and takes appropriate action based on the nature of the update.
1. If the current playing bit rate matches the bit rate of the modified manifest, the  <!-- PH element: phrases/primetime-sdk-name --> switches to the new profile.The new profile could be from a different server or the same server, at the same bit rate. In this case, the transition is smooth.

1. If the current playing bit rate is no longer present in the new manifest, the  <!-- PH element: phrases/primetime-sdk-name --> tries to find a bit rate in the current profile that also exists in the new manifest.
    * If a match is found, the player first switches to the matching bit rate profile in the existing manifest and switches to the matching bit rate profile in the updated manifest. This ensures that the transition is smooth.
    * If there is no bit rate in common between the previous manifest and the new manifest, or if the  <!-- PH element: phrases/primetime-sdk-name --> cannot switch to the bit rate that matches, the <!-- PH element: phrases/primetime-sdk-name --> switches directly to the lowest bit rate profile of the new manifest and uses ABR to switch to any allowable bit rate based on bandwidth. This may cause a slight glitch in playback but should have minimal impact.

1. If the update is successful, the  <!-- PH element: phrases/primetime-sdk-name --> dispatches a `MediaPlayerItemEvent.MASTER_UPDATED` event.
1. If the update is not successful, playback continues with the set-up from before this update.

