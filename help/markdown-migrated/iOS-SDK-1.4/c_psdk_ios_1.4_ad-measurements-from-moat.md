---
description: TVSDK takes information from FreeWheel and other adservers providing VAST responses. FreeWheel provides, within VAST responses, information from the Moat service. The Moat service counts ad impressions with an accuracy that better shows that creatives capture or neglect an audience's interests.
seo-description: TVSDK takes information from FreeWheel and other adservers providing VAST responses. FreeWheel provides, within VAST responses, information from the Moat service. The Moat service counts ad impressions with an accuracy that better shows that creatives capture or neglect an audience's interests.
seo-title: Ad measurements from Moat
title: Ad measurements from Moat
---

# Ad measurements from Moat

Moat is a service measuring ad viewing across many uses, from browsers to within applications. Moat generates marketing analytics data in real-time across multiple platforms.

The VAST response XML has a property and an element your code can read, the outermost ad id property and the outermost extension element. Either way, your code can use TVSDK to save both the ad id information and the extension information and organize the information in a tree structure. With this organization, your code can pick up the data from any level and pass it along to wherever it needs to go. The value of the outermost ad id property enables your code to coordinate information from the associated campaign.

For example, FreeWheel can return data in an Extensions element. Below is a sample element.

```xml
&lt;Extensions&gt; 
 &lt;Extension type="FreeWheel"&gt; 
 &lt;Parameter name="moat"&gt; 
 &lt;MeasurementInfo renditionID="6398737" type="MediaFile"&gt; 
 &lt;MoatID&gt; 
 &lt;![CDATA[169843;56705;17860255;17860316;2509639;g8912342;103311138;g436558;530633]]]]&gt; 
 &lt;![CDATA[&gt; 
 &lt;/MoatID&gt; 
 &lt;/MeasurementInfo&gt; 
 &lt;MeasurementInfo renditionID="6398739" type="MediaFile"&gt; 
 &lt;MoatID&gt; 
 &lt;![CDATA[169843;56705;17860255;17860316;2509639;g8912342;103311138;g436558;530633]]]]&gt; 
 &lt;![CDATA[&gt; 
 &lt;/MoatID&gt; 
 &lt;/MeasurementInfo&gt; 
 &lt;/Parameter&gt; 
 &lt;/Extension&gt; 
&lt;/Extensions&gt;
```
Freewheel can also set the id property in the Ad element, as shown in the sample below.

```
&lt;Ad id="118566" sequence="1"&gt;
```
Refer to the API documentation for the class `codeph  PTNetworkAdInfo` in `codeph  PTAdAsset`.

