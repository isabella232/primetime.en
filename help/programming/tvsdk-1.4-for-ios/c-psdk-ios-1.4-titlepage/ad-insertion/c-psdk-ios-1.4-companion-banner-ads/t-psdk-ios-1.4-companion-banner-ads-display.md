---
description: To display banner ads, you need to create banner instances and allow TVSDK to listen for ad-related events.
seo-description: To display banner ads, you need to create banner instances and allow TVSDK to listen for ad-related events.
seo-title: Display banner ads
title: Display banner ads
uuid: 7cc25d0f-279c-4079-af61-7d1ec5dcd846
---

# Display banner ads {#display-banner-ads}

To display banner ads, you need to create banner instances and allow TVSDK to listen for ad-related events.

TVSDK provides a list of companion banner ads that are associated with a linear ad through the `PTMediaPlayerAdPlayStartedNotification` notification event.

Manifests can specify companion banner ads by:

* An HTML snippet 
* The URL of an iFrame page 
* The URL of a static image or an Adobe Flash SWF file

For each companion ad, TVSDK indicates which types are available for your application. 

1. Create  a `PTAdBannerView`  instance for each companion ad slot on your page.

       Ensure that the following information has been provided:

    * To prevent the retrieval of companion ads of different sizes, a banner instance that specifies the width and height. 
    * Standard banner sizes.

1. Add an observer for the `PTMediaPlayerAdStartedNotification` that does the following:
   1. Clears existing ads in the banner instance.
   1. Gets the list of companion ads from `Ad.getCompanionAssets` `PTAd.companionAssets`.
   1. If the list of companion ads is not empty, iterate over the list for banner instances.
   
      Each banner instance ( a `PTAdAsset`) contains information, such as width, height, resource type (html, iframe, or static), and data that is required to display the companion banner.   
   1. If a video ad has no companion ads booked with it, the list of companion assets contains no data for that video ad.
   
      To show a standalone display ad, add the logic to your script to run a normal DFP (DoubleClick for Publishers) display ad tag in the appropriate banner instance.   
   1. Sends the banner information to a function on your page that displays the banners in an appropriate location.
   
      This is usually a `div`, and your function uses the `div ID` to display the banner. For example:

      ```   
      - (void) onMediaPlayerAdPlayStarted:(NSNotification *) notification { 
          _currentAd  = [notification.userInfo  objectForKey:PTMediaPlayerAdKey];  
          if (_currentAd != nil) { 
              [self removeAllBanners]; // remove any existing PTAdBannerView views 
       
              // banners 
              if (_currentAd.companionAssets && _currentAd.companionAssets.count > 0) { 
                  PTAdAsset *bannerAsset = [_currentAd.companionAssets objectAtIndex:0]; 
       
                  PTAdBannerView *bannerView = [[PTAdBannerView alloc] initWithAsset:bannerAsset];  
                  bannerView.player = self.player; 
                  bannerView.delegate = self; 
       
                  bannerView.frame = CGRectMake(0.0, 0.0, bannerAsset.width, bannerAsset.height);  
                  [_adBannerView.bannerView addSubview:bannerView]; 
              } 
          } 
      }
      ```

