---
description: 
seo-description: 
seo-title: Configure Video Analytics
title: Configure Video Analytics
---

# Configure Video Analytics

You can track video usage in the Primetime Android Reference Implementation by configuring it to work with your Adobe Analytics account. The Android Reference Implementation is designed to send video usage and heartbeat data to Adobe Analytics. To enable this feature, you must first contact your Adobe Primetime representative and create an Adobe Analytics account.

There are two places within the Reference Implementation that you must configure to enable the Adobe Analytics integration. The run-time Video Analytics configurations take affect once a new video is selected for playback (i.e. once a new PlayerActiviy is created).

>1. Configure load-time options in the `codeph ADBMobileConfig.json` assets file.
>   This file is provided by your Adobe representative. It is not included in the Primetime SDK bundle by default. For more information on the settings in this config file, see the Android Programmer's Guide here:[Initialize and configure video analytics](http://help.adobe.com/en_US/primetime/psdk/android/index.html#PSDKs-task-Initialize_and_configure_video_analytics_).
>   
>1. Configure run-time options in the Reference Implementation settings menu
><table id="table_lsq_hg5_zr"> 
 <tgroup cols="2"> 
  <thead> 
   <tr> 
    <th class="entry">Run-time Options</th> 
    <th class="entry">Description</th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td>Video Analytics tracking server</td> 
    <td>URL of the video analytics back-end collection end-point. This is where all video heartbeat tracking calls are sent.</td> 
   </tr> 
   <tr> 
    <td>Job ID</td> 
    <td>The processing job identifier. This indicates to the back-end endpoint which kind of processing to apply for the video-tracking calls.</td> 
   </tr> 
   <tr> 
    <td>Channel</td> 
    <td>The name of the channel where the user is watching the content. For a mobile application, this is typically the name of the application.</td> 
   </tr> 
   <tr> 
    <td>Publisher</td> 
    <td>The name of the content publisher</td> 
   </tr> 
   <tr> 
    <td>Debug Logging</td> 
    <td>Activates extensive logging. Disabled by default, this can impact performance when enabled, so you disable this for a production environment.</td> 
   </tr> 
   <tr> 
    <td>Quiet Mode</td> 
    <td>When this is enabled, no network calls are made, so this would be useful for local debugging, but must be disabled for a production environment.</td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>   
>   
>   
