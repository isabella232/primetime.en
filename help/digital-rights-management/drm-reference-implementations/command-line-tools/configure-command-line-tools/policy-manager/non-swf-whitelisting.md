---
seo-title: Non-SWF Application Whitelisting
title: Non-SWF Application Whitelisting
uuid: d4f93b15-e556-4749-95ab-f7f58b1061d7
---

# Non-SWF Application Whitelisting {#non-swf-application-whitelisting}

AIR was the first platform that featured application whitelisting, and the name of the property you use to whitelist non-SWF applications (Adobe AIR, iOS, Android, etc.) retains its original name: `policy.allowedAIRApplication.n`. This allows the content to be played back by all non-Flash applications that are signed with a Signing Certificate prior to publishing. This is referred to as the *Application ID*. You can extract the Application ID by using the [!DNL AdobePublisherIDUtility.jar] tool. This whitelisting will be enforced on any client that supports Primetime DRM.

The Application ID is derived from the public key of the signing certificate used to sign a particular application. If the public key in the certificate ever expires, then all previous content whitelisted to only play on apps signed with the old certificate will not play on the new app (signed with the new certificate).

If you are in the situation where you have a library of content whitelisted to applications that were signed with a particular signing certificate, and that certificate expires and you are issued a new certificate (with a different public/private keypair), your old content will not play on your new app *unless* you do any of the following:

* Use a `PolicyUpdateList` on your license server to override the incoming policy and insert a new Application Whitelist entry with your new signing certificate's digest . 
* Update your license server's logic to override the incoming policy and insert a new Application Whitelist entry. 
* Request that your signing certificate issuer issues you a new certificate that uses the same public/private keypair that your previous certificate used. 
* If you are delivering HDS/HLS content that is referencing a URL endpoint to retrieve the `DRMMetadata`, you can regenerate the `DRMMetadata` (using the Primetime DRM Java SDK) to insert a new DRM Policy that contains an updated Application Whitelist entry. 

* Repackage all of your old content with a new DRM policy that has the digest of your new signing certificate.

See `policy.allowedAIRApplication.n` in *Configuration properties* for details.

>[!NOTE]
>
>Whitelisting an iOS application requires you a special approach. See [Whitelist your iOS application](../../../../../programming/tvsdk-3x-ios-prog/ios-3x-drm-content-security/ios-3x-whitelist-your-ios-application.md) in the *TVSDK for iOS Programmer's Guide*.