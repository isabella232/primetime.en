---
cloud: experience-cloud
product: adobe
archtype: end-user
user-guide: null
---

# Table of Contents {#table-of-contents}

+ [Manifest Server Debugging Tool](manifest-server-debugging-tool.md)
+ Manifest Server API for Ad Insertion
   + [Overview of Manifest Server interactions](msapi_topics/ms-overview.md)
   + Get started with Manifest Server
      + [Send a command to the Manifest Server](msapi_topics/ms-getting-started/ms-sending-cmd.md)
      + [Manifest server query parameters](msapi_topics/ms-getting-started/ms-api-query-params.md)
   + [Ad insertion requests](msapi_topics/ms-insert-ads/ms-insert-ads.md)
      + [Requests for ad insertion](msapi_topics/ms-insert-ads/ms-ad-insert.md)
      + [Optional query parameters by client and situation](msapi_topics/ms-insert-ads/ms-api-query-param-situation.md)
      + [Facilitating HLS player switching to failover/backup streams](msapi_topics/ms-insert-ads/hls-switching-to-failover.md)
      + [Multiple bit rate streams](msapi_topics/ms-insert-ads/ms-api-mbr-streams.md)
      + [Partial Ad Break Insertion](msapi_topics/ms-insert-ads/partial-ad-break-insetion.md)
      + [Multiple CDN support for CRS ad delivery](msapi_topics/ms-insert-ads/ms-api-multi-cdns-for-crs.md)
   + [Replace VOD timelines](msapi_topics/ms-changes-vod-timeline/ms-changes-vod-timeline.md)
      + [Changes to VOD](msapi_topics/ms-changes-vod-timeline/ms-replace-vod-timeline.md)
      + [VOD timeline format](msapi_topics/ms-changes-vod-timeline/ms-api-timeline-format.md)
      + [Replace a VOD timeline](msapi_topics/ms-changes-vod-timeline/t-ms-replace-vod-timeline.md)
   + [Ad effectiveness tracking](msapi_topics/ms-at-effectiveness/ms-at-effectiveness.md)
      + [Ad tracking](msapi_topics/ms-at-effectiveness/ms-at-overview.md)
      + [Enable client-side ad tracking](msapi_topics/ms-at-effectiveness/ms-enable-client-side-ad-tracking.md)
      + [Overview of non-TVSDK client-side tracking](msapi_topics/ms-at-effectiveness/notvsdk-csat-overview.md)
      + [API for players to interact with the manifest server](msapi_topics/ms-at-effectiveness/notvsdk-csat-ms-interface.md)
      + [EXT-X-MARKER Directive](msapi_topics/ms-at-effectiveness/ms-api-playlists.md)
   + [Cookies](msapi_topics/ms-cookies.md)
   + [Support for WebVTT captions](msapi_topics/ms-webvtt-captions.md)
   + [List of file formats](msapi_topics/ms-list-file-formats/ms-list-file-formats.md)
      + [File formats](msapi_topics/ms-list-file-formats/ms-api-file-formats.md)
      + [JSON format for URL for requesting variant manifest playlist](msapi_topics/ms-list-file-formats/ms-json-m3u8.md)
      + [JSON formats for tracking URLs](msapi_topics/ms-list-file-formats/notvsdk-csat-sidecar.md)
      + [VMAP format for tracking URLs](msapi_topics/ms-list-file-formats/notvsdk-csat-vmap.md)
   + [Video player requirements](msapi_topics/ms-player-req.md)
+ Primetime Creative Repackaging Service (CRS)
   + [Overview of   CRS](creative-repackaging-service/crs-overview.md)
   + [Main Uses of CRS](creative-repackaging-service/jit-async-hls-conv.md)
   + [Multi CDN   support](creative-repackaging-service/multi-cdn-supportt.md)
   + [Detailed Workflows for JIT Repackaging](creative-repackaging-service/jit-repackage.md)
   + [Using CRS to Inject ID3 Timed Metadata Tags](creative-repackaging-service/inject-id3.md)
   + [Repackaging API](creative-repackaging-service/api-repackage.md)
