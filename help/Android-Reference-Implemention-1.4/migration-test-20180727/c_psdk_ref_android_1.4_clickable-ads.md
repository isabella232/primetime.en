---
description: Clickable ads are set up through (previously known as ). You set up the destination for your ad creatives through and then use the to get the external URL from the response.
seo-description: Clickable ads are set up through (previously known as ). You set up the destination for your ad creatives through and then use the to get the external URL from the response.
seo-title: Clickable ads
title: Clickable ads
uuid: 2d6c23d5-4903-4bd5-b770-d0a1b44e8e35
index: n
internal: n
snippet: y
translate: y
---

# Clickable ads

You can either enable clickable ads in the Primetime reference implementation through the Setting user interface or by implementing [ IAdConfig isClickableAdsEnabled() ](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IAdConfig.html). 
You can enable clickable ads in the Primetime reference implementation by clicking ** ` ON` ** in the ** ` Enable clickable ads` ** panel in the Settings user interface. 
<a id="fig_B638E8E7B60F468C92D1843A943F20CE"></a> ![](images/clickableads-configuration.jpg) 
The reference implementation demonstrates how to handle a clickable ad during an ad break.
You can implement various workflows, depending on your player user interface. The general workflow for the Primetime reference implementation is as follows: 
1. When an ad creative starts, the  determines if the ad is clickable.
1. If the ad is clickable, the player shows a button: ** ` Click here for more info.` **
1. If the user clicks the button, playback is paused and the device launches the default browser and loads the URL returned from the .

There are three components that the reference implementation uses to handle clickable ads:

* **Clickable Ad Fragment** This fragment sits on top of the video player fragment and contains the clickable button that notifies the player fragment to handle the click action. It only appears while the clickable ad plays.

* **AdsManagerOn** This is the feature manager that handles the advertisement workflow.

* **Player Fragment** This fragment checks if the current ad is clickable by calling isClickable() and shows the ad if it returns true. After it receives the event that is dispatched when a user clicks the "Click here for more info" button, it calls adsManager to trigger the clickable ad feature.

  ```
  java  /** 
   * Show ad break progress when each ad creative starts 
   * If this is a clickable ad, show the clickable ad fragment 
   */ 
  @Override 
  public void onAdStarted(AdBreak adBreak, Ad ad) { 
      adOverlay.startAd(adBreak, ad); 
      if (adsManager.isClickableAdsEnabled() &amp;&amp; ad.isClickable()) { 
          playerClickableAdFragment.show(); 
      } 
  } 
   
  /** 
   * Hide ad break progress when each ad ends 
   * Hide the clickable ad fragment 
   */ 
  @Override 
  public void onAdCompleted(AdBreak adBreak, Ad ad) { 
      adOverlay.stopAd(adBreak, ad); 
      playerClickableAdFragment.hide(); 
  } 
  
  ```
  This event handler is executed when the ` AdsManagerOn` displatches an ` AD_STARTED` event. It determines the clickability of an ad and if it is clickable, registers an event listener to detect any mouse clicks. 


>[!NOTE]
>
>If an ad has been properly configured with a click-through URL in Ad Serving but the "More info" button does not show up, check the ad request result to see if the click-through URL is included in the ad response. You can find the  ad request URL, ` ad.auditude.com/adserver`, in the log. 


