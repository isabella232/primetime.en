---
seo-title: Working with DRM Policy Update Lists
title: Working with DRM Policy Update Lists
uuid: 41f89671-81c6-4d3d-ac31-9c2a1980517a
---

# Working with DRM Policy Update Lists {#working-with-drm-policy-update-lists}

If you update the usage rules in a DRM policy after packaging any content, the license server needs to have the latest version before it can issue licenses that use an updated DRM policy. One way to achieve this is through a DRM policy update list.

A DRM policy update list is represented by a file that includes a list of updated or revoked DRM policies. Whenever you update a DRM policy, you need to generate a new DRM Policy Update List and periodically push the list to all license servers.

For license servers that do not have access to a database for storing information about DRM policies, you may want to use a DRM policy update list to notify the license server of any updated DRM policies. DRM Policy Update Lists may include updated versions of DRM policies or a list of DRM policy IDs that have been revoked. If a policy update list is included in `HandlerConfiguration`, the SDK enforces this list when it issues a license.

You can also revoke any DRM policies if content owners or distributors want to discontinue issuing licenses under a particular DRM policy. A DRM policy update list can be used to enforce DRM policy revocation in the SDK. You can also apply DRM policy update lists to provide a list of updated DRM policies to the SDK.

>[!NOTE]
>
>Whenever you revoke a DRM policy, any licenses that have already been issued are not automatically revoked. It only prevents additional licenses from being issued under that DRM policy.

