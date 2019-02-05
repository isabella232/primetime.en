---
description: null
seo-description: null
seo-title: Add Digital Rights Management
title: Add Digital Rights Management
uuid: 7bd1303b-32bc-4b00-9c0f-faf42f8f5cd5
---

# Add Digital Rights Management{#add-digital-rights-management}

1. Add the `DRMMetadataInfoAvailableEvent` to get the `DRMMetadata`.

   ```js
   player.addEventListener(AdobePSDK.PSDKEventType.DRM_METADATA_INFO_AVAILABLE, onDRMMetadataInfoAvaialble);
   ```

1. Implement the `onDRMMetadataInfoAvailable` section above the line in step 1.

   ```js
   var onDRMMetadataInfoAvaialble = function(event) { 
    var drmMetadataInfo = event.drmMetadataInfo; 
    var drmMetadata = null; 
    
    if(drmMetadataInfo) { 
     drmMetadata = drmMetadataInfo.drmMetadata; 
    } 
    
    drmManager.acquireLicense(drmMetadata, null, null); 
   };
   ```

1. Create the DRMManager in the setupVideo method.

   ```js
   var drmManager = player.drmManager;
   ```

1. Create the protection data for Widevine and PlayReady by copying the following sample:

   ```js
   var protectionData = { 
     "com.widevine.alpha":{ 
       "serverURL":"https://wv.service.expressplay.com/hms/wv/rights/? 
                    ExpressPlayToken=[YOUR_EXPRESSPLAY_TOKEN]"  
     }, 
    
     "com.microsoft.playready":{ 
       "serverURL":"https://pr.test.expressplay.com/playready/RightsManager.asmx? 
                    ExpressPlayToken=[YOUR_EXPRESSPLAY_TOKEN]", 
         "httpRequestHeaders":{ 
       } 
     } 
   };
   ```

1. Add the protection data to the drmManager.

   ```js
   drmManager.setProtectionData(protectionData);
   ```

1. Change the resource URL to a DASH test stream.

   >[!TIP]
   >
   >Ensure that you update the resource type, because this is now DASH.

   ```js
   var resourceUrl = "https://ptdemos.com/videos/dashdrm/stream.mpd"; 
   var resourceType = AdobePSDK.MediaResourceType.DASH;
   ```

1. Test your configuration.
