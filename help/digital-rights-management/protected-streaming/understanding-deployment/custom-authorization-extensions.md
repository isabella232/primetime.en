---
description: You can invoke custom authorization logic during license acquisition to decide if a license should be issued to the requesting client.
seo-description: You can invoke custom authorization logic during license acquisition to decide if a license should be issued to the requesting client.
seo-title: Custom authorization extensions
title: Custom authorization extensions
uuid: 588b05e5-3402-4586-bbd4-58b7e9a58ee4
---

# Custom authorization extensions{#custom-authorization-extensions}

You can invoke custom authorization logic during license acquisition to decide if a license should be issued to the requesting client.

If you want to implement your own customer authorization extension, you must first take a look at the [!DNL SampleAuthorizer.java] sample code that is located in the samples directory. The compiled version of this sample is located in [!DNL flashaccess-license-server-ext-sample.jar].

If you want to build your own extension, you need to implement the `com.adobe.flashaccess.server.license.extension.auth.IAuthorizer` interface and make sure [!DNL flashaccess-license-server-exts.jar] and [!DNL commons-logging.jar] are in the build path ( [!DNL adobe-flashaccess-sdk.jar] must also be in the build path if you use certain fields in `IMessageFacade`).

If you want to deploy your extension, you need to copy the jar or class files to *LicenseServer.ConfigRoot* [!DNL /flashaccessserver/libs].

If you want to update the jar or class files, you need to restart the server before the updated version can be used. You also must add the authorizer class name to the tenant configuration file. 
