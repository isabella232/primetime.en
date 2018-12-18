---
description: These classes provide metadata for advertising, namespaces, and tracking.
seo-description: These classes provide metadata for advertising, namespaces, and tracking.
seo-title: Metadata classes
title: Metadata classes
uuid: 6d5099c8-d562-4635-9ef0-068cc6fb9f82
index: y
internal: n
snippet: y
---

# Metadata classes{#metadata-classes}

These classes provide metadata for advertising, namespaces, and tracking.

 Package: [com.adobe.mediacore.metadata](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/metadata/package-summary.html) 

|  Name  | Description  |
|---|---|
| ` [AdvertisingMetadata](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/metadata/AdvertisingMetadata.html)` | Class that provides properties that should be configured for resolving ads for a given media item. All the required properties must be set to configure the player for successfully resolving ads.  |
| `AuditudeMetadata`  | Deprecated. Use AuditudeSettings.  |
| ` [AuditudeSettings](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/metadata/AuditudeSettings.html)`  |Class that extends Java `AdvertisingMetadata` specifically for  Phrase. Provides properties to be configured for resolving  Phrase ads for a given media item. You must set all the required properties, including zone ID, media ID, and ad server URL, to configure the player for successfully resolving ads.  |
| ` [Metadata](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/metadata/Metadata.html)` | Defines the generic interface for configuring all available metadata for your player and additional objects. |
| ` [MetadataNode](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/metadata/MetadataNode.html)` | Generic data-structure-like class for storing arbitrary key-value pairs.  |
| ` [TimedMetadata](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/metadata/TimedMetadata.html)` | Class for the raw representation of the timed metadata inserted into a media stream. |

