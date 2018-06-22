---
description: You can enable and build controls for 608 and 708 closed captions as well as WebVTT subtitles.
seo-description: You can enable and build controls for 608 and 708 closed captions as well as WebVTT subtitles.
seo-title: Closed captions
title: Closed captions
---

# Closed captions


* When you select a media item, you are provided with a user interface where you can choose to view closed captions for that item. Active tracks are indicated by a `codeph has activity` message. Selecting an active track turns its visibility on.
* If you select CC, all the closed caption tracks for the media item are displayed.
* To remove the closed captions, select None from the chooser dialog.

To implement closed captions, you need to edit .



The PlayerFragment calls the `apiname displayClosedCaptioningDialog()` function, which populates the captions array with the tracks returned from the `codeph CCManager`, using the function `apiname getClosedCaptionTracks()`.

When you select a language, the index or the language is passed back to the `codeph CCManager` to be displayed on the device. If you select None, no captions are displayed.

The `codeph selectClosedCaptionTrack()` function from `codeph CCManager` provides a list of all tracks in the player interface.

The reference implementation reads the configuration parameters from the Android `codeph SharedPreferences` file, for convenience. You can configure the player to read configuration from whatever source you are currently using.

