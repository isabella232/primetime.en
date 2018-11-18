---
description: While the default Creative Repackaging Service (CRS) scenario is to use one Content Data Network (CDN), you can deploy CRS assets on more than one CDN.
seo-description: While the default Creative Repackaging Service (CRS) scenario is to use one Content Data Network (CDN), you can deploy CRS assets on more than one CDN.
seo-title: Multiple CDN support for CRS ad delivery
title: Multiple CDN support for CRS ad delivery
uuid: bff125bb-2100-4855-81e6-98297da6e4b4
index: y
internal: n
snippet: y
---

# Multiple CDN support for CRS ad delivery{#multiple-cdn-support-for-crs-ad-delivery}

While the default Creative Repackaging Service (CRS) scenario is to use one Content Data Network (CDN), you can deploy CRS assets on more than one CDN.

You can use multiple CDNs for the following reasons:

* A requirement to scale up for large viewing events. 
* A requirement to match the CDN source of the CRS asset with the CDN source of the main content.

You can transform the default URL that is provided by the CRS by using TVSDK URL Transformer APIs.

Here are the API additions in TVSDK:

* `URLTransformer` An interface that describes the methods that are required to transform the CRS ad URLs that are requested by TVSDK. Applications can implement this interface and provide implementations for the required methods. 

* `DefaultURLTransformer` The default URL transformer instance that is created in TVSDK and that implements the `URLTransformer` interface. Applications can override this class or add a post URL transformation handler. This handler is useful when the application wants to make changes to the URL request after the default transformation has been applied. 

* `NetworkConfiguration.setURLTransformer` A setter method that is provided on the `NetworkConfiguration` metadata instance to set the `URLTransformer` implementation.

>[!IMPORTANT]
>
>Your app implementations must check for the `URLTransformerInputType` enumeration and only transform URLs of type `URLTransformerInputType.CRSCreative` for CRS.

The following code sample shows how your application can change the default host component to a different string (for example, `cdn.mycrsdomain.com`): 

```java
NetworkConfiguration networkConfiguration = new NetworkConfiguration(); 
DefaultURLTransformer urlTransformer = new DefaultURLTransformer(); 
urlTransformer.addPostURLTransformHandler(new DefaultURLTransformer.URLTransformHandler() { 
    @Override 
    public String call(String url, URLTransformerInputType type) { 
        if (type == URLTransformerInputType.CRSCreative) { 
            try { 
                return url.replaceAll(new java.net.URI(url).getHost(), "cdn.mycrsdomain.com"); 
            } catch (URISyntaxException e) { 
            } 
        } 
        return url; 
    } 
}); 
   
networkConfiguration.setURLTransformer(urlTransformer); 
   
// metadata is the Metadata instance set on a MediaResource instance. 
metadata.setNode(DefaultMetadataKeys.NETWORK_CONFIGURATION.getValue(), networkConfiguration);
```

