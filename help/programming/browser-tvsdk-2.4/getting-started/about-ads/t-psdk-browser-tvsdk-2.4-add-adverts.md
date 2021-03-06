---
description: null
seo-description: null
seo-title: Add Advertising
title: Add Advertising
uuid: 7762506f-b55e-445d-b8a2-c1208358a370
---

# Add Advertising {#add-advertising}

1. Define the advertising metadata.

   ```js
   var auditudeSettings = new AdobePSDK.AuditudeSettings(); 
     auditudeSettings.domain = "auditude.com"; 
     auditudeSettings.mediaId = "adbe_tearsofsteel2"; 
     auditudeSettings.zoneId = "123869";
   ```

1. Add the advertising metadata to the `MediaResource`.

   ```js
   var mediaResource =  
     new AdobePSDK.MediaResource(resourceUrl, resourceType, auditudeSettings, false);
   ```

1. Add the settings to the config and add a `SpliceOut` parser factory.

   ```js
   var config = new AdobePSDK.MediaPlayerItemConfig(); 
   config.advertisingMetadata = auditudeSettings; 
   config.advertisingFactory = new ExtCueOutContentFactory(auditudeSettings);
   ```

1. Add the `ExtCueOutContentFactory` to the library section.
1. Download the `ExtCueOutContentFactory.js` from the library section and place it in the working folder.

   ```js
   <script src= "frameworks/player/dash.min.js"></script> 
   <script src= "frameworks/player/primetimemain.min.js"></script> 
   <script src= "frameworks/player/swfobject.js"></script> 
   <script src= "frameworks/player/primetimeei.min.js"></script> 
   <script src= "ExtCueOutContentFactory.js"></script>
   ```

1. Test your configuration.
