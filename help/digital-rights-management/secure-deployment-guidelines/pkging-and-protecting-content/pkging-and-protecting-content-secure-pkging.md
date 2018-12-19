---
description: The configuration file for the Adobe Primetime DRM Media Packager command-line tool requires a PKCS12 credential that is used during packaging.
seo-description: The configuration file for the Adobe Primetime DRM Media Packager command-line tool requires a PKCS12 credential that is used during packaging.
seo-title: Securely packaging content
title: Securely packaging content
uuid: 3887f48f-6c27-4eb8-b91c-4227fdd50f7b
index: y
internal: n
snippet: y
---

# Securely packaging content{#securely-packaging-content}

The configuration file for the Adobe Primetime DRM Media Packager command-line tool requires a PKCS12 credential that is used during packaging.

In the Reference Implementation command-tine tools, the password for the PKCS12 credentials file is stored in the `flashaccess.properties` file in clear text. For this reason, take extra care when you secure the computer that hosts this file and ensure that the computer is in a secure environment. For more information, see [Physical security and access](../../secure-deployment-guidelines/physical-sec-and-access.md).

The packager also uses the License Server and License Server Transport certificates, and the integrity and confidentiality of this information must be protected. Only authorized entities should be permitted to use the packager. If your private keys are compromised, inform Adobe Systems Incorporated immediately so that the certificate can be revoked.

>[!NOTE] {class="- topic/note "}
>
>The API enables you to use the same key for multiple pieces of content. To ensure the highest level of security, you should only use this feature for multi-bit rate FMS content. Do not use the same key for multiple files that represent different content.

The Primetime DRM Packaging API issues warnings under certain conditions. Review these warnings to determine whether your files have been successfully encrypted. The warning messages might be one of the following:

* 
* 
*

If content is packaged by using a policy with incorrect attributes, the policy needs to be updated. The updated policy must be made available to the License Server though a policy update list or another delivery mechanism. Some policy attributes cannot be changed after the policy is created. If these attributes are incorrect, pull the content back from the distribution sites, revoke the policy so that no future licenses can be granted, and encrypt the content again.

When packaging is complete, the packaging key is garbage-collected, and is not explicitly destroyed. As a result, the packaging key remains present in memory for some time. You must guard against unauthorized access to the machine and ensure that you do not expose any files, such as core dumps, that might reveal this information. 
