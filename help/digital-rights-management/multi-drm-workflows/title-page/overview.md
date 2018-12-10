---
description: You can implement multiple DRM solutions for your TVSDK apps using Primetime DRM Cloud, powered by ExpressPlay. DRM solutions include Apple's FairPlay, Google's Widevine, Microsoft's PlayReady, and Primetime Access from Adobe.
seo-description: You can implement multiple DRM solutions for your TVSDK apps using Primetime DRM Cloud, powered by ExpressPlay. DRM solutions include Apple's FairPlay, Google's Widevine, Microsoft's PlayReady, and Primetime Access from Adobe.
seo-title: Multi-DRM overview
title: Multi-DRM overview
uuid: 5722152d-6a8a-4d48-ae0a-dc7d3577205a
index: y
internal: n
snippet: y
---

# Multi-DRM overview{#multi-drm-overview}

You can implement multiple DRM solutions for your TVSDK apps using Primetime DRM Cloud, powered by ExpressPlay. DRM solutions include Apple's FairPlay, Google's Widevine, Microsoft's PlayReady, and Primetime Access from Adobe.

Adobe TVSDK supports DRM protection using multiple DRM schemes. Adobe offers *Primetime DRM Cloud, powered by ExpressPlay* to provide packaging, licensing, and playback of your video content on multiple platforms.

DRM schemes supported include Adobe’s *Primetime Access* DRM (AAXS), as well as native DRMs on various devices including [Widevine](http://www.widevine.com) on Chrome and Android, [FairPlay](https://developer.apple.com/streaming/fps/) on Safari and iOS, and [PlayReady](https://www.microsoft.com/playready/) on Edge and XboxOne. Check with an Adobe representative for information on which DRM schemes are currently available on these platforms, as well as the scheduled dates of future releases.

TVSDK supports DRM licenses issued by any license server using these protocols. In addition to support for multiple DRM solutions, Adobe offers *Primetime DRM Cloud, powered by ExpressPlay* as a solution in which ExpressPlay operates the license servers for each solution. This can simplify setup and maintenance for your DRM license issuance needs.

To use *Primetime DRM Cloud, powered by ExpressPlay* for implementing your DRM needs in TVSDK apps, you must first obtain an [ExpressPlay.com](https://www.expressplay.com) account. ExpressPlay provides the licensing capability for several different DRM protection schemes, and also provides other services including packaging and key management.

Your Adobe representative will initially set up your ExpressPlay account. You can then configure your account and obtain the *customer authenticators* that you will use in license token requests to the ExpressPlay servers. 
