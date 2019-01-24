---
seo-title: White-list for Adobe® Flash® Player SWFs allowed to play protected content
title: White-list for Adobe® Flash® Player SWFs allowed to play protected content
uuid: 482bfbed-7ef9-48d9-b399-d23fddabc81e
index: y
internal: n
snippet: y
---

# White-list for Adobe® Flash® Player SWFs allowed to play protected content {#white-list-for-adobe-flash-player-swfs-allowed-to-play-protected-content}

Specifies the SWF files that can play content. Specify the SWF file by a SWF URL or a SHA-256 digest computed using the contents of the SWF. If you use the SHA-256 digest, this usage rule also specifies the maximum amount of time to allow for the client to download and verify the SWF.

Example use case: Conceptually equivalent to SWF Verification in the case of Flash Media Server, but enforced on the client side to limit which video players can play the content. Note that Adobe Access behavior is different in regards to enforcement of the child SWF compared to the parent SWF. 
