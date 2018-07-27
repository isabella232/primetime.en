---
description: FYI, this topic doesn't appear to be used anywhere at this time (April 2015). That's good because it's incorrect, outdated, doesn't use items from the phrase library when it should, etc. Not going to fix it because it's not used. -ellen
seo-description: FYI, this topic doesn't appear to be used anywhere at this time (April 2015). That's good because it's incorrect, outdated, doesn't use items from the phrase library when it should, etc. Not going to fix it because it's not used. -ellen
seo-title: MBR configuration details
title: MBR configuration details
uuid: 15c57eee-9d89-482d-98bc-7300c49604fa
index: n
internal: n
snippet: y
translate: y
---

# MBR configuration details

There is only one public API: setABRParameters()
To return the parameters required for MBR processing, you need to implement the following functions from IPlaybackConfig: 

| getABRInitialBitRate() |Returns an integer value that represents the byte-per-second profile. |
|---|---|
| getABRMinBitRate() |Returns an integer value that represents the byte-per-second profile. |
| getABRMaxBitRate() |Returns an integer value that represents the byte-per-second profile. |
| [getABRPolicy()](http://help.adobe.com/en_US/primetime/api/psdk/javadoc/com/adobe/mediacore/ABRControlParameters.html#getABRPolicy())  |Returns the ABRPolicy enum: ABR_AGGRESSIVE, ABR_CONSERVATIVE and ABR_MODERATE . |

