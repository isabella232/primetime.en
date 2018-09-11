---
description: You can save the current playback position in a video and resume playing at the same position in a future session.
seo-description: You can save the current playback position in a video and resume playing at the same position in a future session.
seo-title: Save the video position and resume later
title: Save the video position and resume later
uuid: 6810b338-bf7e-44b1-aab4-f82a692ef222
index: y
internal: n
snippet: y
translate: y
---

# Save the video position and resume later

You can save the current playback position in a video and resume playing at the same position in a future session.

Dynamically inserted ads differ between user sessions, so saving the position **with** spliced ads refers to a different position in a future session. TVSDK provides methods to retrieve the playback position while ignoring spliced ads. 

1. When the user quits a video, your application retrieves and saves the position in the video.


   >[!TIP]
   >
   >Ad durations are not included.
   Ad breaks can vary in each session due to ad patterns, frequency capping, and so on. The current time of the video in one session might be different in a future session. When saving a position in the video, the application retrieves the local time . Use the `localTime` property to read this position, which you can save on the device or in a database on the server. 

   For example, if the user is at the 20th minute of the video, and this position includes five minutes of ads, `currentTime` will be 1200 seconds, while `localTime` at this position will be 900 seconds. 

   >[!IMPORTANT]
   >
   >Local time and current time are the same for live/linear streams. In this case, `convertToLocalTime` has no effect. For VOD, local time remains unchanged while ads play. 


   ```
   - (void) onMediaPlayerTimeChange:(NSNotification *)notification { 
       CMTimeRange seekableRange = self.player.seekableRange; 
        
       if (CMTIMERANGE_IS_VALID(seekableRange)) { 
           double seekableRangeStart = CMTimeGetSeconds(seekableRange.start); 
           double seekableRangeDuration = CMTimeGetSeconds(seekableRange.duration); 
           double currentTime = CMTimeGetSeconds(self.player.currentTime); // includes ads 
           double localTime = CMTimeGetSeconds(self.player.localTime); // no ads 
       } 
   }
   ```
1. 
   <!-- Q: Does iOS need the same step before this that The ANdroid & DHLS versions have: "Restore the user session when player activity resumes." with an example of how to do that? -->
   To resume the video at the same position:

    
    * To resume playing the video from the position that was saved from a previous session, use `seekToLocalTime`. 
      >[!TIP]
      >
      >This method is called only with local time values. If the method is called with current time results, incorrect behavior occurs.
    
    * To seek to the current time, use `seekToTime`.    
    
    
    
1. When your application receives the `PTMediaPlayerStatusReady` status change event, seek to the saved local time.

   ```
   [self.player seekToLocalTime:CMTimeMake(900, 1) completionHandler:^(BOOL finished) { 
       [self.player play]; 
   }];
   ```
1. Provide the ad breaks as specified in the ad policy interface.
1. Implement a custom ad policy selector by extending the default ad policy selector.
1. Provide the ad breaks that must be presented to the user by implementing `selectAdBreaksToPlay`.

   This method includes a pre-roll ad break and the mid-roll ad breaks before the local time position. Your application can decide to play a pre-roll ad break and resume to the specified local time, play a mid-roll ad break and resume to the specified local time, or play no ad breaks.
