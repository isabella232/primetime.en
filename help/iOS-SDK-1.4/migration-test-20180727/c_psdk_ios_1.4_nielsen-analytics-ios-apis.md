---
description: The supports Nielsen Analytics.
seo-description: The supports Nielsen Analytics.
seo-title: API elements for Nielsen Analytics
title: API elements for Nielsen Analytics
uuid: a7baa45b-893a-4fab-9746-a95aad43a73a
index: n
internal: n
snippet: y
translate: y
---

# API elements for Nielsen Analytics

The following  elements facilitate your Nielsen Analytics integration: 

>[!NOTE]
>
>To enable Nielsen tracking, your application must link with the ` CoreLocation` iOS framework in the target. 


* **PTNielsenTrackingMetadata** Provides the information necessary to initialize a PTNielsenTracker instance and required channel and CMS metadata information.

  ```
  /** The name of the key associated with this PTNielsenTracker instance. */ 
  extern NSString *const  
<b>PTNielsenTrackingMetadataKey</b>; 
   
  @interface  
<b>PTNielsenTrackingMetadata</b> : PTMetadata 
    
  /** Channel information dictionary  */ 
  @property (nonatomic, retain) NSDictionary * 
<b>channelInfo</b>; 
    
  /** CMS Metadata information dictionary  */ 
  @property (nonatomic, retain) NSDictionary * 
<b>metadataInfo</b>; 
    
  @end
  ```

* **PTNielsenTracker** Provides Nielsen tracking capability for  playable streams. Includes methods to enable and disable the tracker and to expose data relevant to the Nielsen integration 

  ```
  @interface  
<b>PTNielsenTracker</b> : NSObject 
    
  /** Initializes the tracker instance with an app information dictionary  */ 
  - (id) 
<b>initWithAppInfo</b>:(NSDictionary *)info; 
    
  /** * Begins tracking with the given media player instance  */ 
  - (void) 
<b>attachMediaPlayer</b>:(PTMediaPlayer *)mediaPlayer; 
    
  /** 
   * Load metadata from content or ad. 
   * @param metadata A dictionary of metadata that needs to be provided for tracking 
   */ 
  - (void) 
<b>loadMetadata</b>:(NSDictionary *)metadata; 
    
  /** 
   * Get the URL of the web page that is used for giving user a chance to 
   * opt out from the Nielsen measurements. Returns nil if there is no valid  
   * Nielsen tracker instance. 
   */ 
  - (NSString *) 
<b>optOutURLString</b>; 
    
  /** 
   * Disable metering for the app due to user opt out. This method does nothing if there is  
   * no valid Nielsen tracker instance. 
   * Returns YES if the opt out is handled and NO otherwise. 
   * @param optOut string to disable or enable 
   */ 
  - (BOOL) 
<b>userOptOut</b>:(NSString *)optOut; 
    
  /** Retrieve Nielsen ID for user opt-in or opt-out purpose.  
   * Returns nil if there is no valid Nielsen tracker instance */ 
  - (NSString *) 
<b>getNielsenId</b>; 
    
  @end
  ```

* **Error logs** The  provides the following logs related to the Nielsen Anlaytics module: 
    * Basic debug logs
    * A warning log, to notify you whether you have an incompatible version of the Nielsen library. If the library version used by your application does not match the version required by the Nielsen integration module, then the  generates out a warning log.


