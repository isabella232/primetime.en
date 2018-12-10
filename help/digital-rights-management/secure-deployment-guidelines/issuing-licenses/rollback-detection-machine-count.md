---
description: If the business rules require that the number of machines for a user be tracked, the License Server or Domain Server must store the machine IDs that are associated with the user.
seo-description: If the business rules require that the number of machines for a user be tracked, the License Server or Domain Server must store the machine IDs that are associated with the user.
seo-title: Machine count when issuing licenses
title: Machine count when issuing licenses
uuid: 3994e6d5-29ee-416c-98f8-09040a76bcce
index: y
internal: n
snippet: y
---

# Machine count when issuing licenses{#machine-count-when-issuing-licenses}

If the business rules require that the number of machines for a user be tracked, the License Server or Domain Server must store the machine IDs that are associated with the user.

The most robust way to track machine IDs is to store the value that is returned by the [ `MachineId.getBytes()`](http://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/cert/MachineId.html#getBytes()) method in a database. When a new request is received, compare the machine ID in the request with the known machine IDs by using [ `MachineId.matches()`](http://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/cert/MachineId.html#matches(com.adobe.flashaccess.sdk.cert.MachineId)).

[ `MachineId.matches()`](http://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/cert/MachineId.html#matches(com.adobe.flashaccess.sdk.cert.MachineId)) performs a comparison of IDs to determine whether the IDs represent the same machine. This comparison is only practical if there is a small number of machine IDs. For example, if users are allowed five machines in their domain, you can search the database for the machine IDs that are associated with the user’s username and obtain a small set of data for comparison.

This comparison is not practical for deployments that allow anonymous access. In this case, [ `MachineId.getUniqueID()`](http://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/cert/MachineId.html#getUniqueId()) can be used. However, this ID cannot be the same if the user accesses content from Flash and Adobe AIR® runtimes.

>[!NOTE]
>
>The ID does not survive if the user reformats the hard drive.

