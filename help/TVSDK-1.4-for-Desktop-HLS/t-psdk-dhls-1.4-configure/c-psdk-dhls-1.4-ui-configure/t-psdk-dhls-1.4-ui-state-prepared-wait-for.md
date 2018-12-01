---
description: Before you can use most of the TVSDK player methods, the player must be in a valid status.
seo-description: Before you can use most of the TVSDK player methods, the player must be in a valid status.
seo-title: Wait for a valid state
title: Wait for a valid state
uuid: 5f567f50-0de1-4fcb-8e2d-f2a3c5a2f7b7
index: y
internal: n
snippet: y
---

# Wait for a valid state{#wait-for-a-valid-state}

Before you can use most of the TVSDK player methods, the player must be in a valid status.

 The player moves through various statuses. Waiting for the player to be in the correct status ensures that the media resource has successfully loaded. If the player is not in at least the required status, many player methods throw throw `IllegalStateException`.

The required status is usually PREPARED. 

1. To confirm that the status is PREPARED:

   When the player is initializing, wait for TVSDK to call the callback for the `MediaPlayerStatusChangeEvent.STATUS_CHANGED` event with PREPARED status.

   To check whether the current status of the `MediaPlayer` object is at least PREPARED. 

   ```
   function getstatus():String;
   ```

