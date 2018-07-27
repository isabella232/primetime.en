---
description: When a user clicks an ad or a related button, your application is responsible for responding. provides you with information about the destination URL.
seo-description: When a user clicks an ad or a related button, your application is responsible for responding. provides you with information about the destination URL.
seo-title: Respond to clicks on ads
title: Respond to clicks on ads
uuid: a635d967-5493-498d-8e94-70825aa8f90e
index: n
internal: n
snippet: y
translate: y
---

# Respond to clicks on ads

Thisexample shows one possible way to manage ad clicks.

>1. Each time an ad is played, display a button on top of the media player. A user who clicks the ad is redirected to the ad URL. This button is part of the ` ClickableAdsOverlay.xml`.
>
>   ```
>   xml>   >   &lt;?xml version="1.0"?&gt; 
>   &lt;s:VGroup xmlns:fx="http://ns.adobe.com/mxml/2009"  
>       xmlns:s="library://ns.adobe.com/flex/spark" percentWidth="100" horizontalAlign="center"&gt;     
>           &lt;fx:Declarations&gt;&lt;fx:String id="text"/&gt;&lt;/fx:Declarations&gt; 
>           &lt;s:Label text="{text}"  backgroundAlpha="0.75" backgroundColor="#DEDEDE"  
>               color="#000000" paddingBottom="5" paddingRight="5" paddingLeft="5"  
>               paddingTop="5"/&gt; 
>   &lt;/s:VGroup&gt;
>   ```
>
>1. Include this overlay on our media player sample, ` psdkdemo.xml`.
>
>   ```
>   xml>   >   &lt;psdk:ClickableAdsOverlay id="clickableAdsOverlay"  
>       visible="false"   top="10" right="0" left="0"  
>       text="Click here for more information"   
>       click="onAdsOverlayClicked()" 
>   &lt;/psdk:ClickableAdsOverlay
>   ```

>
>1. To make the view visible only when an ad is playing, listen for the ` onAdStart` and ` onAdComplete` events dispatched by  <!-- PH element: phrases/primetime-sdk-name --> .
>
>   ```
>   _player.addEventListener(AdPlaybackEvent.AD_STARTED, onAdStarted); 
>   _player.addEventListener(AdPlaybackEvent.AD_COMPLETED, onAdCompleted); 
>   
>   ```

>
>   ```
>   >   private function onAdStarted(event:AdPlaybackEvent):void { 
>       var primaryAsset:AdAsset = event.ad.primaryAsset; 
>       if (primaryAsset.adClick != null) { 
>           clickableAdsOverlay.visible = true;  
>       } 
>   } 
>   private function onAdCompleted(event:AdPlaybackEvent):void { 
>       clickableAdsOverlay.visible = false; 
>   }
>   ```

>
>1. Monitor user interactions on clickable ads. When the user touches or clicks the ad or button, notify  <!-- PH element: phrases/primetime-sdk-name --> with ` notifyClick`.
>
>   ```
>   private function onAdsOverlayClicked():void {     
>       _mediaPlayer.view.notifyClick(); 
>   }
>   ```

>
>1. Listen for the ` AdclickEvent.AD_CLICK` event.
>   If an ad is playing,  <!-- PH element: phrases/primetime-sdk-name --> dispatches the ` AdClickEvent.AD_CLICK` event, from which you can retrieve the click-through URL and related information. 
>
>
>   ```
>   >   _player.addEventListener(AdClickEvent.AD_CLICK, onAdClick);
>   ```

>
>1. Pause the media player while directing the user to the ad URL.
>
>   ```
>   private function onAdClick(event:AdClickEvent):void { 
>       _logger.info("#onAdClick Ad clicked. Target url is {0}", event.adClick.url);  
>       _player.pause(); 
>       var adRequest:URLRequest = new URLRequest(event.adClick.url); 
>       navigateToURL(adRequest, event.adClick.title); 
>   }
>   ```

>
>1. Display the ad click-through URL and any related information.
>       For example, you could display it in one of the following ways:>    
>    * Open the click-throughURL in a browser within your application. On desktop platforms,the video ad playback area is typically used for invoking click-throughURLs upon user clicks.

>    * Redirect the userto the external mobile web browser. On mobile devices, thevideo ad playback area is used for other functions, such as hidingand showing controls, pausing playback, expanding to full screen,and so on. Therefore, on mobile devices, a separate view, such asa sponsor button, is usually presented to the user as a means tolaunch the click-through URL.

>    
>1. Close the browser window in which the click-through information is displayed and resume playing the video.
