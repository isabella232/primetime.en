---
description: Resolving ads might cause delays in starting playback, and lazy ad resolving can reduce this delay.
seo-description: Resolving ads might cause delays in starting playback, and lazy ad resolving can reduce this delay.
seo-title: Lazy ad resolving
title: Lazy ad resolving
uuid: 9b0d69af-3b61-40bb-8254-4ad905a1b4ae
index: n
internal: n
snippet: y
translate: y
---

# Lazy ad resolving

To play content with embedded advertising, TVSDK downloads a manifest (playlist), which contains URLs of the content segments and the advertising. Before playing the ads, TVSDK resolves the ads. The player uses the URLs in the manifest to obtain the ad content (creatives), ensures that the ad content is in a format that TVSDK can play, and TVSDK places the ads on the timeline. If the manifest contains several ad URLs, this process might take ten seconds or more.

>[!TIP]
>
>Lazy ad resolution does not affect pre-roll ads.

After the pre-roll ads are in place and the player is prepared to play, the player resolves additional ads as content is playing. During playback, the player places the ads on the timeline and updates the scrub bar if necessary.
Lady ad resolving is enabled by default, but you can disable it.

>[!IMPORTANT]
>
>Although content is played back much faster, missing ad breaks might occur in the first 60 seconds. Lazy ad resolution requires the player application to disable seeks or trick play operations until all ads are resolved. Also, lazy ad resolution is incompatible with instant on. For more information, see instant-on . 

