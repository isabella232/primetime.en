---
seo-title: Updating policies
title: Updating policies
uuid: f6686c8b-bedf-4ec5-a14e-f03326519f89
index: y
internal: n
snippet: y
---

# Updating policies{#updating-policies}

If policies are updated after the content is packaged, provide the updated policies to the license server so the updated version can be used when issuing a license. If your license server has access to a database for storing policies, you can retrieve the updated policy from the database and call `LicenseRequestMessage.setSelectedPolicy()` to provide the new version of the policy.

For license servers that do not rely on a central database, the SDK provides support for Policy Update Lists. A policy update list is a file containing a list of updated or revoked policies. When a policy is updated, generate a new Policy Update List and periodically push the list out to all the license servers. Pass the list to the SDK by setting `HandlerConfiguration.setPolicyUpdateList()`. If an update list is provided, the SDK consults this list when parsing the content metadata. `ContentInfo.getUpdatedPolicies()` contains the updated versions of policies specified in the metadata.

See [Working With Policies](../../../aaxs-protecting-content/content-working-with-policies/content-working-with-policies.md) and [Policy update lists.](content-policy-update-lists.md) 
