---
seo-title: Custom authorization extensions
title: Custom authorization extensions
uuid: 8aa99488-1f36-43f4-b414-ff194e98536e
index: y
internal: n
snippet: y
---

# Custom authorization extensions{#custom-authorization-extensions}

Custom authorization logic may be invoked during license acquisition to decide if a license should be issued to the requesting client.

To implement your own customer authorization extension, first look at the [!DNL SampleAuthorizer.java] sample code located in the samples directory (the compiled version of this sample is located in flashaccess-license-server-ext-sample.jar).

To build your own extension, implement the `com.adobe.flashaccess.server.license.extension.auth.IAuthorizer` interface and make sure [!DNL flashaccess-license-server-exts.jar] and [!DNL commons-logging.jar] are on the build path (adobe-flashaccess-sdk.jar must also be on the build path if you utilize certain fields in `IMessageFacade`). To deploy your extension, copy your jar or class files to *LicenseServer.ConfigRoot* [!DNL /flashaccessserver/libs]. If you need to update the jar or class files, the server must be restarted before the updated version is used. You also must add the authorizer class name to the tenant configuration file. 
