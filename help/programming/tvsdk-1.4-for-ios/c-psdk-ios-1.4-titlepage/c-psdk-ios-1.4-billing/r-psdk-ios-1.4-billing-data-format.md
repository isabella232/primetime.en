---
description: TVSDK sends billing metrics to Adobe in an XML format.
seo-description: TVSDK sends billing metrics to Adobe in an XML format.
seo-title: Transmit billing metrics
title: Transmit billing metrics
uuid: 6a20b52a-dfcf-4e09-8af6-159d28a7afe2
index: y
internal: n
snippet: y
---

# Transmit billing metrics{#transmit-billing-metrics}

TVSDK sends billing metrics to Adobe in an XML format.

<!--<a id="example_13ABDB1CC0B549968A534765378DA3A0"></a>-->

If you use a network capture tool to monitor the statistics TVSDK transmits to Adobe, you should see units like the following:

```
<request> 
     <sc_xml_ver>1.0</sc_xml_ver> 
     <reportSuiteID>ptebilling</reportSuiteID> 
     <visitorID>5536C629-5EF7-4F02-8E5D-9FA136CB3CED</visitorID> 
     <pageName>com.adobe.primetime.psdksample</pageName> 
     <timestamp>2016-11-22T18:06:30+0000</timestamp> 
     <userAgent>Mozilla/5.0 (iPad; CPU OS 9_1 like Mac OS X) AppleWebKit/601.1.46 (KHTML, like Gecko) Mobile/13B143</userAgent> 
     <contextData> 
         <billingMetrics> 
                 <contentDuration>1799111</contentDuration> 
                 <contentURL>https%3A%2F%2Fdevimages.apple.com.edgekey.net%2Fstreaming%2Fexamples%2Fbipbop_16x9%2Fbipbop_16x9_variant.m3u8</contentURL> 
                 <contentType>vod</contentType> 
                 <midrollEnabled>true</midrollEnabled> 
                 <tvsdkVersion>1.0.211</tvsdkVersion> 
                 <platform>Mozilla/5.0 (iPad; CPU OS 9_1 like Mac OS X) AppleWebKit/601.1.46 (KHTML, like Gecko) Mobile/13B143</platform> 
                 <publisherID>com.adobe.primetime.psdksample</publisherID> 
                 <adsEnabled>true</adsEnabled> 
                 <type>start</type> 
         </billingMetrics> 
     </contextData> 
</request>
```

The boolean properties `drmProtected`, `adsEnabled`, and `midrollEnabled` appear only if they are true.  