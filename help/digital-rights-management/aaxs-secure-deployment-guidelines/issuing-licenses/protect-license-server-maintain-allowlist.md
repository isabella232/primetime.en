---
seo-title: Maintain a allowlist of trusted content packagers
title: Maintain a allowlist of trusted content packagers
uuid: ad40993c-15c3-43b2-9593-7b75802cfe69
---

# Maintain a allowlist of trusted content packagers{#maintain-a-allowlist-of-trusted-content-packagers}

A *allowlist* is a list of trusted entities. In the case of content packagers, these are organizations trusted by the content owner to package (or encrypt) the FLV/F4V video files, creating DRM protected content. When deploying Adobe Access, it is recommended that you maintain a allowlist of trusted content packagers, and that you verify the identity of the content packager contained in the DRM metadata (the DRM header) of a DRM protected file prior to issuing a license.

To learn more about obtaining information about the entity that packaged the content, see `V2ContentMetaData.getPackagerInfo()` in the *Adobe Access API Reference*.
