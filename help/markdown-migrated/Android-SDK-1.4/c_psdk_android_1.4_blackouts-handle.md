---
description: You can handle blackouts in live video streams and provide alternate content during a blackout.
seo-description: You can handle blackouts in live video streams and provide alternate content during a blackout.
seo-title: Handle blackouts in live streams
title: Handle blackouts in live streams
---

# Handle blackouts in live streams

When a blackout occurs in a live stream, your player uses event handlers to detect the blackout and provide alternate content to those users who are ineligible to watch the main stream. Your player detects the start and end of the blackout period, switches playback from the main stream to an alternate stream, and switches back to the main stream when the blackout period ends.

To handle blackouts in live streams:
1. Set up your app to detect blackout tags by subscribing to blackout tags in a live-stream manifest.
   does not detect blackout tags on its own; you must subscribe to blackout tags to receive notification when the tags are encountered during manifest file parsing.
   
   
1. Create event listeners for tags to which your player is subscribed .
   When a tag occurs that your player has subscribed to (for example, a blackout tag) in either the foreground (main content) or background (alternate content) stream manifests,  dispatches a `codeph  TimedMetadataEvent` and creates a `codeph  TimedMetadataObject` for the `codeph  TimedMetadataEvent`.
   
   
1. Implement handlers for the timed metadata events for both the foreground and the background streams.
   In these handlers, get the start and end times for the blackout period from the timed metadata event objects.
   
   
1. Create methods for switching content at the start and end of the blackout period.
   When the blackout period starts, switch the main content to the background and switch the alternate content to become the main stream. Continue to fetch and parse the original manifest in the background and keep checking for the "blackout end" tag, so that the player can rejoin the original stream when the blackout ends.
   
   
1. Update nonseekable ranges if the blackout range is in DVR on the playback stream.
   Track and handle the `codeph  TimedMetadata` on the background stream, by preparing and updating blackout nonseekable ranges.
   
   

