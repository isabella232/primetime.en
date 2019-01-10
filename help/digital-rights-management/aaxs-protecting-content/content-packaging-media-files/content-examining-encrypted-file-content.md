---
seo-title: Examining encrypted file content
title: Examining encrypted file content
uuid: 2132fac7-5f11-4308-b511-ed4f216527a6
index: y
internal: n
snippet: y
---

# Examining encrypted file content{#examining-encrypted-file-content}

To examine the contents of an FLV or an F4V file by using the Java API, perform the following steps:

1. Set up your development environment and include all of the JAR files mentioned in [Setting up the development environment](settingUpSDK.md#WS287f927bd30d4b1f4fad6c7f1304f5e91be-7fff_ver2.0) within your project. 
1. Create a `MediaEncrypter` instance. 
1. Pass the encrypted file to the `MediaEncrypter.examineEncryptedContent` method, which returns a `KeyMetaData` object. 
1. Inspect the information within the `KeyMetaData` object.

For sample code demonstrating how to extract DRM metadata from an encrypted file, see `com.adobe.flashaccess.samples.mediapackager.ExamineContent` in the Reference Implementation Command Line Tools “samples” directory. 
