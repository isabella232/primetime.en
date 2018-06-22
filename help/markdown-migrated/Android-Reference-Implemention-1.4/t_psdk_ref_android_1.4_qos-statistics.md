---
description: You can set up your player to read playback and device statistics from the QoSProvider as often as needed.
seo-description: You can set up your player to read playback and device statistics from the QoSProvider as often as needed.
seo-title: Display QoS playback and device statistics
title: Display QoS playback and device statistics
---

# Display QoS playback and device statistics

The`codeph QoSProvider` class provides various statistics, including the frame rate, the profile bit rate, the total time spent in buffering, the number of buffering attempts, the time it took to get the first byte from the first video fragment, the time it took to render the first frame, the currently buffered length, and the buffer time.
The reference implementation provides a `codeph QoSManager` class where you can enable the display of the QoS overlay. You can also enable the QoS visibility in the Settings user interface:

The `codeph QoSManager` tracks QoS statistics by getting device information, attaching to the media player, and updating with the latest QoS information.

