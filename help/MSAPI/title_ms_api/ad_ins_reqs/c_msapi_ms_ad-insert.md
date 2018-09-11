---
description: All requests for ad insertion use the same URL structure and the same basic query parameters. Additional query parameters enable the manifest server to work with a variety of clients and situations.
seo-description: All requests for ad insertion use the same URL structure and the same basic query parameters. Additional query parameters enable the manifest server to work with a variety of clients and situations.
seo-title: Requests for ad insertion
title: Requests for ad insertion
uuid: fa798b39-036e-4111-9571-f07cfc67d645
index: y
internal: n
snippet: y
translate: y
---

# Requests for ad insertion

All requests for ad insertion use the same URL structure and the same basic query parameters. Additional query parameters enable the manifest server to work with a variety of clients and situations.


>[!NOTE]
>
>The __sid__ parameter is surrounded by double underscore characters.


<table id="table_210C8BF3E233489DAF4D2C9AED23A17A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><span class="codeph"> u</span> </td> 
   <td colname="col2">The asset ID is an MD5 hash of the <span class="codeph"> ad_request_id</span> from the Adobe Primetime ad decisioning metadata. <p>Provided by your Adobe Technical Account Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> z</span> </td> 
   <td colname="col2">The zone id for the asset that needs to be provided to Auditude. <p>Provided by your Adobe Technical Account Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> __sid__</span> </td> 
   <td colname="col2"> A unique id that the manifest server will use to generate the session id. </td> 
  </tr> 
 </tbody> 
</table>

The manifest server maintains sessions for individual clients or groups of clients to ensure that the sequences of API interactions for different clients stay separate. The `__sid__` that the client sends in the bootstrap URL to the manifest server should be unique within its environment. The manifest server uses it to construct a globally unique ID, which it returns to the client. 

The remaining query parameters pertain to different clients and situations. 
