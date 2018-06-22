---
---

<a id="section_4DD54E085AB345FE9BE00865E56B28DB"></a>

provides a scalable, efficient workflow to implement content protection in  applications. You protect and manage the rights to your video content by creating a license for each digital media file.

supports  integration as custom DRM workflows. This means that your application must implement the DRM authentication workflows before playing the stream by using the Flash `codeph DRMManager`. To enable this, the `codeph MediaPlayer` provides you with the DRM manager for authentication.

These are the most important API elements for working with DRM:
  *
  A reference in the media player to the DRM manager object that implements the DRM subsystem:
  ```
  public function get drmManager():DRMManager
  ```
  
  

<a id="section_4204CE2731A44F67A3664AEDE8CCCA47"></a>

Additional relevant API elements:
* [flash.net.drm.DRMManager ](http://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/net/drm/DRMManager.html)
* [flash.net.drm.DRMContentData ](http://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/net/drm/DRMContentData.html)
* [flash.net.drm.DRMVoucher ](http://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/net/drm/DRMVoucher.html)
* [flash.net.drm.AuthenticationMethod](http://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/net/drm/AuthenticationMethod.html)
* [flash.events.DRMStatusEvent ](http://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/events/DRMStatusEvent.html)
* [flash.events.DRMErrorEvent ](http://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/events/DRMErrorEvent.html)

<a id="section_F58941D68EB94A5EBD1C7454D2A1B17A"></a>

For more information about DRM, see the [  documentation](http://help.adobe.com/en_US/primetime/drm).

