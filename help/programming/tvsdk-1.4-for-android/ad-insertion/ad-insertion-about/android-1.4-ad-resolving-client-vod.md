---
description: For video-on-demand (VOD) content, TVSDK inserts ad breaks by splicing the ads in the main content so that the timeline duration increases.
seo-description: For video-on-demand (VOD) content, TVSDK inserts ad breaks by splicing the ads in the main content so that the timeline duration increases.
seo-title: VOD ad resolving and insertion
title: VOD ad resolving and insertion
uuid: 33280792-ad08-41c1-b180-cc2159e8137c
---

# VOD ad resolving and insertion{#vod-ad-resolving-and-insertion}

For video-on-demand (VOD) content, TVSDK inserts ad breaks by splicing the ads in the main content so that the timeline duration increases.

Before playback, TVSDK resolves known ads, inserts ad breaks in the main content as described by a timeline that is returned from Adobe Primetime ad decisioning, and recomputes the virtual timeline, if necessary.

TVSDK inserts ads in the following ways:

* **Pre-roll**, which is before the content. 
* **Mid-roll**, which is in the content. 
* **Post-roll**, which is after the content.

After playback starts,  no additional changes can occur in the content. Ads cannot be:

* Inserted 
* Deleted

  For example, you cannot delete built-in ads from the content to offer an ad-free experience. 
* Replaced

  For example, you cannot replace built-in ads with targeted ads.

