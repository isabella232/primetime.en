---
description: For video-on-demand (VOD) content, inserts ad breaks by splicing the ads in the main content so that the timeline duration increases.
seo-description: For video-on-demand (VOD) content, inserts ad breaks by splicing the ads in the main content so that the timeline duration increases.
seo-title: VOD ad resolving and insertion
title: VOD ad resolving and insertion
uuid: 606f80df-2f2d-4b8a-afa2-15b3811c83df
index: n
internal: n
snippet: y
translate: y
---

# VOD ad resolving and insertion

Before playback,  <!-- PH element: phrases/primetime-sdk-name --> resolves known ads, inserts ad breaks in the main content as described by a timeline that is returned from <!-- PH element: phrases/auditude-name-long --> , and recomputes the virtual timeline, if necessary.
<!-- PH element: phrases/primetime-sdk-name --> inserts ads in the following ways:

* **Pre-roll**, which is placed before the content.
* **Mid-roll**, which is in the middle of the content.
* **Post-roll**, which is placed after the content.

>[!TIP]
>
>After playback starts, no additional changes can occur in the content.

Ads cannot be: 
* Inserted
* Deleted For example, you cannot delete built-in ads from the content to offer an ad-free experience.

* Replaced For example, you cannot replace built-in ads with targeted ads.


