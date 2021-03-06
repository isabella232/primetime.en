---
description: null
seo-description: null
seo-title: Allow list for Adobe® Flash® Player SWFs
title: Allow list for Adobe® Flash® Player SWFs
uuid: 670d8ccf-5145-499f-a6e3-d5d89562291e
---

# Allow list for Adobe® Flash® Player SWFs{#allowlist-for-adobe-flash-player-swfs}

This allow list specifies the SWF files that are allowed to play content.

Specify the SWF file with a SWF URL or a SHA-256 digest computed using the contents of the SWF. If you use the SHA-256 digest, this usage rule also specifies the maximum amount of time to allow for the client to download and verify the SWF.

Example use case: Conceptually equivalent to SWF Verification in the case of Flash Media Server, but enforced on the client side to limit which video players can play the content. Note that Primetime DRM behavior differs regarding the enforcement of the child SWF compared to the parent SWF. 
