---
title: TVSDK Conversion - 1.3 to 2.0 For JavaScript
seo-title: TVSDK Conversion - 1.3 to 2.0 For JavaScript
description: Many method signatures and API element names have changed for 2.0. Review these tables to see all API change details.
seo-description: Many method signatures and API element names have changed for 2.0. Review these tables to see all API change details.
uuid: d2d1742d-c90c-43f5-94fc-8c4a57cb8ed4
contentOwner: asgupta
products: SG_PRIMETIME
topic-tags: migration
discoiquuid: c732f54d-116c-43f3-bec4-5e71af208426
index: y
internal: n
snippet: y
---

# TVSDK Conversion - 1.3 to 2.0 For JavaScript {#tvsdk-conversion-to-for-javascript}

Many method signatures and API element names have changed for 2.0. Review these tables to see all API change details.

## Implement callback functions in JavaScript {#implement-callback-functions-in-javascript}

Comments in method documentation suggest the signature for callbacks that you need to implement.

For JavaScript, the API syntax is based on Web ID. For a TVSDK interface, the method names are called *methodName*(). For methods to be implemented by your application, a read/write attribute called *methodName*CallbackFunc is added to the interface and your application should set it to point to a function that implements the method. For example:

```shell
// An app implementable interface
interface ContentFactory
{
    /*
     * AdPolicySelector retrieveAdPolicySelector(MediaPlayerItem item);
     */
    attribute Object retrieveAdPolicySelectorCallbackFunc;
 
    /*
     * ContentResolverList retrieveResolvers(MediaPlayerItem item);
     */
    attribute Object retrieveResolversCallbackFunc;
 
    /*
     * OpportunityGeneratorList retrieveGenerators(MediaPlayerItem item);
     */
    attribute Object retrieveGeneratorsCallbackFunc;
};

// this is how to implement it
var factory = new AdobePSDK.ContentFactory();
factory.retrieveAdPolicySelectorCallbackFunc = function(item)
{
    // return your adPolicySelector according to the item
    return adPolicySelector;
}
 
mediaPlayerItemConfig = new AdobePSDK.MediaPlayerItemConfig ();
playerConfig.adFactory = factory;
// Use this config to load new MediaResource
```

## Advertising workflow API element changes for 2.0 {#advertising-workflow-api-element-changes-for}

These tables compare the advertising workflow API elements for the JavaScript TVSDK between versions 1.3 and 2.0.

Tables in this topic:

* TimedMetadata
* AdSignalingMode
* AdvertisingMetadata
* CustomRangeMetadata
* ReplaceTimeRange
* Placement
* Opportunity
* Reservation
* Timeline / TimelineItem / TimelineMarker
* AdBreak
* Ad / AdAsset / AdClick / AdList / AdAssetList / AdBannerAsset
* AdBreakTimelineItem / AdTimelineItem
* AdBreakPolicy / AdBreakWatchedPolicy / AdPolicy / AdPolicyMode / AdPolicyInfo / AdPolicySelector
* TimelineOperation
* AdBreakPlacement
* AuditudeSettings

### TimedMetadata {#timedmetadata}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>TimedMetadata</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p> interface TimedMetadata {<br /> const unsigned short METADATA_TYPE_TAG = 0 ; <br /> const unsigned short METADATA_TYPE_ID3 = 1 ; <br /> readonly attribute unsigned short type; <br /> readonly attribute long time;<br /> readonly attribute DomString id;<br /> readonly attribute DomString name;<br /> readonly attribute DomString content; <br /> readonly attribute Object metadata;<br /> }; </p> </td> 
   <td valign="top" width="42.37288135593219%"><p>interface TimedMetadata {<br /> const unsigned short METADATA_TYPE_TAG = 0 ;<br /> const unsigned short METADATA_TYPE_ID3 = 1 ;<br /> readonly attribute unsigned short metadataType;<br /> readonly attribute long time;<br /> readonly attribute long id;<br /> readonly attribute DomString name;<br /> <br /> readonly attribute Object metadata;<br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>TimedMetadataList</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%">(No change for 2.0)</td> 
   <td valign="top" width="42.37288135593219%"><p>interface TimedMetadataList {<br /> readonly attribute unsigned long length;<br /> getter TimedMetadata(unsigned long index);<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### AdSignalingMode {#adsignalingmode}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdSignalingMode</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>Interface AdSignalingMode { <br /> const unsigned short MODE_DEFAULT, <br /> const unsigned short MODE_MANIFEST_CUES , <br /> const unsigned short MODE_SERVER_MAP , <br /> const unsigned short MODE_CUSTOM_RANGES <br /> };</p> </td> 
   <td valign="top" width="42.37288135593219%">This replaces MetadataKeys::MANIFEST_CUES key.</td> 
  </tr> 
 </tbody> 
</table>

### AdvertisingMetadata {#advertisingmetadata}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdvertisingMetadata</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>Interface AdvertisingMetadata { <br /> attribute AdSignalingMode mode; <br /> attribute AdBreakWatchedPolicy adBreakAsWatched; <br /> attribute boolean livePreroll; <br /> attribute boolean delayAdLoading ; <br /> };</p> </td> 
   <td valign="top" width="42.37288135593219%">This functionality was provided by<p>MetadataKeys::ADVERTISING_METADATA</p> key.</td> 
  </tr> 
 </tbody> 
</table>

### CustomRangeMetadata {#customrangemetadata}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>CustomRangeMetadata</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>Interface CustomRangeMetadata { <br /> const unsigned short TYPE_MARK_RANGE; <br /> const unsigned short TYPE_DELETE_RANGE; <br /> const unsigned short TYPE_REPLACE_RANGE; <br /> attribute unsigned short type; <br /> attribute boolean adjustSeekPosition; <br /> attribute TimeRangeList timeRangeList; <br /> };</p> </td> 
   <td valign="top" width="42.37288135593219%">(New for 2.0)</td> 
  </tr> 
 </tbody> 
</table>

### ReplaceTimeRange {#replacetimerange}

<table border="1" cellpadding="4" cellspacing="0"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
 </tbody> 
 <tbody> 
  <tr> 
   <td colspan="2" valign="top"><strong>ReplaceTimeRange</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>interface ReplaceTimeRange { <br /> attribute unsigned long begin; <br /> readonly attribute unsigned long end; <br /> attribute unsigned long duration; <br /> attribute unsigned long replaceDuration; <br /> };</p> </td> 
   <td valign="top" width="42.37288135593219%">(New for 2.0)</td> 
  </tr> 
 </tbody> 
</table>

### Placement {#placement}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>Placement</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>Interface Placement { <br /> const unsigned short TYPE_MID_ROLL; <br /> const unsigned short TYPE_PRE_ROLL; <br /> const unsigned short TYPE_POST_ROLL; <br /> const unsigned short TYPE_SERVER_MAP; <br /> const unsigned short TYPE_CUSTOM_RANGE;<br /> readonly attribute unsigned short type; <br /> readonly attribute long time; <br /> readonly attribute long duration; <br /> const unsigned short MODE_DEFAULT; <br /> const unsigned short MODE_INSERT; <br /> const unsigned short MODE_REPLACE; <br /> const unsigned short MODE_DELETE; <br /> const unsigned short MODE_MARK; <br /> const unsigned short MODE_FREE_REPLACE; <br /> readonly attribute unsigned short mode; <br /> readonly attribute TimeRange range; <br /> };</p> </td> 
   <td valign="top" width="42.37288135593219%">(New for 2.0)</td> 
  </tr> 
 </tbody> 
</table>

### Opportunity {#opportunity}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>Opportunity</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>interface Opportunity { <br /> readonly attribute DomString id; <br /> readonly attribute Placement placement; <br /> readonly attribute Object settings; <br /> readonly attribute Object customParameters; <br /> }; </p> </td> 
   <td valign="top" width="42.37288135593219%">(New for 2.0)</td> 
  </tr> 
 </tbody> 
</table>

### Reservation {#reservation}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>Reservation</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>interface Reservation { <br /> readonly attribute TimeRange range; <br /> readonly attribute long hold; <br /> }; </p> </td> 
   <td valign="top" width="42.37288135593219%"> (New for 2.0)</td> 
  </tr> 
 </tbody> 
</table>

### Timeline / TimelineItem / TimelineMarker {#timeline-timelineitem-timelinemarker}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>Timeline</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>interface Timeline <br /> { readonly attribute TimelineMarkerList timelineMarkers; <br /> readonly attribute TimelineItemList timelineItems; <br /> double convertToLocalTime( double time); <br /> double convertToVirtualTime( double time); <br /> };</p> </td> 
   <td valign="top" width="42.37288135593219%"><p>interface Timeline {<br /> readonly attribute TimelineMarkerList timelineMarkers;<br /> <br /> <br /> <br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>TimelineItem</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p> interface TimelineItem :<br /> TimelineMarker {<br /> readonly attribute long id; <br /> readonly attribute TimeRange virtualRange; <br /> readonly attribute TimeRange localRange; <br /> readonly attribute boolean watched; <br /> readonly attribute boolean temporary; <br /> }; </p> </td> 
   <td valign="top" width="42.37288135593219%">(New for 2.0)</td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>TimelineMarker</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%">(No change for 2.0)</td> 
   <td valign="top" width="42.37288135593219%"><p>interface TimelineMarker {<br /> readonly attribute double time;<br /> readonly attribute double duration;<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### AdBreak {#adbreak}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdBreak</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>interface AdBreak {<br /> <br /> <br /> <br /> readonly attribute double duration;<br /> readonly attribute AdList ads;<br /> <br /> <br /> readonly attribute AdInsertionType insertionType;<br /> }; </p> </td> 
   <td valign="top" width="42.37288135593219%"><p>interface AdBreak {<br /> readonly attribute double time;<br /> readonly attribute double replaceDuration;<br /> <br /> readonly attribute double duration;<br /> readonly attribute AdList adList;<br /> <br /> readonly attribute DomString data;<br /> <br /> }; </p> </td> 
  </tr> 
 </tbody> 
</table>

### Ad / AdAsset / AdClick / AdList / AdAssetList / AdBannerAsset {#ad-adasset-adclick-adlist-adassetlist-adbannerasset}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>Ad</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p> interface Ad {<br /> readonly attribute AdAsset primaryAsset;<br /> readonly attribute AdAssetList companionAssets;<br /> <br /> readonly attribute double duration;<br /> readonly attribute DomString id;<br /> const unsigned short ADTYPE_LINEAR = 0 ;<br /> const unsigned short ADTYPE_NONLINEAR = 1 ;<br /> <br /> readonly attribute unsigned short adType;<br /> readonly attribute AdInsertionType adInsertionType; <br /> <br /> readonly attribute boolean clickable; <br /> readonly attribute boolean isCustomAdMarker;<br /> }; </p> </td> 
   <td valign="top" width="42.37288135593219%"><p>interface Ad {<br /> readonly attribute AdAsset primaryAsset;<br /> readonly attribute AdAssetList companionAssets;<br /> <br /> readonly attribute double duration;<br /> readonly attribute DomString id;<br /> const unsigned short ADTYPE_LINEAR = 0 ;<br /> const unsigned short ADTYPE_NONLINEAR = 1 ;<br /> <br /> readonly attribute unsigned short type;<br /> readonly attribute AdInsertionType insertionType; <br /> readonly attribute Object tracker;<br /> <br /> <br /> }; </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdAsset</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%">(No change for 2.0)</td> 
   <td valign="top" width="42.37288135593219%"><p>interface AdAsset {<br /> readonly attribute DomString id;<br /> readonly attribute double duration;<br /> readonly attribute MediaResource resource;<br /> readonly attribute AdClick adClick;<br /> readonly attribute Object metadata;<br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><p><strong>AdClick</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%">(No change for 2.0)</td> 
   <td valign="top" width="42.37288135593219%"><p>interface AdClick {<br /> readonly attribute DomString id;<br /> readonly attribute DomString title;<br /> readonly attribute DomString url;<br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdList</strong> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%">(No change for 2.0)</td> 
   <td valign="top" width="42.37288135593219%"><p>interface AdList {<br /> readonly attribute unsigned long length;<br /> getter Ad(unsigned long index);<br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdAssetList</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%">(No change for 2.0)</td> 
   <td valign="top" width="42.37288135593219%"><p>interface AdAssetList {<br /> readonly attribute unsigned long length;<br /> getter AdAsset(unsigned long index);<br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdBannerAsset</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>interface AdBannerAsset : AdAsset<br /> {<br /> readonly attribute int width;<br /> readonly attribute int height;<br /> readonly attribute DomString staticUrl;<br /> readonly attribute DomString height;<br /> readonly attribute DomString width;<br /> };</p> </td> 
   <td valign="top" width="42.37288135593219%"> New in 2.0</td> 
  </tr> 
 </tbody> 
</table>

### AdBreakTimelineItem / AdTimelineItem {#adbreaktimelineitem-adtimelineitem}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><p><strong>AdBreakTimelineItem</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p> interface AdBreakTimelineItem : TimelineItem { <br /> readonly attribute AdBreak adBreak; <br /> readonly attribute AdTimelineItemList items; <br /> }; </p> </td> 
   <td valign="top" width="42.37288135593219%"> (New for 2.0)</td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><p><strong>AdTimelineItem</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>interface AdTimelineItem : TimelineItem { <br /> readonly attribute AdBreak adBreak; <br /> readonly attribute Ad ad; <br /> }; </p> </td> 
   <td valign="top" width="42.37288135593219%"> (New for 2.0)</td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdBreakTimelineItemList</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>interface AdBreakTimelineItemList { <br /> readonly attribute unsigned long length; <br /> getter AdBreakTimelineItem (unsigned lo ng index); <br /> };</p> </td> 
   <td valign="top" width="42.37288135593219%"> (New for 2.0)</td> 
  </tr> 
 </tbody> 
</table>

### AdBreakPolicy / AdBreakWatchedPolicy / AdPolicy / AdPolicyMode / AdPolicyInfo / AdPolicySelector {#adbreakpolicy-adbreakwatchedpolicy-adpolicy-adpolicymode-adpolicyinfo-adpolicyselector}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdBreakPolicy</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="50.495049504950494%"><p>interface AdBreakPolicy {<br /> readonly attribute short AD_BREAK_POLICY_SKIP;<br /> readonly attribute short AD_BREAK_POLICY_PLAY;<br /> readonly attribute short AD_BREAK_POLICY_REMOVE;<br /> readonly attribute short AD_BREAK_POLICY_REMOVE_AFTER_PLAY;<br /> };</p> </td> 
   <td valign="top" width="49.504950495049506%"><p> interface AdPolicyConstants {<br /> readonly attribute short AD_BREAK_POLICY_SKIP;<br /> readonly attribute short AD_BREAK_POLICY_PLAY;<br /> readonly attribute short AD_BREAK_POLICY_REMOVE;<br /> readonly attribute short AD_BREAK_POLICY_REMOVE_AFTER_PLAY;<br /> ...</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdBreakWatchedPolicy</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="50.495049504950494%"><p> interface AdBreakWatchedPolicy {<br /> readonly attribute short AD_BREAK_AS_WATCHED_ON_BEGIN;<br /> readonly attribute short AD_BREAK_AS_WATCHED_ON_END;<br /> readonly attribute short AD_BREAK_AS_WATCHED_NEVER;<br /> }; </p> </td> 
   <td valign="top" width="49.504950495049506%"><p> ...<br /> readonly attribute short AD_BREAK_AS_WATCHED_ON_BEGIN;<br /> readonly attribute short AD_BREAK_AS_WATCHED_ON_END;<br /> readonly attribute short AD_BREAK_AS_WATCHED_NEVER;<br /> ...</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdPolicy</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="50.495049504950494%"><p>interface AdPolicy {<br /> readonly attribute short AD_POLICY_PLAY;<br /> readonly attribute short AD_POLICY_PLAY_FROM_AD_BEGIN;<br /> readonly attribute short AD_POLICY_PLAY_FROM_AD_BREAK_BEGIN; readonly attribute short AD_POLICY_SKIP_TO_NEXT_AD_IN_BREAK;<br /> <br /> readonly attribute short AD_POLICY_SKIP_AD_BREAK;<br /> };</p> </td> 
   <td valign="top" width="49.504950495049506%"><p> ... <br /> readonly attribute short AD_POLICY_PLAY;<br /> readonly attribute short AD_POLICY_PLAY_FROM_AD_BEGIN;<br /> readonly attribute short AD_POLICY_PLAY_FROM_AD_BREAK_BEGIN;<br /> readonly attribute short AD_POLICY_SKIP_TO_NEXT_AD_IN_BREAK;<br /> readonly attribute short AD_POLICY_SKIP_AD_BREAK;<br /> ...</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdPolicyMode</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="50.495049504950494%"><p>interface AdPolicyMode {<br /> readonly attribute short AD_POLICY_MODE_PLAY;<br /> readonly attribute short AD_POLICY_MODE_SEEK;<br /> readonly attribute short AD_POLICY_MODE_TRICKPLAY;<br /> };</p> </td> 
   <td valign="top" width="49.504950495049506%"><p> ...<br /> readonly attribute short AD_POLICY_MODE_PLAY;<br /> readonly attribute short AD_POLICY_MODE_SEEK;<br /> readonly attribute short AD_POLICY_MODE_TRICKPLAY;<br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdPolicyInfo</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="50.495049504950494%"><p>interface AdPolicyInfo {<br /> readonly attribute AdBreakTimelineItemList <br /> adBreakTimelineItems;<br /> readonly attribute AdTimelineItem adTimelineItem;<br /> readonly attribute double currentTime;<br /> readonly attribute double seekToTime;<br /> readonly attribute double rate;<br /> readonly attribute short mode; //AdPolicyMode<br /> };</p> </td> 
   <td valign="top" width="49.504950495049506%"><p>interface AdPolicyInfo {<br /> readonly attribute AdBreakPlacementList <br /> adBreakPlacements;<br /> readonly attribute Ad ad;<br /> readonly attribute double currentTime;<br /> readonly attribute double seekToTime;<br /> readonly attribute double rate;<br /> readonly attribute short mode; //AdPolicyMode<br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdPolicySelector</strong></td> 
  </tr> 
  <tr> 
   <td valign="top" width="50.495049504950494%"><p>interface AdPolicySelector {<br /> /**<br /> * AdbreakPolicy selectPolicyForAdBreak(<br /> * AdPolicyInfo adPolicyInfo);<br /> */<br /> attribute Object selectPolicyForAdBreakCallbackFunc;<br /> /**<br /> * AdBreakTimelineItemList selectAdBreaksToPlay(<br /> * AdPolicyInfo adPolicyInfo);<br /> */<br /> attribute Object selectAdBreaksToPlayCallbackFunc;<br /> /**<br /> * AdPolicy selectPolicyForSeekIntoAd(AdPolicyInfo adPolicyInfo);<br /> */<br /> attribute Object selectPolicyForSeekIntoAdCallbackFunc; <br /> /**<br /> * AdBreakWatchedPolicy selectWatchedPolicyForAdBreak(<br /> * AdPolicyInfo adPolicyInfo);<br /> */<br /> attribute Object selectWatchedPolicyForAdBreakCallbackFunc;<br /> };</p> </td> 
   <td valign="top" width="49.504950495049506%"><p>interface AdPolicySelector {<br /> /**<br /> * AdbreakPolicy selectPolicyForAdBreak(<br /> * AdPolicyInfo adPolicyInfo);<br /> */<br /> attribute Object selectPolicyForAdBreakFuncCallback;<br /> /**<br /> * AdBreakPlacementList selectAdBreaksToPlay(<br /> * AdPolicyInfo adPolicyInfo);<br /> */<br /> attribute Object selectAdBreaksToPlayCallback;<br /> /**<br /> * AdPolicy selectPolicyForSeekIntoAd(AdPolicyInfo adPolicyInfo);<br /> */<br /> attribute Object selectPolicyForSeekIntoAdCallback; <br /> /**<br /> * AdBreakAsWatched selectWatchedPolicyForAdBreak(<br /> * AdPolicyInfo adPolicyInfo);<br /> */<br /> attribute Object selectWatchedPolicyForAdBreakCallback;<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### TimelineOperation {#timelineoperation}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>TimelineOperation</strong> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>interface TimelineOperation { <br /> readonly attribute Placement placement ; <br /> };</p> </td> 
   <td valign="top" width="42.37288135593219%"> (New for 2.0)</td> 
  </tr> 
 </tbody> 
</table>

### AdBreakPlacement {#adbreakplacement}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AdBreakPlacement</strong> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>interface AdBreakPlacement : TimelineOperation {<br /> readonly attribute AdBreak adBreak;<br /> readonly attribute Placement placement; // From TimelineOperation<br /> readonly attribute double time;<br /> readonly attribute double duration;<br /> };</p> </td> 
   <td valign="top" width="42.37288135593219%"><p>interface AdBreakPlacement {<br /> readonly attribute AdBreak adBreak;<br /> readonly attribute Placement placement;<br /> readonly attribute double time;<br /> readonly attribute double duration;<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### AuditudeSettings {#auditudesettings}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 API</th> 
   <th>1.3 API</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AuditudeSettings</strong> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="57.6271186440678%"><p>interface AuditudeSettings : AdvertisingMetadata { <br /> attribute DomString zoneId; <br /> attribute DomString mediaId; <br /> attribute DomString defaultMediaId ; <br /> attribute DomString domain ; <br /> attribute Object targettingInfo ; <br /> attribute Object customParameters ; <br /> attribute Boolean creativePackaingEnabled ;<br /> attribute Boolean showStaticBanners ;<br /> };</p> </td> 
   <td valign="top" width="42.37288135593219%">Functionality was provided byMetadataKeys::AUDITUDE_METADATA_KEY key.</td> 
  </tr> 
 </tbody> 
</table>

## Customization API element changes for 2.0 {#customization-api-element-changes-for}

These tables compare the customization API elements for the JavaScript TVSDK between versions 1.3 and 2.0.

Tables in this topic:

* MediaPlayerItemConfig
* ContentFactory
* NetworkConfiguration

### MediaPlayerItemConfig {#mediaplayeritemconfig}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>MediaPlayerItemConfig</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface MediaPlayerItemConfig {<br /> attribute ContentFactory adFactory;<br /> attribute StringList subscribeTags;<br /> <br /> attribute StringList adTags;<br /> <br /> <br /> attribute AdSignalingMode adSignalingMode;<br /> attribute CustomRangeMetadata customRangeMetadata;<br /> attribute NetworkConfiguration networkConfiguration;<br /> attribute AdvertisingMetadata advertisingMetadata;<br /> attribute Boolean useHardwareDecoder;<br /> };</p> </td> 
   <td valign="top"><p>interface MediaPlayerConfig {<br /> <br /> <br /> <br /> attribute StringList adTags;<br /> attribute StringList subscribedTags;<br /> attribute MediaPlayerClientFactory clientFactory;<br /> <br /> <br /> <br /> <br /> <br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### ContentFactory {#contentfactory}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>ContentFactory</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface ContentFactory {<br /> /*<br /> * AdPolicySelector retrieveAdPolicySelector(<br /> * MediaPlayerItem item);<br /> */<br /> attribute Object retrieveAdPolicySelectorCallbackFunc;<br /> };</p> </td> 
   <td valign="top"><p>interface MediaPlayerClientFactory {<br /> /*<br /> * AdPolicySelector retrieveAdPolicySelector(<br /> * MediaPlayerItem item);<br /> */<br /> attribute Object retrieveAdPolicySelectorFunc;<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### NetworkConfiguration {#networkconfiguration}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>NetworkConfiguration</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface NetworkConfiguration<br /> {<br /> attribute boolean forceNativeNetworking;<br /> attribute boolean useRedirectedUrl;<br /> attribute Object cookieHeader;<br /> attribute boolean readSetCookieHeader;<br /> attribute int masterUpdateInterval; <br /> attribute boolean useCookieHeaderForAllRequests;<br /> attribute int readLimit;<br /> };</p> </td> 
   <td valign="top">In 1.3, some of this functionality was provided by MetadataKeys</td> 
  </tr> 
 </tbody> 
</table>

## DRM API element changes for 2.0 {#drm-api-element-changes-for}

These tables compare the DRM API elements for the JavaScript TVSDK between versions 1.3 and 2.0.

Tables in this topic:

* DRM Workflow Initialization
* DRMAcquireLicenseSettings / DRMAuthenticationMethod
* DRMMetadata
* DRMPlaybackTimeWindow
* DRMLicense
* DRMLicenseDomain
* DRMPolicy
* DRMManager

### DRM Workflow Initialization {#drm-workflow-initialization}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td valign="top">Application needs to call AdobePSDK.initiateDRMWorkflow to initiate the DRM workflow. Without this call, DRM videos will not play.<p>interface AdobePSDK<br /> {<br /> void initiateDRMWorkFlow(<br /> DomString appStoratePath, <br /> DomString publisherId, <br /> DomString appId, <br /> DomString appVersion, <br /> boolean privacyModeOn);<br /> };</p> </td> 
   <td valign="top">Initialization was done internally and no explicit call was required.</td> 
  </tr> 
 </tbody> 
</table>

### DRMAcquireLicenseSettings/DRMAuthenticationMethod {#drmacquirelicensesettings-drmauthenticationmethod}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMAcquireLicenseSettings</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0.</td> 
   <td valign="top"><p>enum DRMAcquireLicenseSettings {<br /> const unsigned int FORCE_REFRESH = 0;<br /> const unsigned int LOCAL_ONLY = 1;<br /> const unsigned int ALLOW_SERVER = 2;<br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMAuthenticationMethod</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0.</td> 
   <td valign="top"><p>enum DRMAuthenticationMethod {<br /> const unsigned int UNKNOWN = 0;<br /> const unsigned int ANONYMOUS = 1;<br /> const unsigned int USERNAME_AND_PASSWORD = 2;<br /> }</p> </td> 
  </tr> 
 </tbody> 
</table>

### DRMMetadata {#drmmetadata}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMMetadata</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0.</td> 
   <td valign="top"><p>interface DRMMetadata<br /> {<br /> readonly attribute DomString serverUrl;<br /> readonly attribute DomString licenseId;<br /> readonly attribute DRMPolicyArray policies; <br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### DRMPlaybackTimeWindow {#drmplaybacktimewindow}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMPlaybackTimeWindow</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface DRMPlaybackTimeWindow {<br /> readonly attribute int playbackPeriodInSeconds;<br /> readonly attribute long playbackStartDate;<br /> readonly attribute long playbackEndDate;<br /> };</p> </td> 
   <td valign="top"><p>interface DRMPlaybackTimeWindow {<br /> readonly attribute int periodInSeconds;<br /> readonly attribute int startDate;<br /> readonly attribute int endDate;<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### DRMLicense {#drmlicense}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMLicense</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0.</td> 
   <td valign="top"><p>interface DRMLicense {<br /> readonly attribute Uint8Array bytes;<br /> readonly attribute Date licenseStartDate;<br /> readonly attribute Date licenseEndDate;<br /> readonly attribute Date offlineStorageStartDate;<br /> readonly attribute Date offlineStorageEndDate; <br /> readonly attribute DomString serverUrl;<br /> readonly attribute DomString licenseID;<br /> readonly attribute DomString policyID;<br /> readonly attribute DRMPlaybackTimeWindow playbackTimeWindow;<br /> readonly attribute Object customProperties;<br /> }; </p> </td> 
  </tr> 
 </tbody> 
</table>

### DRMLicenseDomain {#drmlicensedomain}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMLicenseDomain</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface DRMLicenseDomain {<br /> readonly attribute DomString authenticationDomain;<br /> readonly attribute DRMAuthenticationMethod authenticationMethod; <br /> readonly attribute DomString serverUrl;<br /> };</p> </td> 
   <td valign="top"><p>interface DRMLicenseDomain {<br /> readonly attribute DomString authDomain;<br /> readonly attribute DRMAuthenticationMethod authMethod; <br /> readonly attribute DomString serverURL;<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### DRMPolicy {#drmpolicy}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMPolicy</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface DRMPolicy<br /> {<br /> readonly attribute DomString authenticationDomain;<br /> readonly attribute DRMAuthenticationMethod authenticationMethod;<br /> <br /> readonly attribute DomString displayName;<br /> readonly attribute DRMLicenseDomain licenseDomain;<br /> };</p> </td> 
   <td valign="top"><p>interface DRMPolicy<br /> {<br /> readonly attribute DomString authDomain;<br /> readonly attribute DRMAuthenticationMethod authMethod;<br /> readonly attribute DomString dispName;<br /> readonly attribute DRMLicenseDomain licenseDomain;<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### DRMManager {#drmmanager}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMManager</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface DRMManager : EventTarget {<br /> void acquireLicense(DRMMetadata metadata, <br /> DRMAcquireLicenseSettings setting, <br /> DRMAquireLicenseListener listener);<br /> void acquirePreviewLicense(DRMMetadata metadata, <br /> DRMAquireLicenseListener listener);<br /> void authenticate(DRMMetadata metadata, <br /> DomString url,<br /> DomString &amp;authenticationDomain, <br /> DomString user, <br /> DomString password, <br /> DRMAuthenticateListener listener);<br /> <br /> DRMMetadata createMetadataFromBytes(<br /> Uint8Array array, DRMErrorListener listener);<br /> void initialize(DRMOperationCompleteListener listener);<br /> attribute long maxOperationTime;<br /> <br /> void joinLicenseDomain(<br /> DRMLicenseDomain licenseDomain, <br /> boolean forceRefresh, <br /> DRMOperationCompleteListener listener);<br /> void leaveLicenseDomain(<br /> DRMLicenseDomain licenseDomain, <br /> DRMOperationCompleteListener listener);<br /> <br /> void resetDRM(DRMOperationCompleteListener listener);<br /> void returnLicense(DomString serverURL, <br /> DomString licenseID, <br /> DomString policyID, <br /> boolean commitImmediately,<br /> DRMReturnLicenseListener listener);<br /> void setAuthenticationToken(<br /> DRMMetadata metadata, <br /> DomString authenticationDomain, <br /> Uint8Array token, <br /> DRMOperationCompleteListener listener);<br /> void storeLicenseBytes(Uint8Array licenseBytes, <br /> DRMOperationCompleteListener listener);<br /> };</p> </td> 
   <td valign="top"><p>interface DRMManager : EventTarget {<br /> void acquireLicense(DRMMetadata metadata, <br /> DRMAcquireLicenseSettings setting, <br /> EventContext eventContext);<br /> void acquirePreviewLicense(DRMMetadata metadata, <br /> EventContext eventContext);<br /> void authenticate(DRMMetadata metadata, <br /> DomString url,<br /> DomString &amp;authenticationDomain, <br /> DomString user, <br /> DomString password, <br /> EventContext eventContext);<br /> <br /> DRMMetadata createMetadataFromBytes(<br /> Uint8Array array, EventContext eventContext);<br /> void initialize(EventContext eventContext);<br /> attribute long maxOperationTime;<br /> <br /> void joinLicenseDomain(<br /> DRMLicenseDomain licenseDomain, <br /> boolean forceRefresh, <br /> EventContext eventContext);<br /> void leaveLicenseDomain(<br /> DRMLicenseDomain licenseDomain, <br /> EventContext eventContext);<br /> <br /> void resetDRM(EventContext eventContext);<br /> void returnLicense(DomString serverURL, <br /> DomString licenseID,<br /> DomString policyID, <br /> boolean commitImmediately,<br /> EventContext eventContext);<br /> void setAuthenticationToken(<br /> DRMMetadata metadata, <br /> DomString authenticationDomain, <br /> Uint8Array token, <br /> EventContext eventContext);<br /> void storeLicenseBytes(Uint8Array licenseBytes, <br /> EventContext eventContext);<br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMErrorListener</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>class DRMErrorListener : <br /> public psdkutils::PSDKInterfaceWithUserData {<br /> public:<br /> virtual void onDRMError(uint32_t major, <br /> uint32_t minor, <br /> const psdkutils:: PSDKString&amp; errorString, <br /> const psdkutils::PSDKString&amp; errorServerUrl) = 0;<br /> <br /> protected:<br /> virtual ~DRMErrorListener() {}<br /> }</p> </td> 
   <td valign="top">Event / Interface / Description 
    <ul> 
     <li>kEventDRMOperationError<p>/ DRMOperationErrorEvent</p> <p>When an error occurs during one of the asynchronous methods of DRMManger.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMOperationCompleteListener</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>class DRMOperationCompleteListener : <br /> public DRMErrorListener {<br /> public:<br /> virtual void onDRMOperationComplete() = 0;<br /> <br /> protected:<br /> virtual ~DRMOperationCompleteListener() {}<br /> };</p> </td> 
   <td valign="top">Event / Interface / Description 
    <ul> 
     <li>kEventDRMInitializationComplete<p>/ PSDKEvent</p> <p>When Initialization of DRM is complete.</p> </li> 
     <li>kEventDRMJoinLicenseDomainComplete<p>/ PSDKEvent</p> <p>When joinLicenseDomain() action completes successfully.</p> </li> 
     <li>kEventDRMLeaveLicenseDomainComplete<p>/ PSDKEvent</p> <p>When leaveLicenseDomain() action completes successfully.</p> </li> 
     <li>kEventDRMResetCompletePSDKEvent<p>/ PSDKEvent</p> <p>When resetDRM() action completes successfully.</p> </li> 
     <li>kEventDRMAuthenticationTokenSet<p>/ PSDKEvent</p> <p>When setAuthenticationTokenSet() action completes successfully.</p> </li> 
     <li>kEventDRMLicenseStored<p>/ PSDKEvent</p> <p>When storeLicenseBytes() action completes successfully.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMAuthenticateListener</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>class DRMAuthenticateListener : <br /> public DRMErrorListener {<br /> public:<br /> virtual void onAuthenticationComplete(<br /> psdkutils::PSDKImmutableByteArray* <br /> authenticationToken) = 0;<br /> <br /> protected:<br /> virtual ~DRMAuthenticateListener() {}<br /> }</p> </td> 
   <td valign="top">Event / Interface / Description 
    <ul> 
     <li>kEventDRMAuthenticationComplete<p>/ DRMAuthenticationCompleteEvent</p> <p>When DRMManager::authenticate method call is successful.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMAquireLicenseListener</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>class DRMAquireLicenseListener: <br /> public DRMErrorListener {<br /> public:<br /> virtual void onLicenseAcquired(const DRMLicense*) = 0;<br /> <br /> protected:<br /> virtual ~DRMAquireLicenseListener() {}<br /> };</p> </td> 
   <td valign="top">Event / Interface / Description 
    <ul> 
     <li>kEventDRMPreviewLicenseAcquired<p>/ DRMLicenseAcquiredEvent</p> <p>When DRMManager::acquirePreviewLicense method call is successful.</p> </li> 
     <li>kEventDRMLicenseAcquired<p>/ DRMLicenseAcquiredEvent</p> <p>When DRMManager::acquireLicense method call is successful.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMReturnLicenseListener</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>class DRMReturnLicenseListener: <br /> public DRMErrorListener {<br /> public:<br /> virtual void onLicenseReturnComplete(uint32_t numReturned ) = 0;<br /> <br /> protected:<br /> virtual ~DRMReturnLicenseListener() {}<br /> };</p> </td> 
   <td valign="top">Event / Interface / Description 
    <ul> 
     <li>kEventDRMLicenseReturnComplete<p>/ DRMLicenseReturnCompleteEvent</p> <p>When DRMManager::returnLicense method call is successful.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Generic playback API element changes for 2.0 {#generic-playback-api-element-changes-for}

These tables compare the generic playback API elements between the JavaScript TVSDK 1.3 and 2.0.

Tables in this topic:

* MediaResource
* MediaPlayer
* ABRControlParameters
* BufferControlParameters
* TextFormat
* MediaPlayerItemLoader

### MediaResource {#mediaresource}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>MediaResource</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface MediaResource {<br /> attribute DomString url; <br /> attribute unsigned short type;<br /> attribute Object metadata;<br /> const unsigned short TYPE_HLS;<br /> const unsigned short TYPE_HDS;<br /> const unsigned short TYPE_DASH;<br /> const unsigned short TYPE_CUSTOM;<br /> const unsigned short TYPE_UNKNOWN;<br /> };</p> </td> 
   <td valign="top"><p>interface MediaResource {<br /> attribute DomString url;<br /> attribute DomString type;<br /> attribute Object metadata;<br /> <br /> <br /> <br /> <br /> <br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### MediaPlayer {#mediaplayer}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>MediaPlayer</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface MediaPlayer : EventTarget<br /> {<br /> void prepareToPlay( double position);<br /> void play();<br /> void pause();<br /> void seek( double position);<br /> void seekToLocal( double position);<br /> void reset();<br /> void release();<br /> void replaceCurrentItem(MediaPlayerItem item);<br /> void replaceCurrentResource(MediaResource rsource, <br /> MediaPlayerItemConfig config); <br /> void suspend();<br /> void restore();<br /> void notifyClick();<br /> <br /> readonly attribute TimeRange playbackRange;<br /> readonly attribute TimeRange seekableRange;<br /> readonly attribute double currentTime;<br /> readonly attribute double localTime;<br /> readonly attribute TimeRange bufferedRange;<br /> readonly attribute DRMManager drmManager;<br /> readonly attribute MediaPlayerItem currentItem;<br /> <br /> // PlayerStatus<br /> <br /> <br /> const unsigned short PLAYER_STATUS_INITIALIZED;<br /> const unsigned short PLAYER_STATUS_PREPARING;<br /> const unsigned short PLAYER_STATUS_PREPARED;<br /> const unsigned short PLAYER_STATUS_PLAYING;<br /> const unsigned short PLAYER_STATUS_PAUSED;<br /> const unsigned short PLAYER_STATUS_SEEKING;<br /> const unsigned short PLAYER_STATUS_COMPLETE;<br /> const unsigned short PLAYER_STATUS_ERROR;<br /> const unsigned short PLAYER_STATUS_RELEASED;<br /> <br /> readonly attribute unsigned short status;<br /> <br /> attribute unsigned short volume;<br /> attribute ABRControlParameters abrControlParameters;<br /> attribute BufferControlParameters bufferControlParameters;<br /> <br /> const unsigned short VISIBLE; //For CC visibility<br /> const unsigned short INVISIBLE; //For CC visibility<br /> attribute unsigned short ccVisibility;<br /> attribute TextFormat ccStyle;<br /> readonly attribute PlaybackMetrics playbackMetrics;<br /> <br /> attribute double rate;<br /> attribute MediaPlayerView view;<br /> readonly attribute Timeline timeline;<br /> attribute double currentTimeUpdateInterval; <br /> // setting this Won't be supported for 2.0<br /> };</p> </td> 
   <td valign="top"><p>interface MediaPlayer : EventTarget<br /> {<br /> void prepareToPlay( int position);<br /> void play();<br /> void pause();<br /> void seek( int position);<br /> void seekToLocalTime( int position);<br /> void reset();<br /> void release();<br /> void replaceCurrentItem(MediaResource source);<br /> <br /> <br /> <br /> <br /> <br /> <br /> readonly attribute TimeRange playbackRange;<br /> readonly attribute TimeRange seekableRange;<br /> readonly attribute double currentTime;<br /> readonly attribute double localTime;<br /> readonly attribute TimeRange bufferedRange;<br /> readonly attribute DRMManager drmManager;<br /> readonly attribute MediaPlayerItem currentItem;<br /> <br /> // PlayerState<br /> const unsigned short PLAYER_STATE_IDLE;<br /> const unsigned short PLAYER_STATE_INITIALIZING;<br /> const unsigned short PLAYER_STATE_INITIALIZED;<br /> const unsigned short PLAYER_STATE_PREPARING;<br /> const unsigned short PLAYER_STATE_PREPARED;<br /> const unsigned short PLAYER_STATE_PLAYING;<br /> const unsigned short PLAYER_STATE_PAUSED;<br /> const unsigned short PLAYER_STATE_SEEKING;<br /> const unsigned short PLAYER_STATE_COMPLETE;<br /> const unsigned short PLAYER_STATE_ERROR;<br /> const unsigned short PLAYER_STATE_RELEASED;<br /> const unsigned short PLAYER_STATUS_SUSPENDED;<br /> readonly attribute unsigned short state;<br /> <br /> attribute unsigned short volume;<br /> attribute ABRControlParameters abrControlParameters;<br /> attribute BufferControlParameters bufferControlParameters;<br /> <br /> readonly unsigned short VISIBLE; //For CC visibility<br /> readonly unsigned short INVISIBLE; //For CC visibility<br /> attribute unsigned short ccVisibility;<br /> attribute TextFormat ccStyle;<br /> readonly attribute PlaybackMetrics playbackMetrics;<br /> attribute MediaPlayerConfig mediaPlayerConfig;<br /> attribute double rate;<br /> attribute MediaPlayerView view;<br /> readonly attribute Timeline timeline;<br /> <br /> <br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>MediaPlayerStatus</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface MediaPlayerStatus<br /> {<br /> // PlayerStatus<br /> const unsigned short PLAYER_STATUS_IDLE;<br /> const unsigned short PLAYER_STATUS_INITIALIZING;<br /> const unsigned short PLAYER_STATUS_INITIALIZED;<br /> const unsigned short PLAYER_STATUS_PREPARING;<br /> const unsigned short PLAYER_STATUS_PREPARED;<br /> const unsigned short PLAYER_STATUS_PLAYING;<br /> const unsigned short PLAYER_STATUS_PAUSED;<br /> const unsigned short PLAYER_STATUS_SEEKING;<br /> const unsigned short PLAYER_STATUS_COMPLETE;<br /> const unsigned short PLAYER_STATUS_ERROR;<br /> const unsigned short PLAYER_STATUS_RELEASED;<br /> const unsigned short PLAYER_STATUS_SUSPENDED;<br /> };</p> </td> 
   <td valign="top">(New for 2.0)</td> 
  </tr> 
 </tbody> 
</table>

#### Events supported by MediaPlayer {#events-supported-by-mediaplayer}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 Event name</th> 
   <th>2.0 Interface</th> 
   <th> </th> 
   <th>1.3 Event name</th> 
   <th>1.3 Interface</th> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%"><p>(deleted for 2.0)</p> </td> 
   <td valign="top" width="24.922061250687694%"> </td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">prepared</td> 
   <td valign="top" width="24.59196772418852%">Event</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%"><p>itemUpdated</p> <p>When a media player item is updated.</p> </td> 
   <td valign="top" width="24.922061250687694%">MediaPlayerItemEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%"><p>updated</p> <p>When the media player has successfully updated the media.</p> </td> 
   <td valign="top" width="24.59196772418852%">Event</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">timedMetadataAvailable</td> 
   <td valign="top" width="24.922061250687694%">TimedMetadataEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">TtmedMetadata</td> 
   <td valign="top" width="24.59196772418852%">TimedMetadataEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">timelineUpdated</td> 
   <td valign="top" width="24.922061250687694%">Event</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">TtmelineUpdated</td> 
   <td valign="top" width="24.59196772418852%">Event</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">Deleted in 2.0</td> 
   <td valign="top" width="24.922061250687694%"> </td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">playStart</td> 
   <td valign="top" width="24.59196772418852%">Event</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">Deleted for 2.0</td> 
   <td valign="top" width="24.922061250687694%"> </td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">playComplete</td> 
   <td valign="top" width="24.59196772418852%">Event</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">statusChanged</td> 
   <td valign="top" width="24.922061250687694%">StatusEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">stateChanged</td> 
   <td valign="top" width="24.59196772418852%">StateEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">sizeAvailable</td> 
   <td valign="top" width="24.922061250687694%">SizeEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">size</td> 
   <td valign="top" width="24.59196772418852%">SizeEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">adBreakStarted</td> 
   <td valign="top" width="24.922061250687694%">AdBreakEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">adBreakStart</td> 
   <td valign="top" width="24.59196772418852%">AdBreakEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">adStarted</td> 
   <td valign="top" width="24.922061250687694%">AdEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">adStart</td> 
   <td valign="top" width="24.59196772418852%">AdEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">adProgress</td> 
   <td valign="top" width="24.922061250687694%">AdProgressEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">adProgress</td> 
   <td valign="top" width="24.59196772418852%">AdProgressEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">adCompleted</td> 
   <td valign="top" width="24.922061250687694%">AdEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">adComplete</td> 
   <td valign="top" width="24.59196772418852%">AdEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">adBreakCompleted</td> 
   <td valign="top" width="24.922061250687694%">AdBreakEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">adBreakComplete</td> 
   <td valign="top" width="24.59196772418852%">AdBreakEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">timeChanged</td> 
   <td valign="top" width="24.922061250687694%">TimeEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">progress</td> 
   <td valign="top" width="24.59196772418852%">ProgressEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">bufferingBegin</td> 
   <td valign="top" width="24.922061250687694%">Event</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">buffer</td> 
   <td valign="top" width="24.59196772418852%">Event</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">bufferingEnd</td> 
   <td valign="top" width="24.922061250687694%">Event</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">bufferComplete</td> 
   <td valign="top" width="24.59196772418852%">Event</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">seekBegin</td> 
   <td valign="top" width="24.922061250687694%">SeekEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">seekStart</td> 
   <td valign="top" width="24.59196772418852%">Event</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">seekEnd</td> 
   <td valign="top" width="24.922061250687694%">SeekEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">seekComplete</td> 
   <td valign="top" width="24.59196772418852%">TimeEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">loadInformationAvailable</td> 
   <td valign="top" width="24.922061250687694%">LoadInformationEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">loadInfo</td> 
   <td valign="top" width="24.59196772418852%">LoadInfoEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">operationFailed</td> 
   <td valign="top" width="24.922061250687694%">NotificationEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">operationFailed</td> 
   <td valign="top" width="24.59196772418852%">ErrorEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">drmMetadataInfoAvailable</td> 
   <td valign="top" width="24.922061250687694%">DRMMetadataEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">drmMetadata</td> 
   <td valign="top" width="24.59196772418852%">DRMMetadataEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">reservationReached</td> 
   <td valign="top" width="24.922061250687694%">ReservationEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">timelineHolderReached</td> 
   <td valign="top" width="24.59196772418852%">TimelineHolderEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%"> </td> 
   <td valign="top" width="24.922061250687694%"> </td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">bitrateChanged</td> 
   <td valign="top" width="24.59196772418852%">BitrateChangedEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">rateSelected</td> 
   <td valign="top" width="24.922061250687694%">PlaybackRateEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">rateSelected</td> 
   <td valign="top" width="24.59196772418852%">PlaybackRateEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">ratePlaying</td> 
   <td valign="top" width="24.922061250687694%">PlaybackRateEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">ratePlaying</td> 
   <td valign="top" width="24.59196772418852%">PlaybackRateEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">adBreakSkipped</td> 
   <td valign="top" width="24.922061250687694%">AdBreakEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%">adBreakSkipped</td> 
   <td valign="top" width="24.59196772418852%">AdBreakEvent</td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">adClicked<br /> When user clicks on an Ad.</td> 
   <td valign="top" width="24.922061250687694%">AdClickedEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%"><p>New in 2.0</p> </td> 
   <td valign="top" width="24.59196772418852%"> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">profileChanged<br /> When the playback profile changes.</td> 
   <td valign="top" width="24.922061250687694%">ProfileEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%"><p>New in 2.0</p> </td> 
   <td valign="top" width="24.59196772418852%"> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">seekPositionAdjusted<br /> When seek position adjusts due to internal or external rules.</td> 
   <td valign="top" width="24.922061250687694%">SeekEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%"><p>New in 2.0</p> </td> 
   <td valign="top" width="24.59196772418852%"> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">audioUpdated<br /> When a media player item is updated. For certain streams that contain audio tracks that are detectable only at playback time, this event is fired when new audio tracks are available.</td> 
   <td valign="top" width="24.922061250687694%">MediaPlayerItemEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%"><p>New in 2.0</p> </td> 
   <td valign="top" width="24.59196772418852%"> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">captionsUpdated <br /> When a media player item is updated. For live/linear streams, the client must periodically refresh the media resource to detect the new available content. When this happens, certain media characteristics might change.</td> 
   <td valign="top" width="24.922061250687694%">MediaPlayerItemEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%"><p>New in 2.0</p> </td> 
   <td valign="top" width="24.59196772418852%"> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">masterUpdated <br /> When a media player item is updated. For live/linear streams, the client must periodically refresh the media resource to detect the new available content. When this happens, certain media characteristics might change.</td> 
   <td valign="top" width="24.922061250687694%">MediaPlayerItemEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%"><p>New in 2.0</p> </td> 
   <td valign="top" width="24.59196772418852%"> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">playbackRangeUpdated<br /> When a media player item is updated. For live/linear streams, the client must periodically refresh the media resource to detect the new available content. When this happens, certain media characteristics might change.</td> 
   <td valign="top" width="24.922061250687694%">MediaPlayerItemEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%"><p>New in 2.0</p> </td> 
   <td valign="top" width="24.59196772418852%"> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="24.280212726939297%">timedEvent<br /> Sent when timed events are generated.</td> 
   <td valign="top" width="24.922061250687694%">TimedEvent</td> 
   <td valign="top" width="1.8338529249954154%"> </td> 
   <td valign="top" width="24.37190537318907%"><p>New in 2.0</p> </td> 
  </tr> 
 </tbody> 
</table>

### ABRControlParameters {#abrcontrolparameters}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>ABRControlParameters</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface ABRControlParameters<br /> {<br /> const unsigned short ABR_POLICY_CONSERVATIVE = 0 ;<br /> const unsigned short ABR_POLICY_MODERATE = 1 ;<br /> const unsigned short ABR_POLICY_AGGRESIVE = 2 ;<br /> <br /> attribute unsigned short abrPolicy;<br /> attribute unsigned int initialBitRate;<br /> attribute unsigned int minBitRate;<br /> attribute unsigned int maxBitRate;<br /> const unsigned short DEFAULT_ABR_INITIAL_BITRATE;<br /> const unsigned short DEFAULT_ABR_MIN_BITRATE;<br /> const unsigned short DEFAULT_ABR_MAX_BITRATE;<br /> const ABRPolicy DEFAULT_ABR_POLICY;<br /> };</p> </td> 
   <td valign="top"><p>interface ABRControlParameters<br /> {<br /> const unsigned short ABR_POLICY_CONSERVATIVE = 0 ;<br /> const unsigned short ABR_POLICY_MODERATE = 1 ;<br /> const unsigned short ABR_POLICY_AGGRESIVE = 2 ;<br /> <br /> attribute unsigned short abrPolicy;<br /> attribute unsigned int initialBitRate;<br /> attribute unsigned int minBitRate;<br /> attribute unsigned int maxBitRate;<br /> <br /> <br /> <br /> <br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### BufferControlParameters {#buffercontrolparameters}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>BufferControlParameters</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface BufferControlParameters<br /> {<br /> attribute double initialBufferTime;<br /> attribute double playBufferTime;<br /> const double DEFAULT_INITIAL_BUFFER_TIME;<br /> const double DEFAULT_PLAY_BUFFER_TIME;<br /> };</p> </td> 
   <td valign="top"><p>interface BufferControlParameters<br /> {<br /> attribute double initialBufferTime;<br /> attribute double playBufferTime;<br /> <br /> <br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### TextFormat {#textformat}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>TextFormat</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0</td> 
   <td valign="top"><p>interface TextFormat<br /> {<br /> // Color<br /> const unsigned short COLOR_DEFAULT = 0 ;<br /> const unsigned short COLOR_BLACK = 1 ;<br /> const unsigned short COLOR_GRAY = 2 ;<br /> const unsigned short COLOR_WHITE = 3 ;<br /> const unsigned short COLOR_BRIGHT_WHITE = 4 ;<br /> const unsigned short COLOR_DARK_RED = 5 ;<br /> const unsigned short COLOR_RED = 6 ;<br /> const unsigned short COLOR_BRIGHT_RED = 7 ;<br /> const unsigned short COLOR_DARK_GREEN = 8 ;<br /> const unsigned short COLOR_GREEN = 9 ;<br /> const unsigned short COLOR_BRIGHT_GREEN = 10 ;<br /> const unsigned short COLOR_DARK_BLUE = 11 ;<br /> const unsigned short COLOR_BLUE = 12 ;<br /> const unsigned short COLOR_BRIGHT_BLUE = 13 ;<br /> const unsigned short COLOR_DARK_YELLOW = 14 ;<br /> const unsigned short COLOR_YELLOW = 15 ;<br /> const unsigned short COLOR_BRIGHT_YELLOW = 16 ;<br /> const unsigned short COLOR_DARK_MAGENTA = 17 ;<br /> const unsigned short COLOR_MAGENTA = 18 ;<br /> const unsigned short COLOR_BRIGHT_MAGENTA = 19 ;<br /> const unsigned short COLOR_DARK_CYAN = 20 ;<br /> const unsigned short COLOR_CYAN = 21 ;<br /> const unsigned short COLOR_BRIGHT_CYAN = 22 ;<br /> <br /> readonly attribute unsigned short fontColor;<br /> readonly attribute unsigned short backgroundColor;<br /> readonly attribute unsigned short fillColor;<br /> readonly attribute unsigned short edgeColor;<br /> <br /> // Size<br /> const unsigned short SIZE_DEFAULT = 0 ;<br /> const unsigned short SIZE_SMALL = 1 ;<br /> const unsigned short SIZE_MEDIUM = 2 ;<br /> const unsigned short SIZE_LARGE = 3 ;<br /> <br /> readonly attribute unsigned short size;<br /> <br /> // FontEdge<br /> const unsigned short FONT_EDGE_DEFAULT = 0 ;<br /> const unsigned short FONT_EDGE_NONE = 1 ;<br /> const unsigned short FONT_EDGE_RAISED = 2 ;<br /> const unsigned short FONT_EDGE_DEPRESSED = 3 ;<br /> const unsigned short FONT_EDGE_UNIFORM = 4 ;<br /> const unsigned short FONT_EDGE_DROP_SHADOW_LEFT = 5 ;<br /> const unsigned short FONT_EDGE_DROP_SHADOW_RIGHT = 6 ;<br /> readonly attribute unsigned short fontEdge;<br /> <br /> // Font<br /> const unsigned short FONT_DEFAULT = 0 ;<br /> const unsigned short FONT_MONOSPACED_WITH_SERIFS = 1 ;<br /> const unsigned short FONT_PROPORTIONAL_WITH_SERIFS = 2 ;<br /> const unsigned short FONT_MONSPACED_WITHOUT_SERIFS = 3 ;<br /> const unsigned short FONT_CASUAL = 4 ;<br /> const unsigned short FONT_CURSIVE = 5 ;<br /> const unsigned short FONT_SMALL_CAPITALS = 6 ;<br /> readonly attribute unsigned short font;<br /> readonly attribute unsigned short fontOpacity;<br /> readonly attribute unsigned short backgroundOpacity;<br /> readonly attribute unsigned short fillOpacity;<br /> readonly attribute unsigned short DEFAULT_OPACITY;<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### MediaPlayerItemLoader {#mediaplayeritemloader}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>MediaPlayerItemLoader</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface MediaPlayerItemLoader:<br /> {<br /> void load(MediaResource resource, long resourceId,<br /> ItemLoaderListener listener, <br /> MediaPlayerItemConfig config) ;<br /> void cancel();<br /> readonly attribute MediaPlayerItem currentItem;<br /> };</p> </td> 
   <td valign="top">New for 2.0</td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>ItemLoaderListener</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface ItemLoaderListener<br /> {<br /> //onLoadCompleteCallbackFunc(MediaPlayerItem)<br /> var onLoadCompleteCallbackFunc;<br /> //onErrorCallbackFunc(PSDKErrorCode)<br /> var onErrorCallbackFunc;<br /> }</p> </td> 
   <td valign="top">New for 2.0</td> 
  </tr> 
 </tbody> 
</table>

## Media characteristics API element changes for 2.0 {#media-characteristics-api-element-changes-for}

These tables compare the media characteristic API elements for the C++ TVSDK between versions 1.3 and 2.0.

Tables in this topic:

* MediaPlayerItem
* Track, AudioTrack, ClosedCaptionsTrack
* Profile
* DRMMetadataInfo

### MediaPlayerItem {#mediaplayeritem}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>MediaPlayerItem</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface MediaPlayerItem {<br /> readonly attribute MediaResource resource;<br /> readonly attribute long resourceId;<br /> readonly attribute boolean live;<br /> <br /> readonly attribute boolean hasAlternateAudio;<br /> readonly attribute AudioTrackList audioTracks;<br /> readonly attribute AudioTrack selectedAudioTrack;<br /> void selectAudioTrack(AudioTrack track); <br /> <br /> readonly attribute boolean hasClosedCaptions;<br /> readonly attribute ClosedCaptionsTrackList closedCaptionsTracks;<br /> readonly attribute ClosedCaptionsTrack selectedClosedCaptionsTrack;<br /> void selectClosedCaptionsTrack(<br /> ClosedCaptionsTrack track); <br /> <br /> readonly attribute boolean hasTimedMetadata;<br /> readonly attribute TimedMetadataList timedMetadata;<br /> readonly attribute boolean dynamic;<br /> <br /> readonly attribute boolean isProtected;<br /> readonly attribute DRMMetadataInfoList drmMetadataInfos;<br /> readonly attribute ProfileList profiles;<br /> readonly attribute Profile selectedProfile;<br /> <br /> readonly attribute boolean trickPlaySupported;<br /> readonly attribute FloatArray availablePlaybackRates;<br /> readonly attribute float selectedPlaybackRate;<br /> <br /> <br /> readonly attribute MediaPlayer mediaPlayer;<br /> readonly attribute MediaPlayerItemConfig config;<br /> };</p> </td> 
   <td valign="top"><p>interface MediaPlayerItem {<br /> readonly attribute MediaResource resource;<br /> readonly attribute long resourceId;<br /> readonly attribute boolean live;<br /> <br /> readonly attribute boolean hasAlternateAudio;<br /> readonly attribute AudioTrackList audioTracks;<br /> attribute AudioTrack selectedAudioTrack;<br /> <br /> <br /> readonly attribute boolean hasClosedCaptions;<br /> readonly attribute ClosedCaptionsTrackList ccTracks;<br /> attribute ClosedCaptionsTrack selectedCCTrack;<br /> <br /> <br /> <br /> readonly attribute boolean hasTimedMetadata;<br /> readonly attribute TimedMetadataList timedMetadata;<br /> readonly attribute boolean dynamic;<br /> <br /> readonly attribute boolean isProtected;<br /> readonly attribute DRMMetadataInfoList drmMetadataInfos;<br /> readonly attribute ProfileList profiles;<br /> <br /> <br /> readonly attribute boolean trickPlaySupported;<br /> readonly attribute Int32Array availablePlaybackRates;<br /> <br /> readonly attribute StringList adTags;<br /> <br /> readonly attribute MediaPlayer mediaPlayer;<br /> <br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### Track / AudioTrack / ClosedCaptionsTrack {#track-audiotrack-closedcaptionstrack}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>Track</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface Track<br /> {<br /> readonly attribute DomString name;<br /> readonly attribute DomString language;<br /> readonly attribute boolean default;<br /> readonly attribute boolean autoSelect;<br /> }; </p> </td> 
   <td valign="top">New for 2.0</td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AudioTrack</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface AudioTrack : Track<br /> {<br /> readonly attribute DomString name; //FromTrack<br /> readonly attribute DomString language;//FromTrack<br /> readonly attribute boolean default; // From Track<br /> readonly attribute boolean autoSelect;//FromTrack<br /> <br /> readonly attribute unsigned int pid;<br /> };</p> </td> 
   <td valign="top"><p>interface AudioTrack<br /> {<br /> readonly attribute DomString name;<br /> readonly attribute DomString language; <br /> readonly attribute boolean default;<br /> readonly attribute boolean autoSelect;<br /> readonly attribute boolean forced;<br /> <br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>AudioTrackList</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0</td> 
   <td valign="top"><p>interface AudioTrackList<br /> {<br /> readonly attribute unsigned long length;<br /> getter AudioTrack (unsigned long index);<br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>ClosedCaptionsTrack</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface ClosedCaptionsTrack : Track<br /> {<br /> readonly attribute DomString name; //FromTrack<br /> readonly attribute DomString language;//FromTrack<br /> readonly attribute boolean default; // FromTrack<br /> readonly attribute boolean autoSelect;//FromTrack<br /> <br /> <br /> const unsigned short SERVICE_608_CAPTIONS = 0;<br /> const unsigned short SERVICE_708_CAPTIONS = 1;<br /> const unsigned short SERVICE_WEB_VTT_CAPTIONS = 2;<br /> readonly attribute unsigned short serviceType;<br /> readonly attribute boolean forced;<br /> };</p> </td> 
   <td valign="top"><p>interface ClosedCaptionsTrack<br /> {<br /> readonly attribute DomString name;<br /> readonly attribute DomString language;<br /> readonly attribute boolean default;<br /> <br /> <br /> readonly attribute boolean active;<br /> <br /> <br /> <br /> <br /> <br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>ClosedCaptionsTrackList</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0</td> 
   <td valign="top"><p>interface ClosedCaptionsTrackList<br /> {<br /> readonly attribute unsigned long length;<br /> getter ClosedCaptionsTrack(unsigned long index);<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### Profile {#profile}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>Profile</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0</td> 
   <td valign="top"><p>interface Profile<br /> {<br /> readonly attribute unsigned int width;<br /> readonly attribute unsigned int height;<br /> readonly attribute unsigned int bitRate;<br /> }; </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>ProfileList</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0</td> 
   <td valign="top"><p>interface ProfileList<br /> {<br /> readonly attribute unsigned long length;<br /> getter Profile(unsigned long index);<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### DRMMetadataInfo {#drmmetadatainfo}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMMetadataInfo</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0</td> 
   <td valign="top"><p>interface DRMMetadataInfo<br /> { <br /> readonly attribute DRMMetadata metadata;<br /> readonly attribute long prefetchTimestamp;<br /> readonly attribute TimeRange timeRange;<br /> };</p> </td> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DRMMetadataInfoList</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0</td> 
   <td valign="top"><p>interface DRMMetadataInfoList<br /> {<br /> readonly attribute unsigned long length;<br /> getter DRMMetadataInfo(unsigned long index);<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

## Mapping C++ Errors to Exceptions in Different Languages {#mapping-c-errors-to-exceptions-in-different-languages}

You can map C++ error codes to exceptions in different languages.

The C++ PSDK has a "no throw" policy for its APIs. Most of the API methods return a PSDKErrorCode value to indicate whether the method was executed successfully. Asynchronous errors are notified through the error events.

The ActionScript and JAVA PSDK have a different policy. Most of the errors will throw an ArgumentError or IllegalStateException to indicate that the synchronous part of the method could not be executed. These exceptions are not caught, and the application code is responsible for handling the exceptions. They usually carry useful information of why the method call failed. For example, if the prepareToPlay command is called in an invalid state, the following exception is thrown:

```shell
throw new IllegalStateException("Invalid player state. prepareToPlay method 
must be called only once after replaceCurrentItem or replaceCurrentResource method.");
```

The ActionScript/JAVA also throws exceptions from constructors to indicate that some internal object was incorrectly created. These exceptions are handled internally, and they are not propagated to the application. The exceptions will be included in a warning notification that is sent to the application

For example, if no valid media file was found for the received ad response, then no valid ad asset object or ad can be created. As a result, no ad is placed on the timeline, and a NotificationEvent.OperationFailed notification is dispatched.

Error or warning codes that are received asynchronously from the Adobe Video Engine (AVE) are dispatched to the application as normal events. The notification event contains all received error codes and any additional metadata, such as the URL, resource identifier, handle, and so on. If the error is serious and the playback of the current media cannot continue, the MediaPlayer transitions to the ERROR status and onStatusChanged callback or MediaPlayerStatusChanged.STATUS_CHANGED event is dispatched. If the playback can continue, a normal notification event is dispatched.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>C++ Error (PSDKError Code)</th> 
   <th> </th> 
   <th>Java</th> 
   <th>ActionScript</th> 
   <th>JavaScript</th> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECInvalidArgument</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">IllegalArgumentException</td> 
   <td valign="top" width="16.745459069420257%">ArgumentError</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 1, description = "INVALID_ARGUMENT" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECNullPointer</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">IllegalArgumentException</td> 
   <td valign="top" width="16.745459069420257%">ArgumentError</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 2, description = "GENERIC_ERROR" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECIllegalState</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">IllegalStateException</td> 
   <td valign="top" width="16.745459069420257%">IllegalStateException</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 3, description = "ILLEGAL_STATE" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECInterfaceNotFound</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 4, description = "GENERIC_ERROR" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECCreationFailed</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 5, description = "CREATION_FAILED" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECUnsupportedOperation</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 5, description = "CREATION_FAILED" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECDataNotAvailable</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 7, description = "DATA_NOT_AVAILABLE" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECSeekError</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 8, description = "SEEK_ERROR" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECUnsupportedFeature</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 9, description = "UNSUPPORTED_FEATURE" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECRangeError</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 10, description = "RANGE_ERROR" and additionalInfo= &lt;as passed by method which threw this exception</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECCodecNotSupported</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 11, description = "CODEC_NOT_SUPPORTED" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECMediaError</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 12, description = "MEDIA_ERROR" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECNetworkError</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 13, description = "NETWORK_ERROR" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECGenericError</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">MediaPlayerNotification.Error or MediaPlayerNotification.Warning</td> 
   <td valign="top" width="16.745459069420257%">MediaError or NotificationEvent</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 14, description = "GENERIC_ERROR" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECInvalidSeekTime</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 15, description = "INVALID_SEEK_TIME" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECAudioTrackError</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 16, description = "AUDIO_TRACK_ERROR" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECAccessFromDifferent<p>ThreadError</p> </td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 17, description = "GENERIC_ERROR" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECElementNotFound</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 18, description = "GENERIC_ERROR" and additionalInfo= &lt;as passed by method which threw this exception</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECNotImplemented</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 19, description = "GENERIC_ERROR" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECPlaybackOperationFailed</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">-</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 200, description = "PLAYBACK_OPERATION_FAILED" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECNativeWarning</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">MediaPlayerNotification.Warning</td> 
   <td valign="top" width="16.745459069420257%">NotificationEvent</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 201, description = "NATIVE_WARNING" and additionalInfo= &lt;as passed by method which threw this exception</td> 
  </tr> 
  <tr> 
   <td valign="top" width="26.312515551132122%">kECAdResolverFailed</td> 
   <td valign="top" width="1.2440905697934812%"> </td> 
   <td valign="top" width="20.96292610102016%">MediaPlayerNotification.Warning</td> 
   <td valign="top" width="16.745459069420257%">-</td> 
   <td valign="top" width="34.73500870863399%">Exception with code = 202, description = "AD_RESOLVER_FAILED" and additionalInfo= &lt;as passed by method which threw this exception&gt;</td> 
  </tr> 
 </tbody> 
</table>

## Utility and Helper API element changes for 2.0 {#utility-and-helper-api-element-changes-for}

These tables compare the Utility and Helper API elements for the JavaScript TVSDK between versions 1.3 and 2.0.

Tables in this topic:

* Version
* TimeRange
* QOSProvider
* DeviceInformation
* LoadInfo
* View
* PlaybackInformation

### Version {#version}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>Version</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface Version<br /> {<br /> readonly attribute DomString version;<br /> readonly attribute DomString description;<br /> readonly attribute long major;<br /> readonly attribute long minor;<br /> readonly attribute long revision;<br /> readonly attribute long apiVersion;<br /> };</p> </td> 
   <td valign="top"><p>interface Version<br /> {<br /> readonly attribute DomString version;<br /> readonly attribute DomString description;<br /> readonly attribute DomString major;<br /> readonly attribute DomString minor;<br /> readonly attribute DomString revision;<br /> readonly attribute DomString apiVersion;<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### TimeRange {#timerange}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>TimeRange</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0</td> 
   <td valign="top"><p>interface TimeRange<br /> {<br /> readonly attribute unsigned long begin;<br /> readonly attribute unsigned long end;<br /> readonly attribute unsigned long duration;<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### QOSProvider {#qosprovider}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>QOSProvider</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0</td> 
   <td valign="top"><p>interface QOSProvider<br /> {<br /> void attachMediaPlayer(MediaPlayer player);<br /> void detachMediaPlayer();<br /> <br /> readonly attribute DeviceInformation deviceInformation;<br /> readonly attribute PlaybackInformation playbackInformation;<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### DeviceInformation {#deviceinformation}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>DeviceInformation</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface DeviceInformation<br /> {<br /> readonly attribute DomString os;<br /> <br /> <br /> <br /> readonly attribute DomString id;<br /> readonly attribute int densityDPI;<br /> readonly attribute int heightPixels;<br /> readonly attribute int widthPixels;<br /> readonly attribute boolean seekToKeyFrame;<br /> };</p> </td> 
   <td valign="top"><p>interface DeviceInformation<br /> {<br /> readonly attribute DomString os;<br /> readonly attribute int sdk;<br /> readonly attribute DomString model;<br /> readonly attribute DomString manufacturer;<br /> readonly attribute DomString id;<br /> readonly attribute int densityDPI;<br /> readonly attribute int heightPixels;<br /> readonly attribute int widthPixels;<br /> <br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### LoadInfo {#loadinfo}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>LoadInfo</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0</td> 
   <td valign="top"><p>interface LoadInfo<br /> {<br /> readonly attribute DomString url;<br /> readonly attribute int size;<br /> readonly attribute double downloadDuration;<br /> readonly attribute int periodIndex;<br /> readonly attribute double mediaDuration;<br /> readonly attribute short TRACK_TYPE_FRAGMENT;<br /> readonly attribute short TRACK_TYPE_TRACK;<br /> readonly attribute short TRACK_TYPE_MANIFEST;<br /> readonly attribute short type;<br /> readonly attribute DomString trackName;<br /> readonly attribute DomString trackType;<br /> readonly attribute int trackIndex;<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

### View {#view}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>View</strong></td> 
  </tr> 
  <tr> 
   <td valign="top">No change for 2.0</td> 
   <td valign="top"><p>interface View<br /> {<br /> readonly attribute unsigned short x;<br /> readonly attribute unsigned short y;<br /> readonly attribute unsigned short width;<br /> readonly attribute unsigned short height;<br /> <br /> void setSize(unsigned short width, unsigned short height);<br /> void setPos(unsigned short x, unsigned short y);<br /> }</p> </td> 
  </tr> 
 </tbody> 
</table>

### PlaybackInformation {#playbackinformation}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>2.0 APIs</th> 
   <th>1.3 APIs</th> 
  </tr> 
  <tr> 
   <td colspan="2" valign="top"><strong>PlaybackInformation</strong></td> 
  </tr> 
  <tr> 
   <td valign="top"><p>interface PlaybackInformation<br /> {<br /> readonly attribute double timeToFirstByte;<br /> readonly attribute double timeToLoad;<br /> readonly attribute double timeToStart;<br /> readonly attribute double timeToFail;<br /> readonly attribute int totalSecondsPlayed;<br /> readonly attribute int totalSecondsSpent;<br /> readonly attribute double frameRate;<br /> readonly attribute int droppedFrameCount;<br /> readonly attribute int perceivedBandwidth;<br /> readonly attribute int bitrate;<br /> readonly attribute double bufferTime;<br /> readonly attribute int bufferLength;<br /> readonly attribute int emptyBufferCount;<br /> readonly attribute double bufferingTime;<br /> };</p> </td> 
   <td valign="top"><p>interface PlaybackInformation<br /> {<br /> readonly attribute double timeToFirstByte;<br /> readonly attribute double timeToLoad;<br /> readonly attribute double timeToStart;<br /> readonly attribute double timeToFail;<br /> readonly attribute int totalSecondsPlayed;<br /> readonly attribute int totalSecondsSpent;<br /> readonly attribute double frameRate;<br /> readonly attribute int droppedFrameCount;<br /> <br /> readonly attribute int bitrate;<br /> readonly attribute double bufferTime;<br /> readonly attribute int bufferLength;<br /> readonly attribute int emptyBufferCount;<br /> readonly attribute double bufferingTime;<br /> };</p> </td> 
  </tr> 
 </tbody> 
</table>

