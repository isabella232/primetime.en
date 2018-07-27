---
seo-title: JSON object for entitlement resource ID
title: JSON object for entitlement resource ID
uuid: 107bc6fd-15da-49dd-9d73-19df6fe99185
index: n
internal: n
snippet: y
translate: y
---

# JSON object for entitlement resource ID


>The following code block provides an example of a JSON object when the entitlement resource ID is a simple text string. In this case, the resource ID is the string "resource".
>
>```
>"metadata" : { 
>"entitlement" : { 
>"id" : "resource" 
>} 
>}
>```

>The following code block provides an example of a JSON object when the entitlement resource ID is an HTML-encoded mRSS string.
>
>```
>&lt;rss version="2.0" xmlns:media="http://search.yahoo.com/mrss/"&gt; 
>&lt;channel&gt; 
>&lt;title&gt;REF_ADOBE&lt;/title&gt; 
>&lt;item&gt; 
>&lt;title&gt;Adobe Primetime Reference&lt;/title&gt; 
>&lt;guid&gt;1234&lt;/guid&gt; 
>&lt;media:rating scheme="urn:v-chip"&gt;TV-PG&lt;/media:rating&gt; 
>&lt;/item&gt; 
>&lt;/channel&gt; 
>&lt;/rss&gt;
>```
>The following mRSS string is used as the resource id.
>
>```
>"metadata" : { 
>    "entitlement" : { 
>        "id" : "&amp;lt;rss version=&amp;quot;2.0&amp;quot; 
>        xmlns:media=&amp;quot; 
>        http://search.yahoo.com/mrss/&amp;quot; 
>        &amp;gt;&amp;lt;channel&amp;gt;&amp;lt;title&amp;gt;REF_ADOBE&amp;lt;/title&amp;gt;&amp;lt;item&amp;gt; 
>        &amp;lt;title&amp;gt;Adobe Primetime Reference&amp;lt;/title&amp;gt;&amp;lt;guid&amp;gt; 
>        1234&amp;lt;/guid&amp;gt;&amp;lt;media:rating scheme=&amp;quot;urn:v-chip&amp;quot;&amp;gt; 
>        TV-PG&amp;lt;/media:rating&amp;gt;&amp;lt;/item&amp;gt;&amp;lt;/channel&amp;gt;&amp;lt;/rss&amp;gt;" 
>        } 
>} 
>
>```
