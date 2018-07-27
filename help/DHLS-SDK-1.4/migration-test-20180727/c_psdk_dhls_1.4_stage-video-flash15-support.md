---
description: From Flash 15 and later, when hardware rendering with StageVideo is not available, StageVideo seamlessly falls back to a software StageVideo object.
seo-description: From Flash 15 and later, when hardware rendering with StageVideo is not available, StageVideo seamlessly falls back to a software StageVideo object.
seo-title: Flash 15 support for StageVideo
title: Flash 15 support for StageVideo
uuid: 1e5d966d-5cbd-4a7d-9167-b1381955c4e0
index: n
internal: n
snippet: y
translate: y
---

# Flash 15 support for StageVideo

Consider the following information about the Flash 15 StageVideo fallback to software: 
* No code changes are required in your application.
* No change to the  <!-- PH element: phrases/primetime-sdk-name --> is required.You do not need a  <!-- PH element: phrases/primetime-sdk-name --> update to use StageVideo fallback to software.

* Your applications need to be recompiled for Flash 15.
* Applications that you recompile for Flash 15 will continue to work with Flash 14 and earlier, as long as these applications do not use any new APIs that were introduced in Flash Player 15. If your Flash 14 application needs to use a new Flash 15 API, you must dynamically call the API with a cast to the Object type, so that the application does not fail in Flash Player 14 at runtime.


**HTML Overlays** 
In Flash 15 and later, you can maintain a seamless display of HTML overlays when hardware StageVideo becomes unavailable and falls back to software StageVideo. To enable this feature, set `wmode=opaque`. 
Some older browsers do not support hardware acceleration. For more information about these requirements, see [StageVideo minimum requirements](r_psdk_dhls_1.4_requirements-stage-video.md#reference_req_stagevideo). When you set `wmode=opaque`, the video is rendered with software StageVideo, which can impact performance. Typically, setting `wmode=direct` directly renders video to GPU, which results in much better performance. However, this option also overrides HTML overlays. 
