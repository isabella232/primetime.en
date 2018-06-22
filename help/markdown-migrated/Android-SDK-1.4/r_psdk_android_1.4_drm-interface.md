---
---

<a id="section_4DD54E085AB345FE9BE00865E56B28DB"></a>

provides a scalable, efficient workflow to implement content protection in  applications. You protect and manage the rights to your video content by creating a license for each digital media file.

Refer to the DRM sample player code included in the  package.

These are the most important API elements for working with DRM:
  *
  A reference in the media player to the DRM manager object that implements the DRM subsystem:
  ```java
  MediaPlayer.getDRMManager();
  ```
  >[!TIP]
  >
  >This API will return a valid`codeph  DRMManager` object only after the `codeph  MediaPlayerEvent.DRM_METADATA` is fired. If you call `codeph  getDRMManager()` before this event fires, it might return NULL.
  
  
* The `codeph  DRMHelper` helper class, which is useful when implementing DRM workflows.
  You can see `codeph  DRMHelper` in `codeph  ReferencePlayer`.
  
  
* A `codeph  DRMHelper` metadata loader method, which loads DRM metadata when it is located in a separate URL from the media.
  ```java
  public static void loadDRMMetadata(final DRMManager drmManager, 
   final String drmMetadataUrl, 
   final DRMLoadMetadataListener loadMetadataListener);
  ```
  
* A `codeph  DRMHelper` method to check the DRM metadata to determine whether authentication is needed.
  ```java
  /** 
  * Return whether authentication is needed for the provided 
  * DRMMetadata. 
  * 
  * @param drmMetadata 
  * The desired DRMMetadata on which to check whether auth is needed. 
  * @return whether authentication is required for the provided metadata 
  */ 
  public static boolean isAuthNeeded(DRMMetadata drmMetadata);
  ```
  
* `codeph  DRMHelper` method to perform authentication.
  ```java
  /** 
  * Helper method to perform DRM authentication. 
  * 
  * @param drmManager 
  * the DRMManager, used to perform the authentication. 
  * @param drmMetadata 
  * the DRMMetadata, containing the DRM specific information. 
  * @param authenticationListener 
  * the listener, on which the user can be notified about the 
  * authentication process status. 
  * @param authUser 
  * the DRM username provider by the user. 
  * @param authPass 
  * the DRM password provided by the user. 
  */ 
  public static void performDrmAuthentication(final DRMManager drmManager, 
  final DRMMetadata drmMetadata, 
  final String authUser, 
  final String authPass, 
  final DRMAuthenticationListener authenticationListener);
  ```
  
* Events that notify your application about various DRM activities and status.

<a id="section_899BD9061D484E1BBA46E84617C36867"></a>

Additional relevant API elements:
* [ com.adobe.ave.drm.DRMManager ](http://help.adobe.com/en_US/primetime/api/drm/com/adobe/ave/drm/DRMManager.html)
* [ com.adobe.ave.drm.DRMMetdata ](http://help.adobe.com/en_US/primetime/api/drm/com/adobe/ave/drm/DRMMetadata.html)
* [ com.adobe.ave.drm.DRMPolicy ](http://help.adobe.com/en_US/primetime/api/drm/com/adobe/ave/drm/DRMPolicy.html)
* [ com.adobe.ave.drm.DRMAuthenticationMethod ](http://help.adobe.com/en_US/primetime/api/drm/com/adobe/ave/drm/DRMAuthenticationMethod.html)
* [ com.adobe.ave.drm.DRMAuthenticationCompleteCallback ](http://help.adobe.com/en_US/primetime/api/drm/com/adobe/ave/drm/DRMAuthenticationCompleteCallback.html)
* [ com.adobe.ave.drm.DRMOperationErrorCallback ](http://help.adobe.com/en_US/primetime/api/drm/com/adobe/ave/drm/DRMOperationErrorCallback.html)
* [ com.adobe.mediacore.drm.DRMAuthenticateListener ](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_2.4/com/adobe/mediacore/drm/DRMAuthenticateListener.html)

<a id="section_F58941D68EB94A5EBD1C7454D2A1B17A"></a>

For more information about DRM, see the [  documentation ](http://help.adobe.com/en_US/primetime/drm).

