---
description: Before you can use most of the player methods, the player must be in a valid status.
seo-description: Before you can use most of the player methods, the player must be in a valid status.
seo-title: Wait for a valid state
title: Wait for a valid state
uuid: c9684a55-fc5a-439b-940a-4b851231fdb3
index: n
internal: n
snippet: y
translate: y
---

# Wait for a valid state

The player moves through various statuses. Waiting for the player to be in the correct status ensures that the media resource has successfully loaded. If the player is not in at least the required status, many player methods throw throw ` IllegalStateException`. The required status is usually PREPARED.

>1. To confirm that the status is PREPARED:
>   When the player is initializing, wait for  <!-- PH element: phrases/primetime-sdk-name --> to call the callback for the ` MediaPlayerStatusChangeEvent.STATUS_CHANGED` event with PREPARED status. 
>   To check whether the current status of the ` MediaPlayer` object is at least PREPARED. >
>   ```
>   function getstatus():String;
>   ```

>
