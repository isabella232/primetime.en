---
description: For video-on-demand (VOD) content, inserts ad breaks by splicing the ads in the main content so that the timeline duration increases.
seo-description: For video-on-demand (VOD) content, inserts ad breaks by splicing the ads in the main content so that the timeline duration increases.
seo-title: VOD ad resolving and insertion
title: VOD ad resolving and insertion
uuid: 574ff526-fe33-4526-b3db-ca6c80978337
index: n
internal: n
snippet: y
translate: y
---

# VOD ad resolving and insertion

Before playback,  <!-- PH element: phrases/primetime-sdk-name --> resolves known ads, inserts ad breaks in the main content as described by a timeline that is returned from <!-- PH element: phrases/auditude-name-long --> , and recomputes the virtual timeline, if necessary.
<!-- PH element: phrases/primetime-sdk-name --> inserts ads in the following ways:

* **Pre-roll**, which is before the content.
* **Mid-roll**, which is in the content.
* **Post-roll**, which is after the content.

>[!IMPORTANT]
>
>When implementing a custom `AdPolicySelector`, a different policy can be given to each type of `AdBreakTimelineItem` (pre-roll, mid-roll, or post-roll) in `AdPolicyInfo`, based on the type of the `AdBreakTimelineItem`. For example, you can keep mid-roll content after it has played but remove pre-roll content after it has played. 

After playback starts, 
* Inserted
* Deleted For example, you cannot delete built-in ads from the content to offer an ad-free experience.

* Replaced For example, you cannot replace built-in ads with targeted ads.


